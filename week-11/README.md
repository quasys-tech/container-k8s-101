Kubernetes Iac Security
--------------------

Helmchart
--------------------
Helm helps you manage Kubernetes applications — Helm Charts help you define, install, and upgrade even the most complex Kubernetes application.

Charts are easy to create, version, share, and publish — so start using Helm and stop the copy-and-paste.

https://helm.sh/

Iac Scanning with checkov
------------------------
Checkov scans cloud infrastructure configurations to find misconfigurations before they're deployed.

Checkov uses a common command line interface to manage and analyze infrastructure as code (IaC) scan results across platforms such as Terraform, CloudFormation, Kubernetes, Helm, ARM Templates and Serverless framework.

https://www.checkov.io/
https://github.com/bridgecrewio/checkov

    checkov -f Dockerfile
    bash -c 'find -iname chart.yaml' | xargs -n1 -I% bash -c " dirname %" | xargs -n1 -I% bash -c "helm template % > %.yaml && checkov -f %.yaml --framework kubernetes || true" --![image](https://github.com/user-attachments/assets/f144aeef-e507-44bc-bc4b-d7efcdb548bc)
