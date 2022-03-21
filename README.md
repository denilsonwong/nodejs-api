# Currency Exchange API – NodeJS

docker run -d -p 8080:8080 u1ih/nodejs-api

curl -i http://localhost:8080/fx

CI/CD pipeline implemented using GitHub Actions:

* create docker container
* push to gcr.io container registry
* deploy to Google Cloud Run (knative / PaaS)

Live endpoint available at: [https://nodejsapi-tgihgzgplq-uc.a.run.app/](https://nodejsapi-tgihgzgplq-uc.a.run.app/)

[https://nodejsapi-tgihgzgplq-uc.a.run.app/fx](https://nodejsapi-tgihgzgplq-uc.a.run.app/fx)


The CI/CD build workflow needs documentation. For now, here is how you connect it to GCP: [https://gcp-examquestions.com/ci-cd-solutions-deploy-to-google-cloud-run-using-github-actions/](https://gcp-examquestions.com/ci-cd-solutions-deploy-to-google-cloud-run-using-github-actions/)

In order for this to be provisioned on your Google Cloud instance, you need to make sure you create/update these GitHub secrets:

* GCP_APPLICATION
* GCP_CREDENTIALS
* GCP_EMAIL
* GCP_PROJECT

You'll also need to activate a couple of APIs in Google Cloud, the first deployment will probably fail and point you into the right direction. Alternatively, you could deploy the first version manually.

#New try#

Deploy To Google Cloud Run Using Github Actions by follow the instruction from the website below: 
https://towardsdatascience.com/deploy-to-google-cloud-run-using-github-actions-590ecf957af0

Issue encountered and yet to solve: 
No credentials detected, skipping authentication
Error: google-github-actions/setup-gcloud failed with: no credentials provided to export

*Found that the error could be from updated the secrets at dependabot secret section. (didn't understand the difference between action and dependabot secrets)
*From that, created an environment with name Configure deploy to google cloud platform and added the secrets accordingly, but still the same error occurred.

Getting updates from GitHub via Telegram Bot by taking the reference from the website below:
https://cyaninfinite.com/getting-updates-from-github-via-telegram-bot/

https://medium.com/cocoaacademymag/how-to-integrate-github-actions-with-slack-telegram-and-whatsapp-67a4dca0f17d

*realised that it didn't work (loading for infinte period of time) as i changed the code (appleboy/telegram-action@master) to (denilsonwong/nodejs-api@master)
*changed it back to the original code, didn't work still with error: 2022/03/21 01:28:58 missing telegram token or user list
*tried it with my other repo, https://github.com/denilsonwong/backend-sample ; managed to run it successfully.



