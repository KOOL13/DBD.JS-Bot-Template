# DBD.JS Bot Template

This repository contains everything on how to get started with a new dbd.js bot.
> You should have dbd.js installed. To do this, type `npm install dbd.js` into the terminal. (If you are using Glitch or Replit, it should automatically get installed.)


# How to Use

StackEdit stores your files in your browser, which means all your files are automatically saved locally and are accessible **offline!**

## Bot Token
Place your bot's token in the following spot:
```
const bot = new dbd.Bot({
	token: 'YOUR BOT TOKEN HERE',
	prefix: '!'
})
```
_____
Hiding your token:
1. Install the `dotenv` package (`npm install dotenv`)
2. Create a file named `.env`
3. Inside that file, put the following. Replace "YOUR TOKEN HERE" with your bot's token. (Do NOT use quotation marks)
```
token=YOUR TOKEN HERE
```
4. In your main file, put this for your token:
```
const bot = new dbd.Bot({
	token: process.env.token,
	prefix: '!'
})
```
> Note: If you are using Replit or Glitch, you don't need to install anything, just go to the env section and put your token.

## Bot Prefix

```
const bot = new dbd.Bot({
	token: '',
	prefix: [`$getServerVar[prefix]`,  '<@$clientID>',  '<@!$clientID>'],
})
```
This allows for mentioning the bot to work as a prefix too. To change the default prefix, go to index.js and find
```
bot.variables({
	prefix: 'YOUR PREFIX HERE'
})
```

## Bot Status
For A Single Status:
```
bot.status({
	status: 'online', // options: online (if want mobile status, check above), idle, dnd, invisible
	type: 'PLAYING', // options: WATCHING, PLAYING, LISTENING, COMPETING, STREAMING (if you choose streaming, you can also add the url: '' property)
	text: `on $serverCount servers` //Whatever text you want
})
```
For Multiple Statuses:
`time` is how long you want each status to switch for
```
bot.status({
	status: 'online',
	type: 'PLAYING',
	text: `on $serverCount servers`,
	time: 10
})

bot.status({
	status: 'online',
	type: 'WATCHING',
	text: `Im alive!`,
	time: 10
})
```
## Creating Commands

Inside of the `commands` folder, create a new file with any name (make sure you add .js at the end). Files can be located inside sub-folders as well if you want to stay organized. I will be making a ping command as an example.
```
module.exports = {
	name: 'ping', //Name = command name
	aliases: ['pong', 'botping'], // Aliases = Other names of the command
	code: `Pong! - $botPingms` //The actual code of the command
}
```


## Pre-Made Commands

I have already created a ping command and set-prefix command as a basis. Feel free to edit them or delete them if you wish.
