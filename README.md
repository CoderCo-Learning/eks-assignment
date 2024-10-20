# CoderCo Assignment 2 - Cloud Native Adventures (Production Grade EKS Cluster with Ingress and SSL) 🚀

Your task is to create a production-grade Kubernetes (EKS) cluster on AWS, exposing applications securely with HTTPS. You’ll use key tools like Helm, NGINX Ingress Controller, cert-manager for managing SSL certificates, and externalDNS for syncing DNS records. Optionally, you may integrate ArgoCD for deployment automation.

## Task/Assignment 📝

- Create AWS Resources: Set up a VPC and an EKS cluster using infrastructure-as-code tools using Terraform. Ensure the cluster is ready for production with proper networking, security groups and correct node size configuration.

- Deploy Key Helm Charts:
  - Install NGINX Ingress Controller to manage ingress traffic.
  - Use cert-manager to automate SSL certificate issuance and renewal with Let’s Encrypt.
  - Set up externalDNS to automatically manage and update DNS records in Route53.

- Test Application Deployment: Deploy a sample application (e.g., a simple web app or even use the Threat Modeling Tool app we used in the previous assignment) and configure the ingress to expose it publicly via a custom domain. Ensure it is accessible over HTTPS.

- Security Setup:
  - Use Trivy to scan container images for vulnerabilities. (In your pipeline)
  - Use Checkov to scan your Terraform code for security misconfigurations and compliance violations. (In your pipeline)

- CICD Setup:
  - Use GitHub Actions to set up a CI/CD pipeline.
  - The pipeline should include steps for building, testing, and deploying your application.
  - It should also include steps for running security scans (Trivy) and Terraform code scans (Checkov).
  - Add pre-commit hooks for Terraform code scanning (Checkov)

- Integrate ArgoCD into the setup to automate your application deployment pipelines using GitOps principles.

### Bonus Tasks (Optional) 🎁

- Monitoring Setup:
  - Install Prometheus for collecting metrics from your Kubernetes cluster.
    - Set up Grafana for visualizing these metrics and creating dashboards to monitor cluster health and application performance.
    - Set up alerting in Prometheus/Grafana to notify you of any critical issues (e.g., high CPU/memory usage, pod failures). So if your app is down or any high CPU/memory usage is detected, you should be notified.
  - Create a Makefile for your project to manage your commands. Commands like `terraform plan`, `terraform apply`, `terraform destroy`, `make lint` etc.. Get creative and use Makefiles to your advantage.

## Requirements ✒️

- The application must be accessible via a custom domain like `app.<your-domain>.`

- SSL certificates should be issued by Let’s Encrypt, and HTTPS should be enforced.

- DNS should be automatically managed using externalDNS and updated in Route53.

- All Terraform code should be in the `terraform` folder. Organise code into modules etc.

- All Helm chart values should be in the `helm` folder.

- CI/CD:
- Pre-commit hooks must be configured to run security scans and code validation before code is committed.
- A Makefile should be provided to automate common tasks (e.g., Docker builds, scans, Terraform commands).

## Deliverables 📦

- Architecture Diagram: Create an architecture diagram illustrating your infrastructure setup, including monitoring, security, and CI/CD enhancements. Use tools like Lucidchart, draw.io, or Mermaid.

- Cluster, App, and Monitoring Deployment: Ensure that your Kubernetes cluster, application, and monitoring tools are running smoothly. HTTPS should be enforced, and monitoring dashboards should be available in Grafana.

- All infrastructure as code is done in Terraform and modules are created for reusable components. Either your own module or reuse existing community modules.

- CI/CD Setup: Provide a Makefile that automates tasks such as Docker builds, Trivy/Checkov scans, and Terraform commands. Ensure that pre-commit hooks are in place to run linting, validation, and security checks before code is committed.

- Optional: Include an ArgoCD setup if implemented, showing how it automates your deployments.

## Advice & Tips 💡

- Understand every single line of code you write and all concepts you implement. If you use chatGPT, understand what you are doing and if someone asks you to explain it, you should be able to explain it in your own words.
- Think of this like a real-world scenario. You are working on a team with a DevOps Engineer who will be deploying your code. You need to give them the tools to deploy your code.
- Use the `.env.example` file to set your AWS credentials as environment variables or use export in your terminal. Please add this to your .gitignore file if you use an `.env` file.
- Use the Makefile to automate your commands.

## Useful links 🔗

- [Terraform AWS EKS](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/eks_cluster)
- [Terraform Docs](https://www.terraform.io/docs/index.html)
- [Kubernetes Docs](https://kubernetes.io/docs/home/)
- [Helm Docs](https://helm.sh/docs/)
- [ArgoCD Docs](https://argo-cd.readthedocs.io/en/stable/)
- [Let's Encrypt](https://letsencrypt.org/getting-started/)
- [Cert Manager](https://cert-manager.io/docs/)
- [External DNS](https://external-dns.github.io/quickstart/)
- [Trivy](https://aquasecurity.github.io/trivy/v0.46/getting-started/installation/)
- [Checkov](https://www.checkov.io/2.Basics/Installing%20Checkov.html)
