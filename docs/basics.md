# The Basics
Village is a esoteric programming language.  
You are writing instructions for the highly forgetful village chief. The village chief can only understand certain actions.

## Syntax
The syntax of Village is really simple, if you keep in mind the fact that this is a list of instructions for the village chief.  
Each step in your instructions starts with a capital letter and usually ends with a period.  
### Lists
Some instructions, notably the 'Ask' instruction, require a section of indentation (in the form of a list) to immediately follow them.  
List indentation works like this:

| Indent level | What you use |
|:------------:|:-------------|
| 0 (program start) |  |
| 1 | <code>&nbsp;-</code> |
| 2 | <code>&nbsp;&nbsp;+</code> |
| 3 | <code>&nbsp;&nbsp;&nbsp;\*</code> |
| 4 | <code>&nbsp;&nbsp;&nbsp;&nbsp;-</code> |
| 5 | <code>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;+</code> |
| 6 | <code>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\*</code> |
| ...          | You get the pattern |

If you forget the order, the interpreter will remind you what to use. You're welcome. It's the *least* I could do.  
The chart above tells you what to do when the command documentation tells you to increase the indent level. As the indent level increases, you move down the chart.

## Villagers
Villagers are the heart and soul of your village. Villagers hold the following items (More information is available in villagers.md):
 - A scroll (used for output and writing text).
 - An occupation-related item.
