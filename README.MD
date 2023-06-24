This script allows you to publish content from github directly to your webserver.

## Steps to do

1. Publish your website content to github repo
2. On you server [get an ssh key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
3. In your site repo go to **settings** -> **secrets and variables** -> **actions** -> **new repository secret**
4. Name your secret as a **DEPLOY_KEY**
5. If you want to have a telegram notifications also [create a telegram bot](https://medium.com/spidernitt/how-to-create-your-own-telegram-bot-63d1097999b6) *you don't need any code, just get a bot token*
6. Create a chat in telegram where you want to have your notifications and [get a chart id](https://splaitor.com/how-to-find-a-chat-id-in-telegram/) 
7. Save your tg bot id in **TG_TOKEN** secrets var and your chart id in **TG_CHAT**. Use point 3 of following to do list
8. Add your site ip to var **SITE_IP** and the site name to **SITE_NAME** the same as described above
9. Click **actions** -> **set up a workflow yourself** and add the code from this repo there

You need to setup this script just once, after that you will have auto pushing system in your repo.

## Features

- **Telegram notifications** - this script allows you to have notifications in your telegram chat with the status of push, the name of the repo, and the contributor's name. Also it provides the link to the action in case something went wrong to check the trace. If your want to disallow this feature just comment marked code.
- **Hugo website building** - This script is created for deploying [hugo websites](https://gohugo.io/) so if you don't need it comment marked code again.
- **Schedule posting** - for hugo site you may set the future date for the posts and setup schedule posting. It will start deploy according to the pointed time. If you don't need it comment marked code.
