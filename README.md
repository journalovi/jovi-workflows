# Github workflows and templates for the JoVI experimental track

This repository contains Github workflows and templates for the [JoVI "Experimental" (Github) Track](https://www.journalovi.org/submit.html#experimental).

Issue templates in this repository (under `.github/ISSUE_TEMPLATE`) are automatically copied to any repository within the `journalovi` organization that has the `article` topic applied to it.

## Setting up the workflows

The `copy_templates.yml` workflow in this repository requires commit access to repositories in the `journalovi` Github organization. This is enabled by creating an access token with the necessary permissions. The token must be created by someone with the necessary permissions on the `journalovi` organization. This token is stored in a secret called `JOVI_COMMIT_TOKEN`.

Should this token need to be re-generated, here are the steps to do so:

1. A member of the `journalovi` Github organization with commit access to all `journalovi` repos must generate a "Fine-grained Personal Access Token" for the `journalovi` organization:
   1. Click on your profile icon and go to [Settings -> Developer Settings -> Personal Access Tokens](https://github.com/settings/tokens)
   2. Click on "Fine-grained tokens"
   3. Click "Generate New Token"
   4. Give it the name `JOVI_COMMIT_TOKEN` and a description like "Commit access token for JOVI repos"
   5. Pick a suitable expiration date (e.g. a year in the future)
   6. Set **Resource Owner** to `journalovi`
   7. Set **Repository access** to `All repositories`
   8. Under **Repository Permissions**, set the following to **Read and Write**:
      - Actions
      - Commit statuses
      - Contents
      - Pull requests
      - Workflows
   9. **Leave this window open**
2. On the `journalovi/workflows` repository, go to [Settings -> Secrets and variables -> Actions](https://github.com/journalovi/jovi-workflows/settings/secrets/actions)
   1. Under **Repository Secrets**, click **New Repository Secret**.
   2. Name the secret `JOVI_COMMIT_TOKEN` and copy and paste the contents of the Personal Access token you created above into it.

