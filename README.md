My Ruby Configuration
=====================

My basic method of managing ruby on my system is using rbenv with bundler.  Also I rely on rubocop for style and syntax checking.

Overall I'm using the following strategy to organize my ruby interpreters and gem versions:

http://dan.carley.co/blog/2012/02/07/rbenv-and-bundler/


Prereqs:
--------

Your systems default ruby interpreter and development tools (gcc, make, etc)

Deploy:
-------

**Prerequisites:**

 * Ruby that your distro provides
 * Tools to compile ruby interpreter

**Procedure:**

Clone repo to your home directory:

    git clone git://github.com/nurfherder/dotruby.git ~/code/dot/dotruby

Create symlinks to config files and fetch submodules:

    cd ~/code/dot/dotvim
    git submodule update --init
    linkme.sh

Make sure the following lines are in your shell's config:

    PATH="$HOME/.rbenv/bin:$PATH"; export PATH
    eval "$(rbenv init -)"

Initial Setup:
--------------

This is how I initially added rbenv and some of its plugins to the repo.  You'd only need to do this if you're starting your own dotruby from scratch, or as a hint to adding your own favorite plugins.

    mkdir -p rbenv/plugins
    git submodule add git://github.com/sstephenson/rbenv.git ./rbenv
    git submodule add git://github.com/sstephenson/ruby-build.git ./rbenv-plugins/ruby-build
    git submodule add git://github.com/carsomyr/rbenv-bundler.git ./rbenv-plugins/bundlers
