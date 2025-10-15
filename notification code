  function onOpenHandler(e) {
  const props = PropertiesService.getScriptProperties();
  const BOT   = (props.getProperty('TELEGRAM_BOT') || '').trim();
  const CHAT  = (props.getProperty('CHAT_ID') || '').trim();

  const email = Session.getActiveUser().getEmail() || 'unknown';
  const title = DocumentApp.getActiveDocument().getName();
  const ts    = new Date().toISOString().replace('T',' ').replace('Z',' UTC');

  const text  = `✳️ Doc opened by editor\n• Title: ${title}\n• By: ${email}\n• Time: ${ts}`;

  const url = `https://api.telegram.org/bot${BOT}/sendMessage`;
  const res = UrlFetchApp.fetch(url, {
    method: 'post',
    payload: { chat_id: CHAT, text },
    muteHttpExceptions: true
  });
  Logger.log(res.getResponseCode() + ' ' + res.getContentText());
}

// Run this ONCE to create an installable onOpen trigger that runs as YOU
function _installTrigger() {
  ScriptApp.newTrigger('onOpenHandler')
    .forDocument(DocumentApp.getActiveDocument().getId())
    .onOpen()
    .create();
}

// Quick test to verify your token + chat_id
function pingMe() {
  const props = PropertiesService.getScriptProperties();
  const BOT   = (props.getProperty('TELEGRAM_BOT') || '').trim();
  const CHAT  = (props.getProperty('CHAT_ID') || '').trim();
  const url   = `https://api.telegram.org/bot${BOT}/sendMessage`;

  const res = UrlFetchApp.fetch(url, {
    method: 'post',
    payload: { chat_id: CHAT, text: '✅ Test from Apps Script' },
    muteHttpExceptions: true
  });
  Logger.log(res.getResponseCode() + ' ' + res.getContentText());
}

