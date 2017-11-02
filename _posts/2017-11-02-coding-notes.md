---
layout: post
title: Starting Coding Notes
author_profile: true
---

# ZN's Developing Notes

*Some notes*

----

## Table of Contents

1. [Reading to do..?](#reading-to-do)
    1. [Chat with Robert Gieseke](#chat-with-robert-gieseke)
1. [Foreword](#foreword)
1. [If you read nothing else](#if-you-read-nothing-else)
1. [Syntax](#syntax)
1. [The Command Line](#the-command-line)
1. [Python 2.7](#python-27)
    1. [Glossary/definitions](#glossary/definitions)
    1. [Common errors](#common-errors)
    1. [Background](#background)
        1. [Python Packages and Modules](#python-packages-and-modules)
        1. [Namespaces, scoping and importing](#namespaces,-scoping-and-importing)
            1. [Namespaces and scoping](#namespaces-and-scoping)
            1. [dir()](#dir)
            1. [Importing](#importing)
                1. [Best](#best)
                1. [Worse](#worse)
                1. [Worst](#worst)
                1. [Summary](#summary)
            1. [Module cache](#module-cache)
            1. [`__init__.py`](#__init__py)
            1. [Controlling names](#controlling-names)
        1. [Executing modules as scripts](#executing-modules-as-scripts)
        1. [Naming](#naming)
        1. [Imports](#imports)
            1. [Explicit relative imports](#explicit-relative-imports)
            1. [Implicit relative imports](#implicit-relative-imports)
            1. [Absolute imports](#absolute-imports)
        1. [Sharing data](#sharing-data)
            1. [Between modules](#between-modules)
            1. [Within a module](#within-a-module)
        1. [Setting paths](#setting-paths)
        1. [Pretty print](#pretty-print)
        1. [Logging](#logging)
        1. [Debugging](#debugging)
        1. [Testing](#testing)
            1. [`pytest`](#pytest)
                1. [Running](#running)
                1. [Assertions](#assertions)
                    1. [Assert](#assert)
                    1. [Error](#error)
                    1. [Warning](#warning)
                1. [Fixtures](#fixtures)
                    1. [Returning](#returning)
                    1. [Finalisers](#finalisers)
                    1. [Usage](#usage)
                    1. [Arguments](#arguments)
                    1. [Discovery rules](#discovery-rules)
                1. [Marks](#marks)
                1. [Configuration](#configuration)
    1. [How to set up a Python package](#how-to-set-up-a-python-package)
        1. [Exploiting `__name__` == `__main__`](#exploiting-__name__-__main__)
            1. [Sources and further reference](#sources-and-further-reference)
        1. [Code Structure](#code-structure)
        1. [Repository structure](#repository-structure)
    1. [Style](#style)
        1. [Programming Recommendations](#programming-recommendations)
        1. [Typesetting](#typesetting)
            1. [Overarching pieces of advice](#overarching-pieces-of-advice)
            1. [Basic rules](#basic-rules)
                1. [Comments](#comments)
                1. [Indentation](#indentation)
                1. [Maximum line length](#maximum-line-length)
                1. [Quotes](#quotes)
                1. [Whitespace](#whitespace)
                1. [Imports](#imports_1)
                1. [Continuing lines](#continuing-lines)
                1. [Line breaks and binary operators](#line-breaks-and-binary-operators)
        1. [Naming Conventions](#naming-conventions)
            1. [Rules](#rules)
            1. [Underscores](#underscores)
        1. [Potentially useful libraries](#potentially-useful-libraries)
    1. [Documentation](#documentation)
        1. [Examples](#examples)
        1. [Notes from PEP 257](#notes-from-pep-257)
    1. [Distributing](#distributing)
        1. [Public vs. Private](#public-vs-private)
        1. [Setuptools](#setuptools)
            1. [Installing setuptools](#installing-setuptools)
            1. [`setup.py`](#setuppy)
                1. [Basics](#basics)
                1. [README](#readme)
                1. [Other fields](#other-fields)
                    1. [Specifying dependencies](#specifying-dependencies)
                    1. [Long description](#long-description)
                    1. [Keywords](#keywords)
                    1. [url](#url)
                    1. [Tests](#tests)
                    1. [Other classifiers](#other-classifiers)
            1. [Source distributions and wheels](#source-distributions-and-wheels)
                1. [Create source distribution](#create-source-distribution)
                1. [Create wheel](#create-wheel)
                1. [`.gitignore`](#gitignore)
                1. [Installing with source distribution or wheel](#installing-with-source-distribution-or-wheel)
            1. [Sources and further reference](#sources-and-further-reference_1)
        1. [PyPI and pip](#pypi-and-pip)
            1. [Registering with PyPI](#registering-with-pypi)
            1. [Registering your package](#registering-your-package)
            1. [Upload to PyPI](#upload-to-pypi)
            1. [Test the install](#test-the-install)
            1. [Sources and further reference](#sources-and-further-reference_2)
            1. [Working in development mode](#working-in-development-mode)
        1. [Conda](#conda)
    1. [Refactoring](#refactoring)
    1. [Other tips and tricks](#other-tips-and-tricks)
        1. [Comprehensions](#comprehensions)
        1. [Plotting](#plotting)
        1. [Why you should move to Python 3 (or at least the common subset)](#why-you-should-move-to-python-3-or-at-least-the-common-subset)
1. [Matlab](#matlab)
    1. [Refactoring](#refactoring_1)
    1. [Other tips](#other-tips)
1. [Sublime](#sublime)
    1. [Packages I like](#packages-i-like)

<!-- End of table of contents -->

## Reading to do..?

http://python.net/~goodger/projects/pycon/2007/idiomatic/handout.html#other-languages-have-variables at some point 

Other reading? [http://www.datasciencecentral.com/profiles/blogs/the-guide-to-learning-python-for-data-science]

Good code should read like a story/report with executive summary and then other bits. No section of code should be more than a screen in length (~80 lines)

Refactoring is risky. To do it properly you need to do it in a systematic, controlled, disciplined, step by step manner.

Integrating refactoring into your production cycle helps avoid the decline of code from engineering to hacking. With refactoring you can take bad design/chaos and turn it into well designed code. However this only works if refactoring is part of the production process.

https://www.youtube.com/watch?v=t4vKPhjcMZg

https://www.divio.com/en/blog/documentation/

Tests - test each bit individually

Then do parameterised tests to make sure none of the combinations breaks things

https://software-carpentry.org/lessons/

http://katyhuff.github.io/python-testing/

Docker or posting link to conda environment (or conda kapsule) people can download for reproducibility

https://zapier.com/blog/organize-files-folders/

https://zapier.com/

Setting something like this up for my projects, which automatically sets up example function definitions, tests, snippets, documentation etc. would be awesome https://github.com/pytest-dev/cookiecutter-pytest-plugin

If you can't explain your function in a 'To do x, do y, z then w.' sentence, your function is too long.

Error handling, add in