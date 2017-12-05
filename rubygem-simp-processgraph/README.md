<%- includes(:badges,'') do |badges| -%>
<%= badges -%>
<%- end -%>

# simp-processgraph

A tool to draw the process graphs

#### Table of Contents
1. [Overview](#overview)
2. [Setup](#setup)
3. [Beginning with simp-processgraph](#beginning-with-simp-processgraph)
4. [Environment variables](#environment-variables)
5. [Methods](#methods)
6. [Examples](#examples)
7. [License](#license)

## Overview

This code allows you to plot the communications between your host and others.

* It uses the `ss` (socket statistics) command with the `-npatuw` options

-n, --numeric - Do not try to resolve service names.<br>
-a, --all - Display all sockets.<br>
-p, --processes - Show process using socket.<br>
-t, --tcp - Display only TCP sockets.<br>
-u, --udp - Display only UDP sockets.<br>
-w, --raw - Display only RAW sockets.

* It creates an array of hashes of (sitename, hostname, domainname, localIP, localPort, process, user, peerIP, peerPort, socketUsers),
and writes the interim data to a file,
* Then it creates a graph, boxing up site, host, IP, ports, and connecting to destinations.
You can link port-to-port (default), IP-to-IP, or process-to-process, each conglomerating the data underneath. 
Lines are color-alternated to keep them distinct.


## Setup

In order to create the .png files, you must have graphviz installed
```bash
sudo yum install graphviz graphviz-devel graphviz-ruby
```
Build and install the gem by running
```bash
rake pkg:install_gem`
```
(to see other rake options, run `rake -T`)

### Beginning with simp-processgraph

Add this to your project's `Gemfile`:

```ruby
gem 'simp-processgraph'
```

## Environment variables

To ensure you can see the Ruby libraries, type:
```bash
export RUBYLIB=/usr/lib64/graphviz/ruby
```

## Methods


## Examples

and run it

`$ processgraph -s [sitename]`

The usage can be found by typing

`$ processgraph --help`

or, type in the command below to run it right from the ruby:

`$ ruby simp-processgraph.rb`


## License
See [LICENSE](LICENSE)
