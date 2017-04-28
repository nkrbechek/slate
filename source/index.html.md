---
title: Browsersync command line help

language_tabs:
  - shell

toc_footers:
  - <a href='https://www.browsersync.io/'>Go to Browser-sync's website</a>
  - <a href='https://docs.google.com/document/d/1rfqMoSA7U2JUjNc9KDon84lIta0G9IL9XSJnJ8jFul8/edit?usp=sharing'>Justification Essay</a>

search: true
---


# Install
```shell
$ npm install -g browser-sync
```
1. **Install Node.js.** Browsersync is a module for Node.js, a platform for fast network applications. To run Browsersync, you must have Node.js installed; [Node.js installers for MacOS, Windows and Linux can be found here](http://nodejs.org/download/).
2. **Install Browsersync** With Node.js installed, you can use the Node.js package manager (npm) to install Browsersync from a repository. Open a terminal window and run the following command:

This tells the package manager to download the Browsersync files and install them globally (`-g`) so they're available to all your projects.



# Quick Start

## BrowserSync as 'Hot Reload' Server for local Static Files

```shell
# Command:
$ browser-sync start --server --files "."

#Your terminal output should look similar to this:
  [BS] Access URLs:
  ----------------------------------------
        Local: http://localhost:3000
     External: http://168.000.111.222:3000
  ----------------------------------------
           UI: http://localhost:3001
  UI External: http://168.000.111.222:3001
  ----------------------------------------
  [BS] Serving files from: ./
  [BS] Watching files...
```
The simplest use of browsersync is to watch `index.html` in your current directory. Browsersync expects `index.html` to exist, and will watch it by default.

`--server, -s` causes browser-sync to create a server and allow access to the specified files through localhost.

`--files, -f` is used to specify the file path that Browsersync should look for `index.html`.

Upon execution, this will open your default web browser and watch for changes in `index.html`. When you edit `index.html`, upon saving, Browser-sync will reload your browser to display the latest version.

[Here is the complete list of Command Line options for `browser-sync start`](#detailed-command-line-options)

## Watch files other than 'index.html'
```shell
$ browser-sync start -s -f “.” --index “myOtherHtmlFile.html”

```
The `--index` option allows you to direct Browsersync to watch a file other than the default `index.html`.

<b>NOTE:</b> that the abbreviation `-i` *does not exist*! You must fully write out `--index` to use this option.



## Create a Proxy for Existing Servers or Dynamic Sites
```shell
$ browser-sync start --proxy "myproject.dev" --files "css/*.css"
```

If you’re already running a local server with PHP or similar, you’ll need to use the proxy mode. Browsersync will wrap your vhost with a proxy URL to view your site.



## Make a Config File
```shell
# Initialize your config file:
$ browser-sync init

# Your terminal’s output should look similar to the following:
  [BS] Config file created bs-config.js
  [BS] To use it, in the same directory run: browser-sync start --config bs-config.js

# To run Browser-sync with settings from the config file:
$ browser-sync start --config bs-config.js

```
In the config file, you can customize many options to your server, including port, watchOptions, server, proxy, scrolling, and throttling.

`--config` and `-c` are interchangeable.

# Watch Multiple Files
To watch multiple files, use a config file.

1. Follow the instructions to make a config file (below)

2. In the `“files”` portion of the config file (around line 22), replace `false` with files: `["file1.html", "file2.css", “file3.js”]`, and so on.

3. For detailed instructions on config file options, visit [https://www.browsersync.io/docs/options/#option-files](https://www.browsersync.io/docs/options/#option-files)

# Detailed Command Line Options

```shell
# Command:
$ browser-sync start --help
```
Options       | Description
--------------|-------------
`--server, -s` |	Run a Local server (uses your cwd as the web root)
`--serveStatic, --ss` |	Directories to serve static files from
`--port` |	Specify a port to use
`--proxy, -p` |	Proxy an existing server
`--ws` |	Proxy mode only - enable websocket proxying
`--browser, -b` |	Choose which browser should be auto-opened
`--files, -f` |	File paths to watch
`--index` |	Specify which file should be used as the index page
`--plugins` |	Load Browsersync plugins
`--extensions` |	Specify file extension fallbacks
`--startPath` |	Specify the start path for the opened browser
`--https` |	Enable SSL for local development
`--directory` |	Show a directory listing for the server
`--xip` |	Use xip.io domain routing
`--tunnel` |	Use a public URL
`--open` |	Choose which URL is auto-opened (local, external or tunnel), or provide a url
`--cors` |	Add Access Control headers to every request
`--config, -c` |	Specify a path to a configuration file
`--host` |	Specify a hostname to use
`--logLevel` |	Set the logger output level (silent, info or debug)
`--reload-delay` |	Time in milliseconds to delay the reload event following file changes
`--reload-debounce` |	Restrict the frequency in which browser:reload events can be emitted to connected clients
`--ui-port` |	Specify a port for the UI to use
`--watchEvents` |	Specify which file events to respond to
`--no-notify` |	Disable the notify element in browsers
`--no-open` |	Don't open a new browser window
`--no-online` |	Force offline usage
`--no-ui` |	Don't start the user interface
`--no-ghost-mode`  |	Disable Ghost Mode
`--no-inject-changes` |	Reload on every file change
`--no-reload-on-restart` |	Don't auto-reload all browsers following a restart---
