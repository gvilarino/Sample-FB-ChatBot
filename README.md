# hodor-bot-fb
Simple chat bot server for the [Hodor Bot](https://www.facebook.com/bothodor/) Facebook application. Based on [Sample-FB-ChatBot](https://github.com/PahanPerera/Sample-FB-ChatBot).

## Usage
```sh
$ npm i
$ npm start
```

## Configuration
You'll need to set up the `FB_TOKEN` environment variable with the app access token provided by Facebook in your app settings dashboard.

## Facebook setup

#### Step 1 - Setting up the chat bot server
- Clone this repo
```sh
$ git clone https://github.com/gvilarino/hodor-bot-fb.git
```
 - Install NodeJs dependencies
```sh
$ cd Sample-FB-ChatBot
$ npm install
```
 - Run server
```sh
$ npm start
```
If you are seeing "Example app listening on port 3010!", your server has been started successfully.
- Stop the server for now

#### Step 2 - Setting up the Facebook Application
- Create Facebook App and Page ([link](https://developers.facebook.com/docs/messenger-platform/implementation#create_app_page))
- Get Page access token ([link](https://developers.facebook.com/docs/messenger-platform/implementation#page_access_token)
(Save this the next step)

#### Step 3 - Setting up Token in the server and prepare webhook
- Set this to your `FB_TOKEN` env variable
- Start the server
- Since Facebook only accept public https URLs as their webhooks, we need to expose our local server endpoints as public https. Quick way to do that is use https://localtunnel.me/
- Create a https public endpoint using https://localtunnel.me/ (Please make sure you disable your firewalls)
```sh
$ npm install -g localtunnel
```
- Tunnel our local server port
```sh
- lt --port 3010
```
- You will get something like https://something.localtunnel.me which is your public base URL
- If you goto https://something.localtunnel.me/webhook in your web browser you will get a message saying "Error, wrong validation token"
- Once this is done goto https://developers.facebook.com/docs/messenger-platform/implementation#setup_webhook and setup the webhook that we just created in the Facebook Application

#### Step 4 - Subscribe Facebook App and Page
- Subscribe your application with your page ([link](https://developers.facebook.com/docs/messenger-platform/implementation#subscribe_app_pages)

#### Step 5 - Done
- Now goto your Facebook page and send it a chat message, it will echo back the text you send.

### Notice

Keep in mind that only app admins, developers and testers will be able to see the bot's anwsers until the app is public and approved by Facebook.
