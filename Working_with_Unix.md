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





### 3.Search and Regular Expressions

#### 3.1 grep

- One of the most popular tools for searching through text files is grep. The simplest use of grep requires two arguments: a regular expression and a text file to search. Let’s see a simple example of grep in action and then I’ll explain how it works:

```shell
grep "x" states.txt
```

#### 3.2 metacharacters and egrep

-  metacharacters are characters that can be used to represent other characters

- To take full advantage of all of the metacharacters we should use grep’s cousin egrep, which just extends grep’s capabilities

-  "." (period) metacharacter represents *any* character.

  ```shell
  egrep "i.g" states.txt

  ## Virginia
  ## Washington
  ## West Virginia
  ## Wyoming
  ```

- "+" (plus) represents one or more occurrences of the preceeding expression.

  ```shell
  egrep "s+as" states.txt

  ## Arkansas
  ## Kansas
  ## kasssas
  ```

- " * " (star) metacharacter which represents zero or more occurrences of the preceding expression.

  ```shell
  egrep "s*as" states.txt

  ## Alaska
  ## Arkansas
  ## Kansas
  ## Massachusetts
  ## Nebraska
  ## Texas
  ## Washington
  ```

- ou can use curly brackets ({ }) to specify an exact number of occurrences of an expression. For example the regular expression "s{2}" specifies exactly two occurrences of the character “s”. 

  ```shell
  egrep "s{2}" states.txt

  ## Massachusetts
  ## Mississippi
  ## Missouri
  ## Tennessee

  ```

- We could also search for state names that have between two and three adjacent occurrences of the letter “s” with the regular expression "s{2,3}":

  ```shell
  egrep "d{2,3}d" states.txt

  ## dssd
  ## dsssd
  ```

  ​

#### 3.3character sets

- The \w metacharacter corresponds to all “word” characters, the \d metacharacter corresponds to all “number” characters, and the \s metacharacter corresponds to all “space” characters

- the \w metacharacter matches all letters, numbers, and even the underscore character (_). 

- The -v flag (which stands for invert match) makes grep return all of the lines not matched by the regular expression. Note that the character sets for regular expressions also have their inverse sets: \W for non-words, \D for non-digits, and \S for non-spaces. Let’s take a look at using \W:

- we can also create specific character sets using square brackets ([ ]) and then including the characters we wish to match in the square brackets

- You can also create a regular expression for the compliment of a set by including a caret (^) in the beginning of a set

- If you want to specify a range of characters you can use a hyphen (-) inside of the square brackets

  ```shell
  egrep "[e-q]" small.txt

  ## abcdefghijklmnopqrstuvwxyz
  ## rhythms
  ## tragedy + time = humor
  ## http://www.jhsph.edu/

  egrep "[E-Q]" small.txt

  ## ABCDEFGHIJKLMNOPQRSTUVWXYZ

  egrep "[e-qE-Q]" small.txt

  ## abcdefghijklmnopqrstuvwxyz
  ## ABCDEFGHIJKLMNOPQRSTUVWXYZ
  ## rhythms
  ## tragedy + time = humor
  ## http://www.jhsph.edu/
  ```

- the caret (^), which represents the start of a line, and the dollar sign ($) which represents the end of line.

  ```shell
  egrep "^M" states.txt

  ## Maine
  ## Maryland
  ## Massachusetts

  ```

- “or” metacharacter (|)

  ```shell
  egrep "North|South|East|West" states.txt

  ## North Carolina
  ## North Dakota
  ## South Carolina
  ## South Dakota
  ## West Virginia
  ```

- you can display the line number that a match occurs on using the -n flag:

  ```shell
  egrep -n "t$" states.txt

  ## 7:Connecticut
  ## 45:Vermont
  ```

- you can grep multiple files at once by providing multiple file arguments:

  ```shell
  egrep "New" states.txt canada.txt

  ## states.txt:New Hampshire
  ## states.txt:New Jersey
  ```

- find can be used to search for the names of files in a directory.

### 4.configure

#### 4.1history

- Bash keeps track of all of your recent commands, and you can browse your command history two different ways. The commands that we’ve used since opening our terminal can be accessed via the ***history*** command
- The command history has been storaged in ~/.bash_history. So we can use head or grep to look for in there.



#### 4.2 customizing bash

- alias creates a command that can be used as a substitute for a longer command that we use often.
- The ~/.bash_profile is a text file that is run every time we start a shell, and it’s the best place to assign aliases.

  

### 5.differentiate

- The md5 and shasum commands use different algorithms to create codes (called hashes or checksums) that are unique to the contents of a file.
- These hashes can be used to ensure that a file is genuine.



### 6.pip

- he pipe allows us to take the output of a command, which would normally be printed to the console, and use it as the input to another command.

  ```bash
  ls -al | grep "Feb" | less
  ```

  ```bash
  grep "[aeiou]$" states.txt | wc -l
  ```

  ​

### 7.Make

- make is a tool for creating relationships between files and programs, so that files that depend on other files can be automatically rebuilt.
- makefiles are text files that contain a list of rules.
- Rules are made up of targets (files to be built), commands (a list of bash commands that build the target), and dependencies (files that the target depends on to be built).





