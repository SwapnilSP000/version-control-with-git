# Jenkins Pipeline

This document explains a simple Jenkins Declarative Pipeline for learning CI/CD basics.

## Pipeline Stages

A beginner-friendly pipeline can include the following stages:

1. **Checkout**
2. **Build**
3. **Test**
4. **Deploy**

## Example Declarative Pipeline

```groovy
pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        echo 'Cloning repository...'
        git branch: 'dev', url: 'https://github.com/<username>/version-control-using-git.git'
      }
    }

    stage('Build') {
      steps {
        echo 'Simulating build stage...'
        echo 'Running build commands locally...'
      }
    }

    stage('Test') {
      steps {
        echo 'Simulating test stage...'
        echo 'Running unit tests and validation steps...'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Simulating deploy stage...'
        echo 'No real deployment, just a local workflow simulation.'
      }
    }
  }
}
```

## Notes

- This pipeline is educational and uses `echo` to simulate actions.
- The Checkout stage clones the Git repository and checks out a branch.
- The Build, Test, and Deploy stages help illustrate the CI/CD flow.
- No real build or deploy tools are needed for this learning example.
