# kubeuser

This python script creates a kubernetes namespace & rolebinding for the default service account in the namespace.

Then it grabs the token for the service account and prints out a full ~/.kube/config file required to access the namespace.

The script should be run by an admin on the Kube cluster (i.e. default namespace).
