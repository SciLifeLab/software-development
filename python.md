---
layout: page
title: Python
permalink: /python/
---

[PEP8][pep8] should always be considered as the starting point. Unless specified otherwise, we follow the guidelines laid out there. For a brief overview look at the entry in the [Python Guide][python-guide#style].

## PEP8 exceptions
1. Indentation. You can use 2 or 4 *spaces* to indent code. The most important point is not to mix and match in any given project. Never use hard tabs.

## Installation
All packages should be installable through pip by running (inside project root):

{% highlight console %}
$ pip install [-e] .
{% endhighlight %}

This means that the package needs a ``setup.py`` file which is used by ``setuptools`` during installation. To expose scripts it's preferred to use [entry points][entry-points] over explicit python scripts.

## Starting point
To easy get set up with a base project structure we should provide a central skeleton repository to base future Python projects on.

## Python 2 vs. 3 support
Code should be written to take advantage of straight forward ways to accomplish universal Python support. This means:

1. Sticking to pure Python code whenever possible.
2. Making liberal use of ``from __future__ import <e.g. print_function>`` on any page where nessesary. This includes but is not limited to:
  - print_function
  - unicode_literals
  - absolute_import
  - division
3. The Python 3 version of the ``open`` functions should be used through ``from codecs import open``.

## Command line utilities/scripts
If you are building anything remotely complex, the command line framework of choice is [Click][click]. It's an elegant and flexible package with a great syntax.

## Imperative vs. functional programming
Is writing unit tests for your code a piece of cake? If "yes", then you need not worry - you are probably writing good quality already. However, if you are struggling with your tests it might help to consider more of a *functional* (rather than imperative) approach. Read [an introduction to functional programming][functional] or take away some of the key points:

1. Each function should do *only* one thing.
2. Write *stateless* functions that perform tasks without knowledge of what's going on beyond it's scope.
3. Treat all data structures as immutable.
4. Think hard before adding for/while loops, there's usually a cleaner way to do it.
5. Compose small, discrete components into larger once.

## Documentation
Documentation will inevitably be [the most][rdd] [important part][most-important-doc] of your project going forward. It's therefore important to use any and all means at your disposal to document your code. Think about including a lot of example usage and keep it concise and clearly structured.

### Flowcharts
Flowcharts can convey an overview that is impossible to put into words. It can be a great way to organize for example a pipeline of functions that will help you in the design of your project.

### Inline
Worry more about not documenting enough than documenting too much.

### Docstrings
Functions, methods and classes should be annotated using [Google Style Docstrings][google-doc]. They look a little something like this:

{% highlight python %}
def find(some_id):
  """Returns a single item defined by it's unique id. Returns
  ``None`` if it can't find the requested item.

  Args:
    some_id (str): unique item id

  Returns:
    dict or None: item from the data store or ``None``

  Examples:

    >>> find('1')
    {'id': 1, 'director': 'P.T. Anderson', ...}

  """
  pass
{% endhighlight %}

## Helpful tools
We encourage using a linter to continously check the syntax of your code. The Python community maintains a number of linters such as pep8, and [PyFlakes][pyflakes].

[pep8]: http://legacy.python.org/dev/peps/pep-0008/
[pyflakes]: https://pypi.python.org/pypi/pyflakes
[flake8]: https://pypi.python.org/pypi/flake8
[entry-points]: http://pythonhosted.org/setuptools/pkg_resources.html#entry-points
[click]: http://click.pocoo.org/
[python-guide#style]: http://docs.python-guide.org/en/latest/writing/style/
[google-doc]: http://sphinxcontrib-napoleon.readthedocs.org/en/latest/example_google.html
[functional]: http://www.smashingmagazine.com/2014/07/02/dont-be-scared-of-functional-programming/
[rdd]: http://tom.preston-werner.com/2010/08/23/readme-driven-development.html
[most-important-doc]: http://zachholman.com/posts/documentation/
