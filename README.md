

# RSS to Telegram bot
A self-hosted telegram python bot that dumps posts from RSS feeds to a telegram chat. This script was created because all the third party services were unreliable. 

This fork adds support for parsing ss.com advert pages

## Quick setup for ss.com apartment feed:
0. Open telegramRSSbot.py in a text editor and add your bot credentials from BotFather on telegram, chat ID (message @get_id_bot to get your ID) and min/max price for filtering if needed
1. Go to the apartment listings and select city, region and type "Izīrē"
2. Scroll to the bottom and find the RSS link
3. Copy the url
4. Start the bot using `python3 telegramRSSbot.py`
5. Send /add **\<feed name\>** **\<RSS url that you've just copied\>**

![Image of help menu](https://bokker.github.io/telegram.png)

### Docker
**Docker image is unchanged from the original!**

For the docker image go to: https://hub.docker.com/r/bokker/rss.to.telegram/

### Installation
Python 3.X
```sh 
pip install feedparser
pip install python-telegram-bot
```

A telegram bot is needed that the script will connect to. https://botsfortelegram.com/project/the-bot-father/
The chatid is required for the bot to know where to post the RSS feeds. https://stackoverflow.com/questions/32423837/telegram-bot-how-to-get-a-group-chat-id

1. Clone the script
2. Replace your chatID and Token on the top of the script.
3. Edit the delay. (seconds)
4. Save and run
5. Use the telegram commands to manage feeds 

# Usage
send /help to the bot to get this message: 

>RSS to Telegram bot

>After successfully adding a RSS link, the bot starts fetching the feed every 60 seconds. (This can be set) ⏰⏰⏰
>Titles are used to easily manage RSS feeds and need to contain only one word 📝📝📝

>commands:

>**/add** title http://www(.)URL(.)com

>**/help** Shows this text 

>**/remove** !Title! removes the RSS link

>**/list** Lists all the titles and the RSS links from the DB

>**/test** Inbuilt command that fetches a post from Reddits RSS.


# Known issues
 If the bot is set to for example 5 minutes and one feed manages to get 2 new posts before the bot can check. Only the newest post will show up on telegram.
