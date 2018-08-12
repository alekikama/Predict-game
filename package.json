var TelegramBot = require( "node-telegram-bot-api" );
var bot = new TelegramBot( "693072764:AAGSPZgV9W-0eNwGUqx_rPTaLdJeN_ceAE0", { polling: true } );
bot.onText( /\/start/, function( msg ) {

  bot.sendMessage(

      msg.from.id,

      "Hi <b>" + msg.from.first_name + "</> " + msg.from.last_name + "\nLets play Valga game!",

      {

          parse_mode: "HTML"

     }

  );

} );
bot.onText( /\/play (.+)/, function( msg, match ) {

  var fromId = msg.from.id;

  switch( match[1] ) {

      case "TestGame":

          bot.sendGame(

              fromId,

              "TestGame",

              {

                  reply_markup: JSON.stringify({

                      inline_keyboard: [

                          [ { text: "Play", callback_game: JSON.stringify( { Valga: "TestGame" } ) } ],

                          [ { text: "Share", url: "https://t.me/Valga_bot?game=Valga" } ]

                      ]

                  })

              }

          );

          break;

      default:

          bot.sendMessage( fromId, "Sorry " + msg.from.first_name + ", but this game doesn’t exist.." );

  }

} );
bot.on( "callback_query", function( cq ) {

  if ( cq.Valga ) {

      switch( cq.Valga ) {

          case "TestGame":

              bot.answerCallbackQuery( cq.id, undefined, false, { url: "https://tryfdyrgtzbgqnv9wsbdwq-on.drv.tw/Telegram%20game/telegram%202.html" } );

              return;

      }

      bot.answerCallbackQuery( cq.id, "Sorry, '" + cq.Valga + "' is not available.", true );

  }

} );
bot.on( "inline_query", function( iq ) {

  bot.answerInlineQuery( iq.id, [ { type: "game", id: "0", Valga: "TestGame" } ] );

} );
