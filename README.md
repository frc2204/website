# rambots-website

## Getting Started

This project uses [Jekyll](https://jekyllrb.com/) to generate a static website.

While it isn't neccisary to install Jekyll on your own computer, it's required if you would like a proper preview before
finalizing any changes.

To get started, you'll need to install Jekyll and its dependencies. You can find instructions for doing
so [here](https://jekyllrb.com/docs/installation/), but we've also included a quick guide below for Windows.

### Windows (RubyInstaller)

1. Download and install a Ruby+Devkit version from [RubyInstaller](https://rubyinstaller.org/downloads/) Downloads.
2. Run through the installation process. Towards the end of the, a terminal window will open. For this, stick with the
   default options by pressing `ENTER`.
3. Open a new terminal window and install Jekyll and Bundler with `gem install jekyll bundler`.

### Live Reload

To enable live reload, run the following in the project directory:

```
bundle exec jekyll serve --livereload
``` 

This will start a local server at `http://localhost:4000/` that will automatically update when you make changes to the
project files.