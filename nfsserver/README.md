# nfs server in kube

If you need an nfs server in kube--like for example if you need a read-write-many--this is one way to do it.

    ./burnup

You should have a running nfs server:

    kubectl get service 
    nfsshare             ClusterIP   10.104.245.244   <none>        2049/TCP            85m

Grab that IP to pass along to your clients to use in their deployments volumes. Unfortunately you can't use the service name in your client deploys, you have to use the ip:

    ...deploy yml...
    volumes:
    - name: data
      nfs: 
        server: 10.104.245.244
        path: /


You can take down the server with:

    ./burndown 


The data will not be deleted unless you do:

    ./burndown allofit




