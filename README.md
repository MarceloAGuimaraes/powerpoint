[![version](https://badge.fury.io/rb/powerpoint.svg)](https://badge.fury.io/rb/powerpointk)
[![downloads](https://ruby-gem-downloads-badge.herokuapp.com/powerpoint?type=total&total_label=downloads)](https://ruby-gem-downloads-badge.herokuapp.com/powerpoint?type=total&total_label=downloads)

# 'powerpoint' gem -- for creating PowerPoint Slides in Ruby.

'powerpoint' is a Ruby gem that can generate PowerPoint files(pptx).

## Installation

'powerpoint' can be used from the command line or as part of a Ruby web framework. To install the gem using terminal, run the following command:

    gem install powerpoint

To use it in Rails, add this line to your Gemfile:

    gem "powerpoint"


## Basic Usage

'powerpoint' gem can generate a PowerPoint presentaion based on a standard template:

```ruby
require 'powerpoint'

@deck = Powerpoint::Presentation.new

# Creating an introduction slide:
title = 'Bicycle Of the Mind'
subtitle = 'created by Steve Jobs'
@deck.add_intro title, subtitle

# Creating a text-only slide:
# Title must be a string.
# Content must be an array of strings that will be displayed as bullet items.
title = 'Why Mac?'
content = ['Its cool!', 'Its light.']
@deck.add_textual_slide title, content

# Creating an image Slide:
# It will contain a title as string.
# and an embeded image
title = 'Everyone loves Macs:'
image_path = 'samples/images/sample_gif.gif'
@deck.add_pictorial_slide title, image_path

# Specifying coordinates and image size for an embeded image.
# x and y values define the position of the image on the slide.
# cx and cy define the width and height of the image.
# x, y, cx, cy are in points. Each pixel is 12700 points.
# coordinates parameter is optional.
coords = {x: 124200, y: 3356451, cx: 2895600, cy: 1013460}
@deck.add_pictorial_slide title, image_path, coords

# Saving the pptx file to the current directory.
@deck.save('test.pptx')
```
  
## Compatibility

'powerpoint' gem has been tested with LibreOffice (4.2.1.1) and Apache OpenOffice (4.0.1) on Mac OS X Mavericks, Microsoft PowerPoint 2010 on Windows 7 and Google Docs (latest version as of March 2014).

## Contributing

Contributions are welcomed. You can fork a repository, add your code changes to the forked branch, ensure all existing unit tests pass, create new unit tests cover your new changes and finally create a pull request.

After forking and then cloning the repository locally, install Bundler and then use it to install the development gem dependecies:

    gem install bundler
    bundle install

Once this is complete, you should be able to run the test suite:

    rake


## Bug Reporting

Please use the [Issues](https://github.com/MarceloAGuimaraes/powerpoint/issues) page to report bugs or suggest new enhancements.