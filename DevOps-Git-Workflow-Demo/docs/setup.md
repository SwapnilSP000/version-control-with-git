# Setup

## Installing Git

Install Git for your operating system from the official site:

- https://git-scm.com/downloads

Verify the installation:

```bash
git --version
```

## Configuring Git

Set your user name and email globally:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Confirm the configuration:

```bash
git config --list
```

## Clone Repository

Clone the repository to your local machine:

```bash
git clone https://github.com/<username>/DevOps-Git-Workflow-Demo.git
cd DevOps-Git-Workflow-Demo
```

## Initial Commit

If you start a new repository locally, create the initial commit:

```bash
git init
git add .
git commit -m "chore: initial project structure"
```

## Push Repository

Add the remote and push the repository:

```bash
git remote add origin https://github.com/<username>/DevOps-Git-Workflow-Demo.git
git branch -M main
git push -u origin main
```
