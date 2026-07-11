# Jenkins Job Setup

This file explains how to create a simple Jenkins job that connects to a GitHub repository.

## Open Jenkins

1. Open your browser and go to:
   ```text
   http://localhost:8080
   ```
2. Log in with your Jenkins credentials.

## Create a New Job

1. Click `New Item` in the Jenkins dashboard.
2. Enter a name such as `version-control-using-git-ci`.
3. Select `Freestyle project`.
4. Click `OK`.

## Connect the GitHub Repository

1. In the job configuration, find the `Source Code Management` section.
2. Select `Git`.
3. Enter the repository URL:
   ```text
   https://github.com/<username>/version-control-using-git.git
   ```
4. Set the branch specifier to `main` or `dev` depending on the workflow.

## Build Triggers

1. Scroll to `Build Triggers`.
2. For a beginner-friendly setup, enable `Build periodically` or leave it off to trigger manually.
3. If using GitHub integration later, this is where you can enable webhooks.

## Build Steps

1. Add a `Build step`.
2. Choose `Execute shell` or `Windows batch command` depending on your platform.
3. Use simple echo commands to simulate pipeline steps:

```bash
echo "Checkout complete"
echo "Build simulation"
echo "Test simulation"
echo "Deploy simulation"
```

## Trigger the Build Manually

1. Save the job configuration.
2. Open the job page.
3. Click `Build Now`.

## View Console Output

1. On the job page, find the build number in the `Build History`.
2. Click the build entry.
3. Click `Console Output` to review the job execution logs.

## Summary

This setup is intentionally simple to demonstrate how Jenkins can be connected to a GitHub repository and how builds can be triggered manually for learning CI/CD concepts.
