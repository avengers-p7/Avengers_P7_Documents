# GitOps Tools
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Vishal Kumar Kesarwani | 12-01-2024 | 16-01-2024   | v1 | Vishal |
***
# Table of Contents

+ [Purpose](#Purpose)
+ [Tools](#This-document-includes-evaluation-of-GitOps-tools)
+ [ArgoCD ](#ArgoCD )
+ [FluxCD](#FluxCD)
+ [Jenkins X](#Jenkins-X)
+ [BuildPiper](#BuildPiper)
+ [Technical Specifications](#Technical-Specifications)
+ [Tools Comparison](#Tools-Comparison:-ArgoCD-vs-FluxCD-vs-Jenkins-X-vs-Bulidpiper)
+ [Conclusion](#Conclusion)
+ [Contact Information](#Contact-Information)
+ [References](#References)

***
# Purpose 

This document will explore some of the popular tools that can help you enable GitOps workflow in your application environment by automating the testing and deployment of IaC codes.

***

## This document includes evaluation of GitOps tools:
Multiple GitOps tools come with different features and may not cover all GitOps needs. Still, we recommend trying out these  popular GitOps tools:-
* ArgoCD 
* FluxCD
* Jenkins X
* BuildPiper

***
# ArgoCD 
![image](https://github.com/avengers-p7/Documentation/assets/156056413/667bc1b0-10e2-4148-b57e-ccdc988a83ca)

Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes,responsible for continuously monitoring all running applications and comparing their live state to the desired state specified in the Git repository.

# FluxCD
![image](https://github.com/avengers-p7/Documentation/assets/156056413/a6601987-a3d0-4362-9e72-754900b9eeb2)

Flux CD is a Continuous Delivery tool to help keep Kubernetes clusters in sync with configuration sources such as Git repositories and automate configuration updates when available. Flux is built with the GitOps toolkit and supports multi-tenancy and syncing an arbitrary number of Git repositories.


# Jenkins X
![image](https://github.com/avengers-p7/Documentation/assets/156056413/7864044f-dd4d-4692-b887-15f9d551c41d)

Jenkins X automates and accelerates Continuous Integration and Continuous Delivery for developers on the cloud, so they can focus on building software,The entire Jenkins X experience is based around Git. The installation, extensions and applications you develop are managed via a cluster Git repository which is the desired state of your Kubernetes cluster.

# BuildPiper 
![image](https://github.com/avengers-p7/Documentation/assets/156056413/36ff2865-9b5b-41e9-bfa9-1628f0f1aad0)

BuildPiper is a developer and engineering teams’ centric, fully-featured, end-to-end Kubernetes & Microservices Application Delivery Platform. It enables teams to onboard & securely manage Kubernetes & Microservices applications in a seamless manner. Also, the platform empowers teams with the ability to run zero-touch, fully automated & secured CI/CD pipelines.
It provides functionality for modern approaches of CI, CD, GitOps, Observability, Compliance , etc. BuildPiper seamlessly integrates with industry-leading tools like JIRA, SLACK, MS Teams, EFK, Prometheus/Grafana etc.

***
# Technical Specifications
| **Topic** | **ArgoCD** | **FluxCD** | **Jenkins X** | **Buildpiper** |
| --------- | ---------- | ---------- | ------------- | -------------- |
| **Pre-Requisites** | Kubernetes Cluster (v1.23 and later) | Kubernetes Cluster (v1.26 and later) | Kubernetes Cluster | Kubernetes Cluster |
| **System Requirements** | 2 CPU cores and 4GB of RAM | 2 CPU cores and 4GB of RAM  | 2 CPU cores and 4GB of RAM  | 4 CPU cores and 8GB of RAM |
| **Important Ports** | 80, 443 | 80, 443 | 8080, 80, 443 | 80,443 |
| **Dependency** | kubectl | kubectl, Git | kubectl, Git | bpctl,kubectl, Git, Docker |


***
#  Tools Comparison: ArgoCD vs FluxCD vs Jenkins X vs Bulidpiper

| **Feature** | **ArgoCD** | **FluxCD** | **Jenkins X** | **Buildpiper** |
|-------------|------------|------------|---------------|----------------|
| **Primary Use Case** | Continuous Deployment to Kubernetes | GitOps for Kubernetes environments | CI/CD and GitOps for Kubernetes | CI/CD and GitOps |
| **Declarative Configuration** | Yes | Yes | Yes | Yes |
| **Multicluster Support** | Yes | Yes | Yes | Yes |
| **Integration with Helm** | Yes | Yes | Yes | Yes |
| **Web UI** | Yes | Yes | Yes | Yes |
| **Trigger Mechanisms** | Webhooks, CLI, API | Webhooks, CLI, API | Webhooks, Events, CLI, GitOps | Webhooks,UI,API,CLI |
| **Programming Language** | Go | Go | Java, Groovy, Shell | Shell,HCL,Java,Python |
| **Community Support** | Active | Active | Active | Growing |
| **Enterprises Support** | 3rd Party | 3rd Party | Yes | Yes |
| **Documentation Quality** | Good | Good | Good | Developing |
| **License** | Apache License 2.0 | Apache License 2.0 | Apache License 2.0 | Apache License 2.0 |
| **Advanced Scaling** | Auto-scaling based on resource utilization| Manual scaling based on configuration | Auto-scaling based on demand | Auto-scaling based on workload |
| **Secrets Management** | Integrated with Kubernetes secrets | Customizable secrets management | Integrated with Kubernetes secrets | Supports various secret management tools |
| **Policy Enforcement** | Customizable RBAC and policies | Customizable RBAC and policies | Role-based access control (RBAC) | Role-based access control (RBAC) |
| **Extensibility** | Plugins and custom controllers | Custom controllers and operators | Plugins and extensions | Plugin system for extensibility |
| **Artifact Management** | Support for managing container images | Integrates with container registries | Integrated with artifact repositories | Supports various artifact repositories |
| **Monitoring Integration** | Prometheus integration for monitoring | Prometheus and Grafana integration | Built-in monitoring and observability | Integration with popular monitoring tools |
| **Pipeline Visualization** | Visual representation of deployment pipelines| Visual representation of GitOps workflows | Visual pipeline visualization | Visual representation of CI/CD workflows |

***

# Conclusion

The choice between ArgoCD, FluxCD, Jenkins X, and Buildpiper depends on your specific needs and preferences. Here's a general guideline:

* **ArgoCD:** Ideal for continuous deployment in Kubernetes environments with a focus on declarative GitOps principles.

* **FluxCD:** Suitable for managing GitOps workflows in Kubernetes and provides good support for continuous delivery.

* **Jenkins X:** Well-suited for comprehensive CI/CD and GitOps in Kubernetes, offering a broad range of features and good extensibility.

* **Buildpiper:** BuildPiper is a one-stop solution for managing the entire lifecycle of a containerized application. Right from environment setup to build and deployment- everything is available as a plug-and-play solution and is fully customizable.

Ultimately, the "best" tool depends on your project requirements, team expertise, and the specific workflows you want to implement. Evaluate each tool based on your needs, and consider factors such as community support, documentation, and extensibility for a well-informed decision.

***
## Contact Information:
| Name | Email address |
| ---- | ------------- |
| Vishal | vishal.kesarwani.snaatak@mygurukulam.co |

***
## References:
| Source | Description |
| ------ | ----------- |
| https://www.w6d.io/blog/gitops-tools/ | Gitops Tools Features |
| https://loft.sh/blog/gitops-kubernetes-comparing-argo-cd-vs-jenkins-x-vs-flux-vs-spinnaker/ | Gitops Tools Features |
| https://buildpiper.io/documentation/docs/getting/introducing https://www.buildpiper.io/documentation/docs/managed-kubernetes/kubernetescheatsheet/ | Buildpiper |
| https://www.devopsschool.com/blog/list-of-gitops-tools/ | Gitops Tools Architecture |
| https://www.tynybay.com/our-thinking/argocd-vs-fluxcd-vs-jenkins-x-which-gitops-implementation-tool-suits-you-the-best#:~:text=Argo%20CD%20supports%20multi%2Dtenancy,with%20a%20set%20of%20cons. | Gitops Tools Installation |
