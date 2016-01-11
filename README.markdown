# The Official raywenderlich.com C# Style Guide

This style guide is different from other you may see, because the focus is
centered on readability for print and the web. We created this style guide to
keep the code in our tutorials consistent. This style guide is based on the Java Style Guide. Being that the two languages have a lot in common, it makes sense to leverage the work being performed by the Android team.

Our overarching goals are __conciseness__, __readability__ and __simplicity__. Also, this guide is written to keep Unity in mind. 

You should also check out out [Java](https://github.com/raywenderlich/java-style-guide), [Swift](https://github.com/raywenderlich/swift-style-guide),
and [Objective-C](https://github.com/raywenderlich/objective-c-style-guide)
style guides too.

## Inspiration

This style-guide is somewhat of a mash-up between the existing C# language
style guides, and a tutorial-readability focused Swift style-guide. guide). This style guide was created from the Java style guide and then altered from various C# / Unity style guides across the web.

## Table of Contents

- [Nomenclature](#nomenclature)
  + [Namespaces](#namespaces)
  + [Classes & Interfaces](#classes--interfaces)
  + [Methods](#methods)
  + [Fields](#fields)
  + [Parameters](#parameters--parameters)
  + [Delegates](#delegates--delegates)
  + [Events](#events--events)
  + [Misc](#misc)
- [Declarations](#declarations)
  + [Access Level Modifiers](#access-level-modifiers)
  + [Fields & Variables](#fields--variables)
  + [Classes](#classes)
  + [Interfaces](#interfaces)
- [Spacing](#spacing)
  + [Indentation](#indentation)
  + [Line Length](#line-length)
  + [Vertical Spacing](#vertical-spacing)
- [Brace Style](#brace-style)
- [Switch Statements](#switch-statements)
- [Language](#language)
- [Copyright Statement](#copyright-statement)
- [Smiley Face](#smiley-face)
- [Credit](#credits)


## Nomenclature

On the whole, naming should follow C# standards.

### Namespaces

Namespaces are all __UpperCamelCase__, multiple words concatenated together,
without
hypens or underscores:

__BAD__:

```c#
com.raywenderlich.fpsgame.hud.healthbar
```

__GOOD__:

```c#
RayWenderlich.FPSGame.HUD.Healthbar
```

### Classes & Interfaces

Written in __UpperCamelCase__. For example `RadialSlider`. 

### Methods

Public methods are written in __UpperCamelCase__. For example `DoSomething`. 

Private methods are written in __lowerCamelCase__. For example: `doSometing`

### Fields

Written in __lowerCamelCase__.

Static fields should be written in __UpperCamelCase__:

```c#
public static int TheAnswer = 42;
```

All non-static fields are written __lowerCamelCase__. Per Unity convention, this includes __public fields__ as well.

For example:

```C#
public class MyClass {
  public int publicField;
  int packagePrivate;
  private int myPrivate;
  protected int myProtected;
}
```

Private non-static fields should start with a lowercase letter.

__BAD:__

```c#
private int _myPrivateVariable
```

__GOOD:__

```c#
private int myPrivateVariable
```


### Parameters

Parameters are written in __lowerCamelCase__.

__BAD:__

```c#
void doSomething(Vector3 Location)
```
__GOOD:__

```c#
void doSomething(Vector3 location)
```

Single character values to be avoided except for temporary looping variables.

### Delegates

Delegats are written in __UpperCamelCase__.

When declaring delegates, DO add the suffix __EventHandler__ to names of delegates that are used in events. 

__BAD:__

```c#
public delegate void Click()
```
__GOOD:__

```c#
public delegate void ClickEventHandler()
```
DO add the suffix __Callback__ to names of delegates other than those used as event handlers.

__BAD:__

```c#
public delegate void Render()
```
__GOOD:__

```c#
public delegate void RenderCallback()
```
### Events

Prefix event methods with the prefix __On__.

__BAD:__

```c#
public static event CloseCallback Close;
```
__GOOD:__

```c#
public static event CloseCallback OnClose;
```

### Misc

In code, acronyms should be treated as words. For example:

__BAD:__

```c#
XMLHTTPRequest
String URL
findPostByID
```
__GOOD:__

```c#
XmlHttpRequest
String url
findPostById
```

## Declarations

### Access Level Modifiers

Access level modifiers should be explicitly defined for classes, methods and
member variables.

### Fields & Variables

Prefer single declaration per line.

__BAD:__

```c#
string username, twitterHandle;
```

__GOOD:__

```c#
string username;
string twitterHandle;
```

### Classes

Exactly one class per source file, although inner classes are encouraged where
scoping appropriate.

### Interfaces

All interfaces should be prefaced with the letter __I__. 

__BAD:__

```c#
RadialSlider
```

__GOOD:__

```c#
IRadialSlider
```

## Spacing

Spacing is especially important in raywenderlich.com code, as code needs to be
easily readable as part of the tutorial. 

### Indentation

Indentation is using spaces - never tabs.

#### Blocks

Indentation for blocks uses 2 spaces (not the default 4):

__BAD:__

```c#
for (int i = 0; i < 10; i++) {
    Debug.Log("index=" + i);
}
```

__GOOD:__

```c#
for (int i = 0; i < 10; i++) {
  Debug.Log("index=" + i);
}
```

#### Line Wraps

Indentation for line wraps should use 4 spaces (not the default 8):

__BAD:__

```c#
CoolUiWidget widget =
        someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

__GOOD:__

```c#
CoolUiWidget widget =
    someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

### Line Length

Lines should be no longer than 100 characters long.


### Vertical Spacing

There should be exactly one blank line between methods to aid in visual clarity 
and organization. Whitespace within methods should separate functionality, but 
having too many sections in a method often means you should refactor into
several methods.


## Brace Style

Only trailing closing-braces are awarded their own line. All others appear the
same line as preceding code:

__BAD:__

```c#
class MyClass
{
  void DoSomething()
  {
    if (someTest)
    {
      // ...
    }
    else
    {
      // ...
    }
  }
}
```

__GOOD:__

```c#
class MyClass {
  void DoSomething() {
    if (someTest) {
      // ...
    } else {
      // ...
    }
  }
}
```

Conditional statements are always required to be enclosed with braces,
irrespective of the number of lines required.

__BAD:__

```c#
if (someTest)
  doSomething();
if (someTest) doSomethingElse();
```

__GOOD:__

```c#
if (someTest) {
  doSomething();
}
if (someTest) { doSomethingElse(); }
```


## Switch Statements

Switch statements fall-through by default, but this can be unintuitive. Do not use fall-through behavior. 

Alway include the `default` case.

## Language

Use US English spelling.

__BAD:__

```c#
string colour = "red";
```

__GOOD:__

```c#
string color = "red";
```

## Copyright Statement

The following copyright statement should be included at the top of every source
file:

    /*
     * Copyright (c) 2016 Razeware LLC
     * 
     * Permission is hereby granted, free of charge, to any person obtaining a copy
     * of this software and associated documentation files (the "Software"), to deal
     * in the Software without restriction, including without limitation the rights
     * to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
     * copies of the Software, and to permit persons to whom the Software is
     * furnished to do so, subject to the following conditions:
     * 
     * The above copyright notice and this permission notice shall be included in
     * all copies or substantial portions of the Software.
     * 
     * THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
     * IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
     * FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
     * AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
     * LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
     * OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
     * THE SOFTWARE.
     */

## Smiley Face

Smiley faces are a very prominent style feature of the raywenderlich.com site!
It is very important to have the correct smile signifying the immense amount of
happiness and excitement for the coding topic. The closing square bracket ] is
used because it represents the largest smile able to be captured using ASCII
art. A closing parenthesis ) creates a half-hearted smile, and thus is not
preferred.

Bad:

    :)

Good:

    :]

## Credits

This style guide is a collaborative effort from the most stylish
raywenderlich.com team members:

- [Darryl Bayliss](https://github.com/DarrylBayliss)
- [Sam Davies](https://github.com/sammyd)
- [Mic Pringle](https://github.com/micpringle)
- [Brian Moakley] (https://github.com/VegetarianZombie)
- [Ray Wenderlich](https://github.com/rwenderlich)

