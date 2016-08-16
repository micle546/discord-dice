# Discord-Dice-Roller-Bot
A bot that handles most RPG dice rolls - almost entirely stolen from https://github.com/Chaithi/Discord-Dice-Roller-Bot - fixed to use the newer version of discord.py and work with tokens rather thsn username + passwords aaand also run under Heroku.

# Dependencies
This bot is extended from [Discord.py] (https://github.com/Rapptz/discord.py/). Install Discord.py prior to running this bot.

#Python Version
This requires Python 3.5+:

# Usage
1. Create a Discord application + bot user, get its token and add it as the value of a config variable(/environment variable) called ```DISCORD_TOKEN``` in Heroku
2. Take the client ID and insert it into this link: https://discordapp.com/oauth2/authorize?client_id=[CLIENT ID HERE]&scope=bot&permissions=0 - This link will let you add the bot to your server, or let others do the same
3. Launch script

# Commands
`!roll`
Supported rolls are:
- !roll 100 - Rolls from 1-100
- !roll 50-100 - Rolls from 50-100
- !roll 3d6 - Rolls 3 6-sided die

#Modifiers
- `!` Success marker. Used with 3d6 type rolls. !roll 10d6!5 will give you the number of times the dice rolls 5 or higher.
- `>` Success marker. Used with 100, 50-100, 3d6 type rolls. !roll 100>50 will say "Success" if result is over 50 or "Failure" if not.
- `mod` Modifier. Used with any roll. Adds or subtracts from the roll. !roll 100mod4 will add 4 to the roll.

You can string these together:
- `!roll 100>40mod-3` would choose a number between 1-100, subtract 3, then let you know if it was over 40.
- `!roll 10d6!4mod2>3` would roll 10 d6, count number of dice rolled that are 4+, add 2 to that number, and let you know if that number was over 3.
