# 🚀 AWS S3 Static Website Hosting with Terraform + GitHub Actions CI/CD

This project started as a simple Terraform exercise but gradually became a practical DevOps workflow project.

The goal was to automate the deployment of a static website on AWS S3 using Terraform and then improve the workflow by integrating a simple CI/CD pipeline with GitHub Actions.

Instead of manually creating resources through the AWS Console, everything is provisioned and managed as code.

---

# 📌 What This Project Does

This project:

* Creates an AWS S3 bucket using Terraform
* Configures the bucket for static website hosting
* Uploads website files automatically
* Enables public access to the site
* Uses GitHub Actions for automated deployments

Whenever changes are pushed to GitHub, the CI/CD pipeline runs automatically.

---

# 🛠️ Technologies Used

* Terraform
* AWS S3
* GitHub Actions
* HTML/CSS
* Git & GitHub

---

# 📂 Project Structure

```bash id="h90m3k"
.
├── .github/
│   └── workflows/
│       └── terraform.yml
├── main.tf
├── provider.tf
├── variables.tf
├── outputs.tf
├── index.html
├── error.html
└── README.md
```

---

# ⚙️ Prerequisites

Before getting started, make sure you have:

* An AWS account
* Terraform installed
* AWS CLI configured
* Git installed
* A GitHub repository

---

# 🔐 Configure GitHub Secrets

To allow GitHub Actions authenticate with AWS, add the following repository secrets:

| Secret Name             | Description         |
| ----------------------- | ------------------- |
| `AWS_ACCESS_KEY_ID`     | Your AWS access key |
| `AWS_SECRET_ACCESS_KEY` | Your AWS secret key |

Navigate to:

```bash id="q83pmw"
Repository Settings → Secrets and Variables → Actions
```

Then add the secrets there.

---

# 🚀 How to Run the Project

## 1. Clone the Repository

```bash id="8f23bn"
git clone <your-repository-url>
cd <repository-name>
```

---

## 2. Initialize Terraform

```bash id="9l5mdp"
terraform init
```

This downloads the required Terraform providers.

---

## 3. Review the Execution Plan

```bash id="6e29lk"
terraform plan
```

This shows the resources Terraform intends to create.

---

## 4. Deploy the Infrastructure

```bash id="6vnh2s"
terraform apply
```

Type `yes` when prompted.

Once completed, your S3 bucket and static website configuration should be fully deployed.

---

# 🔄 CI/CD Pipeline

This project also includes a simple GitHub Actions workflow.

The workflow automatically:

* Initializes Terraform
* Validates the Terraform configuration
* Runs a Terraform plan
* Applies infrastructure changes on push

Workflow file location:

```bash id="rj2w14"
.github/workflows/terraform.yml
```

This removes the need to manually deploy infrastructure changes every time.

---

# 🌍 Accessing the Website

After deployment:

1. Open your AWS S3 Console
2. Navigate to the created bucket
3. Go to the **Properties** tab
4. Scroll down to **Static Website Hosting**
5. Open the generated website endpoint

Your website should now be live.

---

# 🧠 What I Learned

Working on this project helped me better understand:

* Infrastructure as Code (IaC)
* Terraform resource management
* AWS S3 static website hosting
* CI/CD automation with GitHub Actions
* Automating cloud deployments instead of using the AWS Console manually

---

# 🔮 Possible Improvements

Some future improvements I plan to add:

* CloudFront integration
* Custom domain setup with Route 53
* HTTPS with AWS Certificate Manager
* Remote Terraform backend configuration
* Terraform state locking

---

# 📸 Architecture Overview

```text id="qaqw2j"
Developer → GitHub → GitHub Actions → Terraform → AWS S3 → Static Website
```

---

# 👨‍💻 Author

Built as a hands-on DevOps project while learning Terraform, AWS, and CI/CD automation.
