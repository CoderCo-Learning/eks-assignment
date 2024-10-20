# CoderCo Assignment 2 - Production Grade EKS Cluster with Ingress and SSL

Your task is to create a production-grade Kubernetes (EKS) cluster on AWS, exposing applications securely with HTTPS. You’ll use key tools like Helm, NGINX Ingress Controller, cert-manager for managing SSL certificates, and externalDNS for syncing DNS records. Optionally, you may integrate ArgoCD for deployment automation.

## Task/Assignment

- Create AWS Resources: Set up a VPC and an EKS cluster using infrastructure-as-code tools using Terraform. Ensure the cluster is ready for production with proper networking, security groups and correct node size configuration.

- Deploy Key Helm Charts:
  - Install NGINX Ingress Controller to manage ingress traffic.
  - Use cert-manager to automate SSL certificate issuance and renewal with Let’s Encrypt.
  - Set up externalDNS to automatically manage and update DNS records in Route53.

- Test Application Deployment: Deploy a sample application (e.g., a simple web app or even use the Threat Modeling Tool app we used in the previous assignment) and configure the ingress to expose it publicly via a custom domain. Ensure it is accessible over HTTPS.

- Bonus Task (Optional):

  - Integrate ArgoCD into the setup to automate your application deployment pipelines using GitOps principles.

## Requirements

- The application must be accessible via a custom domain like app.<your-domain>.

- SSL certificates should be issued by Let’s Encrypt, and HTTPS should be enforced.

- DNS should be automatically managed using externalDNS and updated in Route53.

## Deliverables

- Architecture Diagram: Create an architecture diagram illustrating your infrastructure setup. Use tools like Lucidchart, draw.io, or Mermaid.

- All infrastructure as code is done in Terraform and modules are created for reusable components. Either your own module or reuse existing community modules.

- Cluster and App Deployment: Ensure that your Kubernetes cluster and application are running smoothly, with traffic routing properly through the ingress and HTTPS enforced.

- Optional: Include an ArgoCD setup if implemented, showing how it automates your deployments.

## Useful links

- [Terraform AWS EKS](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eks_cluster)
- [Terraform Docs](https://www.terraform.io/docs/index.html)
- [Kubernetes Docs](https://kubernetes.io/docs/home/)
- [Helm Docs](https://helm.sh/docs/)
- [ArgoCD Docs](https://argo-cd.readthedocs.io/en/stable/)
- [Let's Encrypt](https://letsencrypt.org/getting-started/)
- [Cert Manager](https://cert-manager.io/docs/)
- [External DNS](https://external-dns.github.io/quickstart/)
