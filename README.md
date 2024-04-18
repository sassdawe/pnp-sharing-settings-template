# pnp-sharing-settings-template
Template pipeline for SharePoint Online sharing settings governance.

The purpose of this repository is to give you a template what you can just import into your **private** repostory, follow the step-by-step to update a couple of low complexity things and get started using GitHub Actions to enforce the sharing settings of your SharePoint Online tenant. 

## Risks to assess

The [PnP PowerShell Sharing Settings as Code](https://github.com/marketplace/actions/pnp-powershell-sharing-settings-as-code) GitHub Action requires SharePoint Online administrator access. The credentials required to execute this GitHub Action are considered super strong, in the wrong hands they can be used for bad things, really bad things.

Please make sure that only those can access and modify the repository where you implemented this action who are themselves SharePoint Administrators or have higher level access, for example Global Admins.

## Anatomy of this repository

These are the files in this repository

| file | description |
| ---- | ----------- |
| `readme.md` | This is the file we are currently reading with the details and steps, it can be updated |
| `.github/workflows/main.yml` | The GitHub Action file which will be responsible for all the work, **we need to update this** file. |
| `LICENSE` | A file to keep the lawyers happy, after creating a copy this can be deleted | 

## Prerequisites

- One (1) SharePoint Online tenant
- One Entra ID application registration
  - for using v3 of the pipeline we need to grant permissions in Entra ID
  - for using v2 or v1 we need to grant permissions in SharePoint Online for ACS authentication
- Certificate public key uploaded into Entra ID or Client Secret generated for the application
- Certificate private key uploaded into GitHub as a secret 

## Importing this repository

1. Navigate to [github.com/new/import](https://github.com/new/import) to create a new repository by importing this one
2. For **the URL for your source repository** past the git url of this one, which is: `https://github.com/sassdawe/pnp-sharing-settings-template.git`
3. Set the **Owner** make sure the right GitHub organization is selected
4. Give a **name** for your new repository, maybe `SharePointOnlineSharingSettingsAsCode`
5. Set the visibility to **private**
6. Click on **Begin import**

![image](https://github.com/sassdawe/pnp-sharing-settings-template/assets/10754765/1107b1a1-bfba-4b0a-aa3b-aecd379f2e3a)

## Updating the template

## Support for multiple Tenants

When we have multiple tenants, we just need to duplicate parts of the pipeline and repeate the other steps, except importing the template again. 
