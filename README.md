This repo when run with Jenkins pipeline creates docker image of the app and pushes to the docker hub. It then updates the deployment.yml in https://github.com/prashantjkamath/projectpipeline5_manf.git
CI part is done via Jenkins and CD part via ArgoCD (GitOps).

Prerequisites:
1) Jenkins installation, docker and git installations
2)  Jenkins plugins
3) ArgoCD installation 

