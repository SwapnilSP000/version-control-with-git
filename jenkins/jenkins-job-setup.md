# Jenkins Job Setup

This file details how to configure a Jenkins job integration that connects to a remote GitHub repository.

## Open Jenkins

1. Open your browser and navigate to:
   ```text
   http://localhost:8080
   ```
2. Log in with your Jenkins credentials.

## Create a New Job

1. Click `New Item` in the Jenkins dashboard.
2. Enter a name such as `version-control-with-git-pipeline`.
3. Select `Freestyle project` or `Pipeline`.
4. Click `OK`.

## Connect the GitHub Repository

1. In the job configuration, locate the `Source Code Management` section.
2. Select `Git`.
3. Enter the repository URL:
   ```text
   https://github.com/<username>/version-control-with-git.git
   ```
4. Set the branch specifier to `main` or `dev` depending on the target branch configuration.

## Build Triggers

1. Navigate to the `Build Triggers` section.
2. For initial automation, configure `Build periodically` or leave it disabled to trigger manual builds.
3. If integrating webhook notifications, enable `GitHub hook trigger for GITScm polling`.

## Build Steps

1. Add a `Build step`.
2. Select `Execute shell` or `Windows batch command` depending on your environment platform.
3. Use echo statements to validate execution logic:

```bash
echo "Source code checkout completed successfully."
echo "Executing project build tasks..."
echo "Running automated verification tests..."
echo "Simulating application deployment workflow..."
```

## Trigger the Build Manually

1. Save the job configuration.
2. Open the job details page.
3. Click `Build Now`.

## View Build Execution Logs

1. On the job details page, identify the build number under the `Build History` panel.
2. Click the build number.
3. Click `Console Output` to inspect execution logs and verify build status.

## Summary

This configuration demonstrates the integration of Jenkins with a remote GitHub repository, validating how builds are orchestrated to implement continuous integration.
