---
title: Sprint 4 Project
layout: page
---


# alphadoc

[![PyPI version](https://img.shields.io/pypi/v/alphadoc.svg?color=green&style=for-the-badge)](https://pypi.org/project/pdoc3)
![ISSUES](https://img.shields.io/github/issues-closed/MLH-Fellowship/alphadoc?color=blue&style=for-the-badge)
![PULL REQUESTS](https://img.shields.io/github/issues-pr-closed/MLH-Fellowship/alphadoc?color=orange&style=for-the-badge)
    
Automatic docstring generator and style guide that supports a number of specified conventions for documentation in Python.

Features
--------
* Auto-generates docstrings with a customizable template for functions.
* Automatically fixes the code according to the standard PEP-8 style convention for python.
* Support for common and widely used docstrings formats such as Numpy, Google, ReStructured Text and Epytext (Javadoc)

Installation
------------
Using pip:

    $ pip install alphadoc

Usage
-----
alphadoc takes your filename and format type as arguments

    $ alphadoc <filename> -d <doc_format>

See `alphadoc --help` for more command-line switches and options!

Options :
```
Usage: alphadoc [OPTIONS] FILENAME

  Automatic docstring generator and style guide that  supports a
  number of specified conventions for formatting  as well as
  documentation in Python.

Options:
  -d, --doc_format TEXT  Specified format for docstrings from Options-
                         ReST : For ReStructured Text (default); Epytext
                         :  For Epytext (Javadoc); Google : For Google-
                         Style ; Numpydoc : For Numpydoc

  --help                 Show this message and exit.
```
Example :

Before alphadoc
```python
import ast
import sys

def top_level_functions(body):
    return (f for f in body if isinstance(f, ast.FunctionDef))

def parse_ast(filename):
    with open(filename, "rt") as file:
        return ast.parse(file.read(), filename=filename)

def get_func(filename):
    tree = parse_ast(filename)
    func_list = []
    for func in top_level_functions(tree.body):
        func_list.append(func.name)
    return func_list
```
After alphadoc 

Docstring format:

* **ReStructured Text** (default) 
```python
import ast
import sys

def top_level_functions(body):
    """
        This is reST style.

        :param param1: this is a first param
        :param param2: this is a second param
        :returns: this is a description of what is returned
        :raises keyError: raises an exception
    """
    return (f for f in body if isinstance(f, ast.FunctionDef))

def parse_ast(filename):
    """
        This is reST style.

        :param param1: this is a first param
        :param param2: this is a second param
        :returns: this is a description of what is returned
        :raises keyError: raises an exception
    """
    with open(filename, "rt") as file:
        return ast.parse(file.read(), filename=filename)

def get_func(filename):
    """
        This is reST style.

        :param param1: this is a first param
        :param param2: this is a second param
        :returns: this is a description of what is returned
        :raises keyError: raises an exception
    """
    tree = parse_ast(filename)
    func_list = []
    for func in top_level_functions(tree.body):
        func_list.append(func.name)
    return func_list
```
* **Epytext (Javadoc)** 
```python
import ast
import sys

def top_level_functions(body):
    """
        This is javadoc style.

        @param param1: this is a first param
        @param param2: this is a second param
        @return: this is a description of what is returned
        @raise keyError: raises an exception
    """
    return (f for f in body if isinstance(f, ast.FunctionDef))

def parse_ast(filename):
    """
        This is javadoc style.

        @param param1: this is a first param
        @param param2: this is a second param
        @return: this is a description of what is returned
        @raise keyError: raises an exception
    """
    with open(filename, "rt") as file:
        return ast.parse(file.read(), filename=filename)

def get_func(filename):
    """
        This is javadoc style.

        @param param1: this is a first param
        @param param2: this is a second param
        @return: this is a description of what is returned
        @raise keyError: raises an exception
    """
    tree = parse_ast(filename)
    func_list = []
    for func in top_level_functions(tree.body):
        func_list.append(func.name)
    return func_list
```
* **Google** 
```python
import ast
import sys

def top_level_functions(body):
    """
            This is an example of Google style.
            
            Args:
            param1: This is the first param.
            param2: This is a second param.

            Returns:
            This is a description of what is returned.

            Raises:
            KeyError: Raises an exception.
    """
    return (f for f in body if isinstance(f, ast.FunctionDef))

def parse_ast(filename):
    """
            This is an example of Google style.
            
            Args:
            param1: This is the first param.
            param2: This is a second param.

            Returns:
            This is a description of what is returned.

            Raises:
            KeyError: Raises an exception.
    """
    with open(filename, "rt") as file:
        return ast.parse(file.read(), filename=filename)

def get_func(filename):
    """
            This is an example of Google style.
            
            Args:
            param1: This is the first param.
            param2: This is a second param.

            Returns:
            This is a description of what is returned.

            Raises:
            KeyError: Raises an exception.
    """
    tree = parse_ast(filename)
    func_list = []
    for func in top_level_functions(tree.body):
        func_list.append(func.name)
    return func_list
```
* **Numpydoc** 
```python
import ast
import sys

def top_level_functions(body):
    """
        Numpydoc description of a kind
        of very exhautive numpydoc format docstring.

        Parameters
        ----------
        first : array_like
            the 1st param name `first`
        second :
            the 2nd param
        third : {'value', 'other'}, optional
            the 3rd param, by default 'value'

        Returns
        -------
        string
            a value in a string

        Raises
        ------
        KeyError
            when a key error
        OtherError
            when an other error
    """
    return (f for f in body if isinstance(f, ast.FunctionDef))

def parse_ast(filename):
    """
        Numpydoc description of a kind
        of very exhautive numpydoc format docstring.

        Parameters
        ----------
        first : array_like
            the 1st param name `first`
        second :
            the 2nd param
        third : {'value', 'other'}, optional
            the 3rd param, by default 'value'

        Returns
        -------
        string
            a value in a string

        Raises
        ------
        KeyError
            when a key error
        OtherError
            when an other error
    """
    with open(filename, "rt") as file:
        return ast.parse(file.read(), filename=filename)

def get_func(filename):
    """
        Numpydoc description of a kind
        of very exhautive numpydoc format docstring.

        Parameters
        ----------
        first : array_like
            the 1st param name `first`
        second :
            the 2nd param
        third : {'value', 'other'}, optional
            the 3rd param, by default 'value'

        Returns
        -------
        string
            a value in a string

        Raises
        ------
        KeyError
            when a key error
        OtherError
            when an other error
    """
    tree = parse_ast(filename)
    func_list = []
    for func in top_level_functions(tree.body):
        func_list.append(func.name)
    return func_list
```
## Inspiration
As the creator of Python, Guido Van Rossum believed that the superiority of python lies in the fact that it is easily understandable and readable through specified convention styles and documentation. Documentation of code is important not only for the programmers themselves but also for others who use, collaborate, or learn from it. But do programmers love to document their code? Well, that depends on them! But to make their work a little easier, we created alphadoc!

## What it does
alphadoc is a python standalone utility tool that automatically generates docstrings to help document the code better in python. It renders a customizable docstring template after each method detected in the code. Along with this, it also supports common and widely used docstrings formats such as Numpy, Google, ReStructured Text, and Epytext (Javadoc).

## How we built it
For the CLI interface, we used click and for parsing the code and detecting functions or methods in the script we used ast module in python. 

## Challenges we ran into
The biggest challenge was to parse the code and search for functions in it as well as to render the template at the exact positions. 

## Accomplishments that we are proud of
This was the first time we created and published a python for other developers to use and help them in documentation so it's quite an accomplishment itself.
 
## What we learned
We learned about the CLI interface and how to create standalone python CLI applications. In addition to this, we also learned about the Github actions and workflow as well as unit testing.

## What's next for alphadoc
Make the templates a little more customizable depending upon the type of method, the parameter it takes and returns.


References
-----------
http://daouzli.com/blog/docstring.html

Contributing
-----------
alphadoc is fully Open-Source and open for contributions! We request you to respect our contribution guidelines as defined in our [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) and [CONTRIBUTING.md](CONTRIBUTING.md)
