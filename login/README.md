# Configuring an htpasswd identity provider

By default, only a `kubeadmin` user exists on your cluster. To specify an identity provider, you must create a custom resource (CR) that describes that identity provider and add it to the cluster.

1. Create an htpasswd file to store the user and password information.
1. Create a secret to represent the htpasswd file.
1. Define an htpasswd identity provider resource that references the secret.
1. Apply the resource to the default OAuth configuration to add the identity provider.

## Create user
Creating a generic user
```sh
# Login to cluster
oc login --token=<token> --server=<https://api.cluster...:6443>

# Create scratch dir
mkdir scratch

# Add scratch to .gitignore
echo scratch >> . .gitignore

# Create or update your flat file with a user name and hashed password:
htpasswd -c -B -b scratch/users.htpasswd <username> <password>

# Create a Secret object that contains the htpasswd users file:
oc create secret generic htpass-secret --from-file=htpasswd=scratch/users.htpasswd -n openshift-config

# Verify the Htpasswd custom resource config is created
oc get secret/htpass-secret -n openshift-config -o yaml

# The following custom resource (CR) shows the parameters and acceptable values for an htpasswd identity provider
oc apply -f login/htpass-oauth.yaml

# Obtain an API token to login
oc login --web
```

## Update htpasswd
Adding an Administrator user

```sh
# Retrieve the htpasswd file from the htpass-secret Secret object and save the file to your file system:
oc get secret htpass-secret -ojsonpath={.data.htpasswd} -n openshift-config | base64 --decode > scratch/users.htpasswd

# To add a new user:
htpasswd -bB scratch/users.htpasswd <username> <password>

# Replace the htpass-secret Secret object with the updated users in the users.htpasswd file:
oc create secret generic htpass-secret --from-file=htpasswd=scratch/users.htpasswd --dry-run=client -o yaml -n openshift-config | oc replace -f -
```

## Applying the cluster-admin role

```sh
# Define the user as a cluster admin
oc adm policy add-cluster-role-to-user cluster-admin <user>
```

## Resources
1. [Configuring an htpasswd identity provider 
Copy link
](https://docs.redhat.com/en/documentation/openshift_container_platform/latest/html/authentication_and_authorization/configuring-identity-providers#configuring-htpasswd-identity-provider)
1. [Creating a cluster admin](https://docs.openshift.com/container-platform/latest/authentication/using-rbac.html#creating-cluster-admin_using-rbac)