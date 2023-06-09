# manifest file for Kubernetes TodoReactApp

The manifest file defines a Kubernetes Deployment and Service for the WIL42 application.

The Deployment section specifies the desired state of the application. It sets the replica count to 3 and defines a selector to match the labels of the Pods. The template section specifies the Pod template, which includes the container definition for the WIL42 application. It uses the wil42/playground:latest Docker image and exposes port 8080.

The Service section defines a ClusterIP service that selects the Pods labeled with app: wil42-app. It exposes port 8888 and forwards traffic to the targetPort 8888 of the Pods.\
(!) Without a Service, other resources or external entities won't be able to access the WIL42 application using a stable network endpoint. The application will only be accessible within the cluster's network, and you won't be able to access it from outside the cluster.

Related project: https://github.com/jesuisstan/Kubernetes_ArgoCD_for_TodoReactApp
