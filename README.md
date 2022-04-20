# Power Platform GCC DevOps Sample
This is a sample repository to show how to use GitHub Actions with the Power Platform in GCC. Full documentation on the Power Platform GitHub Actions can be found below,

https://github.com/microsoft/powerplatform-actions

Sample Power Platform GitHub Action examples can be found below,

https://github.com/microsoft/powerplatform-actions-lab/tree/main/sample-workflows

## Setting up your Power Platform Environment
1. You will need an O365 tenant with a Power Apps license
2. Create three Power Platform environments.  Save each environment URL for the GitHub setup.  You can get the environment URL from the Power Platform Admin Center
  * Development Environment
  * Build Environment
  * Production Environment
3. Create an Azure Active Directory (AAD) Application and create a secret credential to authenticate with
  * Save the client id, tenant id and app secret for the GitHub setup
4. In Power Platform Admin Center, add the AAD Application as an Application User and assign it a role for each environment you previously created

https://docs.microsoft.com/en-us/power-platform/admin/manage-application-users

## Setting up your GitHub Repository
1. Clone this repository
2. Create the following Action Secrets in your repository
  * ```AAD_CLIENT_ID```
  * ```AAD_TENANT_ID```
  * ```AAD_APP_SECRET```
  * ```DEV_ENVIRONMENT_URL```
  * ```BUILD_ENVIRONMENT_URL```
  * ```PROD_ENVIRONMENT_URL```

## Testing the Export Solution GitHub Action
1. Create a new solution file in the Development environment you created.
2. Update the ```export-hello-world-solution``` action to match the actual ```SOLUTION_NAME```
3. Run the GitHub Action to export the solution file into your GitHub repo
4. Submit a Pull Request to merge the branched unpacked solution file into your main branch

## Testing the Release Solution GitHub Action
1. Update the ```release-hello-world``` action to match the actual ```SOLUTION_NAME``` you want to publish
2. Create a new release in your repository
3. Watch the action complete
4. Go into your Power Platform Production environment and verify the solution was deployed
