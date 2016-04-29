# Poll Plugin
by Patrick Conrad (SuNflOw1991)

## How it works:
Moderators and the Broadcaster are able to create polls. You can manage them like start, list, delete, abort and reset. Polls once created can not be changed afterwards because the command syntax would be to complex. But you can create as many polls as you want. You can execute all commands directly to the bot via whisper chat or via public chat. There is only one exception: The start command. This can only be executed via public chat because the bot has to know where to send the message in which he tells the users to vote.  
Let's take a deeper look how it works:

### Create a poll
First you have to create at least one poll. This can be made with a title (which is in general a question) or without. To create a poll with title use this syntax:
```
!poll create(TITLE) OPT1|OPT2|...
```
To create a simpler poll without a title:
```
!poll create OPT1|OPT2|...
```
As you can see you can add as many options as you want. You have to separate them with the pipe character `|`.  
The bot will answer to you with an id. You need this id to work with this poll.

### List all polls
If you don't remember which polls you have created you can get a list with created polls with:
```
!poll list
```
This will give you a list with all polls their ids and options and you can see in which state the poll is.

### The poll states
A poll can have one of four different states:
* Created - The poll is created and you can start the poll
* Started - The poll is started and can be aborted
* Aborted - The poll is aborted and you can reset, delete or restart the poll
* Finished - The poll is finished and you can restart, delete and reset the poll. Also you can request the results.

### Start a poll
If you want to start a poll you need the poll id and you can tell the bot how long the users can vote.  
To start the poll with id 1 for 2 minutes type:
```
!poll start:1 2
```
If you don't specify the time parameter the poll we be opened for votes for 5 minutes.  
To start the poll with id 1 for 5 minutes type:
```
!poll start:1
```

### Abort a poll
May you want to abort a poll.
To abort the poll with id 1 type:
```
!poll abort:1
```
The poll is now in aborted state. To restart this poll use the restart command or reset the poll and start it later. There are no results available for aborted polls.

### Restart a poll
Once you have aborted a poll you need to run the restart or reset followed by start command to reuse this poll. The restart command let you specify the time parameter. Of course, this command can also be used for finished polls to restart them.
To restart poll with id 1 for 2 minutes type:
```
!poll restart:1 2
```
To restart poll with id 1 for 5 minutes type:
```
!poll restart:1
```

### Reset a poll
If a poll is aborted or finished and you want to restart it you can use the reset command to reset the poll to created state. This makes sense for finished polls that needs to be started later but the results should not longer be available.
To reset the poll with id 1 type:
```
!poll reset:1
```

### Delete a poll
If you did a mistake or you not longer need a poll you can delete it with:
```
!poll delete:1
```

### Get results & detailed information
Once a poll has been finished successfully the bot will print which option has the most votes and how many percent that was. If you want to get a list of how many votes the other options got, you can use the result command.
To get detailed information about poll 1 type:
```
!poll result:1
```

## Change List:
`2016.04.29` - First release