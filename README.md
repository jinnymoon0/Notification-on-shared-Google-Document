# Notification-on-shared-Google-Document
This will give you notification when the owner or an editor opens a shared google document.
1) First, install telegram, and add @BotFather
2) Then, type /start.
3) Now, you can choose to type /newbot or click the link from the message the bot sent.
4) Create a name for your bot, enter, and then choose a username.
5) After you entered both, you will get a token to access the HTTP API. Remember to SAVE THIS.
6) Click on the link from the same message you received the token (that is your new bot).
7) Start the conversation with the bot by typing /start, and send any message such as Hi. 
8) In your browser, type: https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getUpdates
9) You will see a JSON file looking something like this:
{
  "ok": true,
  "result": [
    {
      "update_id": 123456789,
      "message": {
        "message_id": 1,
        "from": {
          "id": 987654321,
          "is_bot": false,
          "first_name": "sam"
        },
        "chat": {
          "id": 987654321,
          "first_name": "sam",
          "type": "private"
        },
        "date": 1720000000,
        "text": "hi"
      }
    }
  ]
}
10) find the chat id (in this example, would be 987654321. remember to also SAVE THIS
11) Go to google document that you would like to implement this, and click "Extensions" and "App Script"
12) In the left side, click on "Project Settings" and add TELEGRAM_BOT with value <YOUR_BOT TOKEN> (that you saved from step 5), and also all a new property named CHAT_ID with value you saved from step 9.
13) Go back to the left hand side and go to editor.
14) Paste the code from "notification code" 
15) Save and choose "pingMe" from the function dropdown next to Run.
16) Run and check if you have received a notification from your bot.
17) Now, you will receive a notification whenever an owner or an editor opens the shared document. 

