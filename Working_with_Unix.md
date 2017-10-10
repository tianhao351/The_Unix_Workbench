## Work With Unix

### 1.self-help

- Each of the commands that we’ve discussed so far are thoroughly documented, and you can view their documentation using the man command
- After typing man ls to open the page, type / in order to start a search
- Press the n key in order to search for the next occurrence of the word, and if you want to go to the previous occurrence type Shift + n. This method of searching also works with less. When you’re finished looking at a man page type q to get back to the prompt.
- The man command works wonderfully when you know which command you want to look up, but what if you’ve forgotten the name of the command you’re looking for? You can use apropos to search all of the available commands and their descriptions. 





### 2.Get wild

- Wildcards can represent many kinds and numbers of characters.
- The star wildcard (*) represents zero or more of any character.
- You can use wildcards on the command line in order to work with multiple files and folders.





### 3.Search







### 4.configure

#### 4.1history

- Bash keeps track of all of your recent commands, and you can browse your command history two different ways. The commands that we’ve used since opening our terminal can be accessed via the ***history*** command
- The command history has been storaged in ~/.bash_history. So we can use head or grep to look for in there.



#### 4.2 customizing bash

- alias creates a command that can be used as a substitute for a longer command that we use often.
- The ~/.bash_profile is a text file that is run every time we start a shell, and it’s the best place to assign aliases.

  







