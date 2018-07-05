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
 <to-do>
