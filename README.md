# semicolon
An esoteric language made up of only semicolons.

**You can't escape the semicolon monster!**

## Installation

Install semicolon globally from npm registry by typing the following command

```
npm install semicolon -g
```

## Usage

```
Usage: semicolon [FILE]
```

The following program consists semicolons, reversed semicolons, spaces and newlines which when ran

```
;;;;⁏;;⁏;;;
⁏ ;;;;;;⁏⁏;;⁏;⁏
⁏ ;;;;;;⁏⁏;⁏⁏;;
;;⁏⁏ ;;⁏ ;;;;;;⁏⁏;⁏⁏⁏⁏
⁏ ;;;;;;⁏;;;;;
⁏ ;;;;;;⁏⁏⁏;⁏⁏⁏
⁏ ;;;;;;⁏⁏;⁏⁏⁏⁏
;;⁏⁏ ;;;;;;⁏⁏
⁏;;⁏ ;;;;;;⁏⁏;⁏⁏;;
⁏ ;;;;;;⁏⁏;;⁏;;
⁏ ;;;;;;⁏;;;;⁏
⁏ ;;;;;;;⁏;⁏;
⁏ ;;  ;
```

gives the following output

```
Hello world!
```

*NOTE: space will be denoted by `s` below because of some github markdown error*

## Instructions

The virtual machine on which programs run has a stack and a heap. The programmer is free to push arbitrary width integers onto the stack (only integers, currently there is no implementation of floating point or real numbers). The heap can also be accessed by the user as a permanent store of variables and data structures.

Many commands require numbers or labels as parameters. Numbers can be any number of bits wide, and are simply represented as a series of `;` and `⁏`, terminated by a `\n`. `;` represents the binary digit 0, `⁏` represents 1. The sign of a number is given by its first character, `;` for positive and `⁏` for negative. Note that this is not twos complement, it just indicates a sign.

Labels are simply `\n` terminated lists of `;` and `⁏`. There is only one global namespace so all labels must be unique.

### Stack manipulation

All stack manipulations start with `;` and followed by

* `;;` - Push a signed integer into the stack (*param:* number)
* `;⁏` - Duplicate the top item of the stack
* `⁏;` - Swap the top two items of the stack
* `⁏⁏` - Discard the top item of the stack

### Arithmetic operation

All arithmetic operations start with `⁏` and followed by

* `;;` - Add the top two items and replace them with result
* `;⁏` - Subtract the second item from first and replace with result
* `⁏;` - Multiply top two items and replace them with result
* `⁏⁏` - Divide the first item by the second and replace with result
* `ss` - Module the first item by the second and replace with result

### Heap access

All heap storage access start with `;s` and followed by

* `;` - Store the first item into address of the second item
* `⁏` - Retrieve and push the value in the address of the top item

### Input/Output

All Input/Output operations start with `⁏s` and followed by

* `;;` - Output the character at the top of the stack
* `;⁏` - Output the number at the top of the stack
* `⁏;` - Read a character and place it in location given by the top item
* `⁏⁏` - Read a number and place it in location given by the top item

### Flow control

All flow controls start with `s` and followed by

* `;;` - Mark a location in the program (*param:* label)
* `;⁏` - Call a subroutine (*param:* label)
* `;s` - End a subroutine and transfer control back to caller
* `⁏s` - Jump unconditionally to a label (*param:* label)
* `⁏;` - Jump to a label if top item is zero (*param:* label)
* `⁏⁏` - Jump to a label if top item is negative (*param:* label)
* `s;` - Exit the program

If you like this project, please watch this and [follow](http://github.com/users/follow?target=pksunkara) me.

## Contributors
Here is a list of [Contributors](http://github.com/pksunkara/semicolon/contributors)

__I accept pull requests and guarantee a reply back within a day__

## License
MIT/X11

## Bug Reports
Report [here](http://github.com/pksunkara/semicolon/issues). __Guaranteed reply within a day__.

## Contact
Pavan Kumar Sunkara (pavan.sss1991@gmail.com)

Follow me on [github](http://github.com/pksunkara), [twitter](http://twitter.com/pksunkara)
