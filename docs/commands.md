# Commands
## Syntax Guide
I will be using the following rules for syntax. The rules are shortened forms of information found in [this](https://stackoverflow.com/a/23242584) StackOverflow answer.

|   What you see  |                      What to do                     |
|:---------------:|:---------------------------------------------------:|
| `<foo>`         | Replace with the appropriate information.           |
| `{foo\|bar\|baz}` | Choose exactly one of `foo`, `bar`, or `baz`.     |
| `[foo]`         | Optional argument, this can be omitted if you wish. |

## Control Flow
Control Flow instructions change how the program 'flows'.

### Skip
 - Syntax: `Skip to {line|step} <step number>.`  
 - This is a "jump" in your program.
 - Example: `Skip to step 10.`
### Ask
 - Syntax: `Ask <villager> if <query>.`
 - Requires an indented block to follow, this is a conditional.
 - The different queries are outlined below.
### Ask (cont'd)
 - Syntax: `Ask <villager> if {he|she} has {any|<number>} <item type>.`
 - Requires an indented block to follow, this is a conditional.
 - If the villager has at least `<number>` of the item specified, it skips to the `If {he|she} does:` in the indented block. Otherwise, it skips to the `If {he|she} doesn't:` in the indented block.
 - Example:
```
Ask Ada if she has any stone.
 - If she does:
 - Tell Ada to write the text 'I have stone' on her scroll.
 - If she doesn't:
 - Tell Ada to write the text `I do not have stone` on her scroll.
 ```
### Ask (cont'd)
 - Syntax: `Ask <villager> if [the text on]{his/her} scroll {starts with|ends with|contains} the text "<text>".`
 - Requires an indent block to follow, this is a conditional. Single quotes also work when surrounding the text. 
 - If the condition passes, it jumps to the `If it does:` in the indented block. Otherwise, it skips to the `If it doesn't:` in the indented block.
 - Example:
```
Ask Ada if the text on her scroll ends with the text 'Hello, World!'.
 - If it does:
 - Tell Ada to write the text ' Hello, World (again)!' on her scroll.
 - If it doesn't:
 - Tell Ada to write the text 'Hello, World!' on her scroll.
 ```
### Ask (cont'd)
 - Syntax: `Ask <villager> if {he|she} has {more|less} <item type> than <other villager>`
 - Requires an indent block to follow, this is a conditional.
 - If `<villager>` has more of `<item type>` than `<other villager>`, it skips to the `If {he|she} does:` in the indented block. Otherwise, it skips to the `If {he|she} doesn't:` in the indented block.
 - **WARNING!!!** If `<villager>` or `<other villager>` are builders, unexpected things can happen.

## Action Commands
These commmands preform an action by tell the villagers what to do.

### Call
 - Syntax: `Call the villager named <villager>.`
 - Grants you access to the villager named `<villager>`.
 - The villager doesn't have a set occupation, the occupation has to be defined using the `Teach` action command.
 - The villager name must be one of the following: (Male villagers prefer the pronoun 'he' and use the ownership pronoun 'his', female villagers prefer 'she' and 'her')
   - Male Villagers: (TO-DO: add more villager names!)
        - Alan
        - Bertrand
        - Charles
        - Dennis
        - Edsger
        - George
        - John
        - Ken
        - Linus
    - Female Villager(s): (TO-DO: add more villager names!):
        - Ada
### Teach
 - Syntax: `Teach <villager> how to <task>.`
 - This is how occupations are assigned to villagers.
 - Allowed tasks are:
   - Architect: `draft blueprints`
   - Builder: `build structures`
   - Farmer: `{cultivate|grow|harvest|farm} wheat`
   - Lumberjack: `{harvest|gather|collect} wood`
   - Quarryman: `{mine|quarry} stone`
