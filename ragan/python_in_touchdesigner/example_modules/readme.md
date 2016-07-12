# Python in TouchDesigner #

## Programmer / Artist ##

**Matthew Ragan** | [ matthewragan.com](http://matthewragan.com)  

## example_modules ##

There are a number of ways that we might use modules on demand in TouchDesigner. Before we get too far along, however, we might first ask "what is a module on demand?"

According to the [TouchDesigner wiki](http://derivative.ca/wiki088/index.php?title=MOD_Class):

```
The MOD class provides access to Module On Demand object, which allows DATs to be dynamically imported as modules. It can be accessed with the mod object, found in the automatically imported td module. Alternatively, one can use the regular python statement: import. Use of the import statement is limited to modules in the search path, where as the mod format allows complete statements in one line, which is more useful for entering expressions. Also note that DAT modules cannot be organized into packages as regular file system based python modules can be.
```

What does this mean? It's hard to sum up in just a single sentence, but the big thing to take away is that we can essentially use any text DAT to hold whole functions for us that we can then call whenever we want.

Let's take a closer look at this process. We'll start with some simple ideas, then work our way up to something a little more complicated.

First we turn things way down, and just think about storing variables. To be clear, we probably wouldn't use this in a project, but it can be helpful for us when we're trying to understand what exactly is going on here.

Let's create a new text DAT and call it "text_variables", inside let's put the following text:

```python
width       = 1280
height      = 720

budget      = 'small'
```

Using the mod class we can access these variables in other operators! To do this we'll use the following syntax:

```python
mod( 'text_variables' ).width
mod( 'text_variables' ).height
mod( 'text_variables' ).budget
```

Try adding a constant CHOP, and a text TOP to your network and using the expressions above to retrieve these values.

Next try printing these values:

```python
print( mod( 'text_variables' ).width )
print( mod( 'text_variables' ).height )
print( mod( 'text_variables' ).budget )
```



