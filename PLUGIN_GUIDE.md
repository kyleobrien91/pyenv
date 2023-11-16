# Pyenv Plugin Guide

## Introduction

Pyenv plugins provide a simple, flexible, and maintainable way to extend and customize the functionality of Pyenv. They allow you to add extra logic that can be run at certain moments, making it easy to add new features or modify existing behavior. This guide will explain how to use existing Pyenv plugins and how to develop your own.

## Using Existing Pyenv Plugins

To use an existing Pyenv plugin, you first need to install it. This typically involves cloning the plugin's repository into the `$(pyenv root)/plugins` directory.

Once a plugin is installed, you can use it by running Pyenv commands as you normally would. The plugin will automatically be invoked when appropriate.

One of the most useful features of Pyenv plugins is the ability to run commands with a plugin's version selection. This can be done using the `pyenv exec` command. For example, if you have a plugin that provides a custom Python version, you can use `pyenv exec` to run a command with that version.

## Developing Pyenv Plugins

Developing a new Pyenv plugin involves creating a new directory in the `$(pyenv root)/plugins` directory and adding a shell script that implements the plugin's functionality.

The structure of a Pyenv plugin is quite simple. At its core, a plugin is just a shell script that is run at certain moments. The script can define functions that are run when certain Pyenv commands are invoked.

To create a new plugin, start by creating a new directory in the `$(pyenv root)/plugins` directory. The name of the directory should be the name of your plugin.

Next, create a shell script in your plugin's directory. The name of the script should be the name of the Pyenv command that your plugin extends. For example, if your plugin extends the `pyenv install` command, the script should be named `install`.

The script should define a function for each phase of the command that it extends. For example, a plugin that extends the `pyenv install` command might define functions for the `download`, `extract`, `configure`, `build`, and `install` phases.

Testing a Pyenv plugin involves running the Pyenv commands that the plugin extends and verifying that they behave as expected. This can often be done using the existing Pyenv test suite, but you may also need to write additional tests depending on the functionality of your plugin.

## Further Reading

For more information on Pyenv plugins, check out the following resources:

- [Pyenv Wiki](https://github.com/pyenv/pyenv/wiki)
- [Pyenv Plugin Examples](https://github.com/pyenv/pyenv/tree/master/plugins)
