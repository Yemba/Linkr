# Linkr

## Overview

A Ruby library for following links. NET/HTTP does not auto-redirect when webpages
return redirects 301's. Also with the amount of url shortening services out there
it is common to want to resolve urls to the cononical version.

Linkr fixes this problem through a simple interface.

## Dependencies

* Uses Net::HTTP under the hood. 
* Linkr requires the addressable Gem. This will be installed as a dependancy
when you install Linkr

## Installation

    gem install linkr

## Usage

    require 'linkr'

    # easy url resolving 
    Linkr.resolve("http://bbc.in/pdTHqe") => http://www.bbc.co.uk

    # if you need more info
    link = Linkr.new("http://bbc.in/pdTHqe", {
      redirect_limit => 10 # default 5
    }) 
    link.body => "<!DOCTYPE html PUBLIC \"-//W3C//DTD XHTML 1.0 Tr
    ansitional//EN\" \"http://www.w3.org/TR/xh".......</body></html>"

## Todo

* currently the passed url is returned unless it is redrected, so 500 errors for example are not reflected
* refactor resolve code

## Contributing

* Fork the project
* Send a pull request
* Don't touch the .gemspec, I'll do that when I release a new version
