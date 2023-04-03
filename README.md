# guestbook-docker-kubernetes-openshift-demo

In this project, we will build a simple guestbook app using docker, kubernetes and openshift. IBM cloud holds our namespaces for the app.

# Run app

 1. change your current directory to v1/guestbook
 
```
        cd v1/guestbook
```

 2. Export your namespace as an environment variable so that it can be used in subsequent commands.
 
```
        export MY_NAMESPACE=sn-labs-$USERNAME
```

 3. Build the guestbook app using the Docker Build command.
 
```
        docker build . -t us.icr.io/$MY_NAMESPACE/guestbook:v1
```
    
 4. Push the image to IBM Cloud Container Registry.
 
```
        docker push us.icr.io/$MY_NAMESPACE/guestbook:v1
```

 5. Apply the deployment using the following command.
    
```
        kubectl apply -f deployment.yml
```

 6. Open a New Terminal and enter the below command to view your application.
 
 ```
        kubectl port-forward deployment.apps/guestbook 3000:3000
 ```
 
 7. Launch your application on port 3000. Click on the Skills Network button on the right of your IDE, 
    it will open the “Skills Network Toolbox”. 
    Then click the Other then Launch Application. From there you should be able to enter the port and launch.
