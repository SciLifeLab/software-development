---
layout: page
title: Environment
permalink: /environment/
---

The process of setting up a development environment can make or break you. Nobody likes messing with conflicting executables but we've all been there. Luckily so has *every other developer* and so there are some great tools and concepts to aliviate or avoid most issues.

Remember that it's usually best to install development tools to *one single location* (to be easily removed) and without using ``sudo`` on your local machine. The tools mentioned below will help you achive this.

## Virtualization
Virtualization is "[the act of creating a virtual [...] computer hardware platform][wiki-virtualization]" on e.g. your local dev machine. Benefits include *complete* separation of installed software and ability to exactly mimic a given production environment.

### Vagrant
:gift_heart: [Vagrant][vagrant] is a much hyped technology to manage multiple virtualized servers. It essentially works by providing a command line interface to tools like :gift_heart: [VirtualBox][virtualbox] that reads a ``Vagrantfile``.

  > You might want to consider including a **Vagrantfile** in your projects as a simple way of setting a customized and complete development environment dependencies for potential collaborators.

## Text editor
The choice of editor is a highly personal decision. What's most important is **stability**, support for plugins, an active developer community - and of course that it *feels right*.

If you lack preferences, go with :gift_heart: [Sublime Text][sublime] or for a free alternative :gift_heart: [Atom by GitHub][atom]. If you have a lot of free time, there's also :gift_heart: [VIM][vim].

:thought_balloon: *Some people prefer IDEs.*

## Languages
Installing a programming language can be a pain, especially if said language comes in multiple, incompatible versions that you have to support and test (see: [Python 2 vs 3][py2v3]).

Because this is a prevalent enough problem, there's usually a rather painless option to handle installing multiple version of languages for you.

### Installing Python
The official solution is to use a mix of [pyenv][pyenv] and [virtualenv][virtualenv]. There is, however, alternatives that work slightly different but require even less dependecies, i.e. C-compilers etc.

One such option is the :gift_heart: [Miniconda][miniconda] (slimmed down version of the [Anaconda][anaconda] distribution). Miniconda includes a complementary package manager called *Conda* that greatly simplifies and speeds up installation of complex Python packages with C/Fortran dependencies. *Conda* will also replace your need for virtualenv as it has it's own, slightly different, concepts of Python virtualized environments. It's easy to create parallell Python installations and switch between Python 2.7 and 3.4.

### Installing Node.js
[nave][nave] or [n][n] seem to be the simplest ways to install and manage one or multiple versions of [Node.js][node].

This seems like a simple way to install *n* (without *npm*).

{% highlight bash %}
$ mkdir ~/tmp
$ cd ~/tmp
$ git clone https://github.com/visionmedia/n
$ cd n
$ make install
{% endhighlight %}

### Installing Ruby
[rbenv][rbenv] seems to be the way to go.



[rbenv]: http://rbenv.org/
[node]: http://nodejs.org/
[nave]: https://github.com/creationix/nvm
[n]: https://github.com/visionmedia/n
[anaconda]: https://store.continuum.io/cshop/anaconda/
[miniconda]: http://conda.pydata.org/miniconda.html
[wiki-virtualization]: http://en.wikipedia.org/wiki/Virtualization
[vagrant]: http://www.vagrantup.com/
[virtualbox]: https://www.virtualbox.org/
[sublime]: https://www.sublimetext.com/
[atom]: https://atom.io/
[vim]: http://vim-adventures.com/
[pyenv]: https://github.com/yyuu/pyenv
[virtualenv]: https://virtualenv.pypa.io/en/latest/
[py2v3]: {{ site.baseurl }}/python#python2vs3
