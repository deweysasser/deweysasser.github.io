# deweysasser.com website

Using [Jekyll](https://jekyllrb.com/) as the generator.

Adding the theme [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes)

## Setup

It should work to just type `bundle`.

## Building

* `make` -- both build the site locally and build an image
* `make site` -- use Jekyll to build the site
* `make image` -- builds an nginx image to serve the static site. The image is called `deweysasser`.

## TODO

* Do I want to use Jekyll long term?
* How do I get it deployed to k8s to serve it? I suppose I could push it to public docker hub --
  there's really nothing on here that's non-public. It's just that doing that feels wrong.