# ideal objects - language spec

## Overview

ideal objects is created to be a consumer-grade programming environment. One important idea fundamental to this system is objects. Everything is an object. The purpose of this language is to create a spec for manipulating objects. 

The basics of the language will focus on object manipulation. The next section will focus on logic manipulation. A third will be to manage the maniupulation of objects as sets. Some final pieces will inlcude the abilities to extend the overall language.

## Basics - Object Manipulation

### create

    create
    create [id]

create is the most standard item in the language. Use this to create an object. The passed id will be included in the object as the _id attribute. Create will put the created object on the locally-defined space. If no id is passed, then it will be automatically generated using a timestamp.

There are no guardrails on the create command. Any id can be used, and all created objects will be standard and basic.

### set

    set [prop name] [value]
    set [prop name] [value] [object]
    set [prop name] to [value] in [object]

set is the mechanism for changing properties of an object.

The object is optional -- it does not need to be set. When an object is not defined, the value will be saved to the local space. It can be referenced using the property name.

When the value is an object, instead of saving the object directly, it will insert a link to the object. This is typically a string that starts with :: or //.

### unset

    unset [prop name]
    unset [prop name] in [object id]
    unset [object id]

unset provides the mechanism for removing the property or object from the local space. If an object id is defined after the property name, it will unset that property in the object.

### rename

    rename [prop name] [new name]
    rename [prop name] [new name] [object id]
    rename [prop name] to [new name]
    rename [prop name] to [new name] in [object id]

rename provides the ability to change a property name. When an object is passed, it will change the name for that object. When it is not, it will change it in the local space.

### clone

    clone [object name]
    clone [object name] [new name]

clone provides the ability to copy one object into another. When no object id is passed, one will automatically be generated using a timestamp.

### Strings, Numbers, and Objects

Any value wrapped in " or ` (key to the left of the 1) will be considered a string. Use the ` for any value that contains line breaks.

Any number without quotes around it will be translated as a number.

Any quoted string that starts with :: or // will attempt a lookup for an object. If nothing is found, it will remain as a string.

### Transition Words

There are several words that can be used in between properties in commands to make the language easier to read (and maybe speak one day!). These will be identified by the interpreter and ignored.

### Variables

Any name without quotes and that is not a transition word can be translated in several different ways. First, it will look to see if there is an associated value in the local space. If there is not, it will convert it to a string.

## Math

### add

    add [num1] [num2] [name]
    add [num1] to [num2] as [name]
    add [num1] to [num2] as [object pointer]

add takes two numbers and adds them together. The result will be stored in the local space for the given name. Instead of using a name of a variable, you can define a path to an object property that will receive the result.

### subtract

    subtract [num1] [num2] [name]
    subtract [num1] from [num2] as [name]
    subtract [num1] from [num2] as [object pointer]

subtract takes two numbers and subtracts them. The result will be stored in the local space for the given name. Instead of using a name of a variable, you can define a path to an object property that will receive the result.

### multiply

    multiply [num1] [num2] [name]
    multiply [num1] by [num2] as [name]
    multiply [num1] by [num2] as [object pointer]

multiply takes two numbers and multiplies them. The result will be stored in the local space for the given name. Instead of using a name of a variable, you can define a path to an object property that will receive the result.

### divide

    divide [num1] [num2] [name]
    divide [num1] from [num2] as [name]
    divide [num1] from [num2] as [object pointer]

divide takes two numbers and divides them. The result will be stored in the local space for the given name. Instead of using a name of a variable, you can define a path to an object property that will receive the result.

### remainder

    remainder [num1] [num2] [name]
    remainder [num1] from [num2] as [name]
    remainder [num1] from [num2] as [object pointer]

remainder takes two numbers, divides them, and gets the remainder. The result will be stored in the local space for the given name. Instead of using a name of a variable, you can define a path to an object property that will receive the result.

### random

    random [num1] [num2] [name]
    random [num1] [num2] as [name]
    random [num1] [num2] as [object pointer]

random takes two numbers and returns a random number between them. The result will be stored in the local space for the given name. Instead of using a name of a variable, you can define a path to an object property that will receive the result.

## Spaces

### save

    save [object id]
    save [object id] to [space name]

save provides the mechanism for saving the object to a more permanent space. Any objects manipulated will be modified in the local space. Save pushes them to the space to be saved in.

If the _space property is set in the object, that will be the space saved to.

If space name is provided, it will set _space and save to that space.

### create space

    create space [space name]

create space provides a built-in mechanism for creating a new space. A space is an object and can be manipulated like one.

### save space

    save space [space name]

Spaces are initially stored in local memory. save space will save the space elsewhere. The metadata on a space will determine where it is saved.

### Metadata

Space methods will react to the following metadata:

    source - where the space is saved.

