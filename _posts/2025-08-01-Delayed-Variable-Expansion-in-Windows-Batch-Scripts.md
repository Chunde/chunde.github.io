---
layout: post
title: Delayed Variable Expansion
date: 2025-07-31 23:29:44
description: Explanation of delayed variable expansion in Windows batch scripting
tags: Windows BatchScript CMD Variables
tabs: true
---

Delayed variable expansion is a feature in Windows batch scripting that allows you to access the current value of a variable at execution time rather than at parse time. This is particularly useful when dealing with variables inside blocks of code (like `if` statements or `for` loops).

### Key Points:

1. **Syntax**: Uses exclamation marks `!var!` instead of percent signs `%var%`
2. **Activation**: Requires `SETLOCAL EnableDelayedExpansion` at the beginning of your script
3. **When Needed**: Essential when modifying and reading variables within the same block

### Example Without Delayed Expansion:
```bat
@echo off
set var=original
if 1==1 (
    set var=new
    echo %var%  :: Will still show "original"
)
```

### Example With Delayed Expansion:
```bat
@echo off
SETLOCAL EnableDelayedExpansion
set var=original
if 1==1 (
    set var=new
    echo !var!  :: Correctly shows "new"
)
```

### Mathematical Operations:
When performing calculations in loops, delayed expansion is often necessary:
```bat
SETLOCAL EnableDelayedExpansion
set /a count=0
for /l %%i in (1,1,5) do (
    set /a count+=1
    echo Iteration !count!
)
```

The main difference can be summarized with the equation:
$$ \text{Regular Expansion} \rightarrow \%var\% = \text{Value at parse time} $$
$$ \text{Delayed Expansion} \rightarrow !var! = \text{Value at execution time} $$

This feature is crucial for writing robust batch scripts that need to handle dynamic variable values within code blocks.