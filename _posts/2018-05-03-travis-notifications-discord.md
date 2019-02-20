---
layout: post
title: "How to setup Travis CI notifications on Discord"
date:   2018-05-03
tags:
  - continuous integration
  - devops
---

As of May 2018, Travis-CI does not support Discord Webhooks in their notifications.

Nevertheless, there are open-source tools that can help achieve these notifications. The one I used for my project was k3rn31p4nic's travis-ci-discord-webhook script. I slightly modified the script to accommodate my needs; I added Travis-CI build stages support. First, let's set-up the notifications using the k3rn31p4nic's guide.

k3rn31p4nic's Guide:

1. Create a webhook in your Discord Server (Guide).

2.  Copy the Webhook URL.

3.  Go to your repository settings (for which you want status notifications) in Travis CI and add an environment variable called WEBHOOK_URL and paste the Webhook URL you got in the previous step.

4.  Add these lines to the `.travis.yml` file of your repository.

```sh
after_success:
- wget https://raw.githubusercontent.com/k3rn31p4nic/travis-ci-discord-webhook/master/send.sh
- chmod +x send.sh
- ./send.sh success $WEBHOOK_URL
after_failure:
- wget https://raw.githubusercontent.com/k3rn31p4nic/travis-ci-discord-webhook/master/send.sh
- chmod +x send.sh
- ./send.sh failure $WEBHOOK_URL
```

Once the steps above are completed, the Discord notifications should work. If you want to add Travis-CI build stages to your notifications, like for example to notify which build stage failed, you can do this by using the Travis job number and creating a BUILD_STAGE variable. You can place the following code snippet in your script and add your custom build stages.

```sh
if [ "${TRAVIS_JOB_NUMBER: -1}" == 1 ]; then
  BUILD_STAGE="Compilation"
elif [ "${TRAVIS_JOB_NUMBER: -1}" == 2 ]; then
  BUILD_STAGE="Unit tests"
else
  BUILD_STAGE="UI tests"
fi
```
Finally, you can use the build stage variable in the notifications. However, this technique only
 works if the build stages are non-parallel.