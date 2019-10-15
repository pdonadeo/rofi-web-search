# Rofi web search

[![Demo](./demo/screencast.gif)](https://youtu.be/2o1t_vuU6LU)

## General description

This simple script is aimed to have something like Spotlight on OSX to make a
web search in a minimalistic window manager using
[Rofi](https://github.com/davatorium/rofi). Personally I use
[i3-gaps](https://github.com/Airblader/i3) but any window manger is ok.

The script provides you the ability to ask suggestions to the search engine
before actually open the browser. Just close your search string with bang (`!`)
and type `ENTER`.

Suggestions will be listed by Rofi and you can select one of them or refine your
search using `CTRL+ENTER` (this is the standard Rofi binding) to copy the
selected line into the input field, then add a `!` and press `ENTER` again.

When you are using DuckDuckGo you can also use the
[bangs search](https://duckduckgo.com/bang), starting the search with a `!` and
optionally closing it with a `!` to get suggestions, as usual.

## Requirements

The only requirements are Rofi (of course...) and Python 3. No external packages
or libraries are required.

## Configuration

The script can be configured editing the first couple of lines. You can choose
the browser, search engine, and terminal (if using Lynx browser).

Supported browsers are Google Chrome, Firefox, Brave, Chromium, and Lynx.

Supported search engines are Google and DuckDuckGo.

If using Lynx, the supported browsers are `st` and `gnome-terminal`

Just open the script and edit the necessary variables:

`SEARCH_ENGINE`

* google
* duckduckgo

`BROWSER`

* chrome
* firefox
* chromium
* brave
* lynx

`TERMINAL`

* st
* gnome-terminal

In i3 you can bind the script in the usual way, for example this is my
configuration:

```bash
bindsym --release $mod+x exec --no-startup-id rofi -lines 10 -padding 0 -show search -modi search:~/bin/rofi-web-search.py -i -p "Search: "
```
