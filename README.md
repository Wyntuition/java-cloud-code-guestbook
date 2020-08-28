# Building Java Apps in Kubernetes, using Cloud Code and Minikube

This will take you through a good software development workflow of building a Java app that will run in Kubernetes. 

To simulate production as much as possibly and gain developer efficiencies in setting up standard development environments, we will develop in a real Kubernetes cluster locally using Minikube. We will use the Kubernetes developer productivity tools Cloud Code and Skaffold to integrate with our IDE and automate much of the inner loop.

_[Cloud Code](https://cloud.google.com/code/)_ is a VS Code/IntelliJ plug-in that provides a lot of Kubernetes helper functionality, including applying deployments, services, exploring objects and running many commands. _[Skaffold](https://skaffold.dev/)_ automates much of the image creation, tagging & push loop. 

The app code here was genereated from the Cloud Code template, and uses:

- Sprint Boot with Maven for frontend and backend containers, and a mongo container for the database
- Skaffold for managing the image build/push process
- Dockerfiles for dev and prod images (multi-stage builds)

The features are:

- Live reload of code changes
- Debugging
- Using real Kubernetes to run and test locally

## Getting started

1. Install [minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/), then start a cluster with `minikube start`. 
1. Install `Cloud Code` in VS Code/IntelliJ. 
1. Run Cloud Code > Run in Kubernetes (menu, or Command-Shift-P > Cloud Code: Run on Kubenetes in VS Code). It will create each image and run the deployment and service manifest files, and output URLs.
1. Try the app via the frontend URL, and change some code and see Live Reload update the app.