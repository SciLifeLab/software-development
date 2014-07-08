---
layout: page
title: Python
permalink: /python/
---

:gem: [PEP8][pep8] and :gem: [PEP20][pep20] (``import this``) should be considered as the starting points. Unless specified otherwise, we follow the guidelines laid out there. For a brief overview, read the [Python Guide][python-guide#style]'s entry on the subject.

## PEP8 exceptions
1. :green_apple: Indentation. You can use 2 or 4 *spaces* to indent code. The most important point is not to mix and match in any given project. Never use hard tabs.

## Installation
All packages should be installable through pip by running (inside project root):

{% highlight console %}
$ pip install [-e] .
{% endhighlight %}

This means that the package needs a ``setup.py`` file which is used by ``setuptools`` during installation. To expose console scripts [it's preferred][setuptools-entrypoints] to use :gem: [entry points][entry-points] over explicit Python scripts.

## Starting point
:thought_balloon: *To easily get set up with a base project structure we should provide a central skeleton repository to base future Python projects on. We might like to consider something like :gift_heart: [Cookiecutter][cookiecutter].*

## Python 2 vs. 3 support
Code should be written to take advantage of straight forward ways to accomplish universal Python support. This means:

1. Sticking to pure Python code whenever possible.
2. Making liberal use of :gem: ``from __future__ import <e.g. print_function>`` on any page where nessesary. This includes but is not limited to:
  - print_function
  - unicode_literals
  - absolute_import
  - division
3. The Python 3 version of the ``open`` functions should be used through :gem: ``from codecs import open``.
4. Use Python 3 style :gem: relative imports: ``from .subpackage import func``

## Command line utilities/scripts
If you are building anything remotely complex, the command line framework of choice is :green_apple: [Click][click]. It's an elegant and flexible package with a great syntax.

## Imperative vs. functional programming
Is writing unit tests for your code a piece of cake? If "yes", then you need not worry - you are probably writing good quality already. However, if you are struggling with your tests it might help to consider more of a *functional* (rather than imperative) approach. Read [an introduction to functional programming][functional] or take away some of the key points:

1. Each function should do *only* one thing.
2. Write *stateless* functions that perform tasks without knowledge of what's going on beyond it's scope.
3. Treat all data structures as immutable.
4. Think hard before adding for/while loops, there's usually a cleaner way to do it.
5. Compose small, discrete components into larger once.

## Docstrings
Functions, methods and classes should be annotated using :green_apple: [Google Style Docstrings][google-doc]. They look a little something like this:

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
We encourage using a :gift_heart: *linter* to continously check the syntax of your code. The Python community maintains a number of linters such as pep8, and [PyFlakes][pyflakes].

Another resource that can greatly ease collaboration is :gift_heart: [EditorConfig][editor-config]. It's an effort to provide a cross editor configuration format and in placed in your project and commited to source control. You also need to install a plugin for your favorite editor, e.g. [Sublime][sublime-config].

[pep8]: http://legacy.python.org/dev/peps/pep-0008/
[pep20]: http://legacy.python.org/dev/peps/pep-0020/
[pyflakes]: https://pypi.python.org/pypi/pyflakes
[flake8]: https://pypi.python.org/pypi/flake8
[entry-points]: http://pythonhosted.org/setuptools/pkg_resources.html#entry-points
[click]: http://click.pocoo.org/
[python-guide#style]: http://docs.python-guide.org/en/latest/writing/style/
[google-doc]: http://sphinxcontrib-napoleon.readthedocs.org/en/latest/example_google.html
[functional]: http://www.smashingmagazine.com/2014/07/02/dont-be-scared-of-functional-programming/
[editor-config]: http://editorconfig.org/
[sublime-config]: https://github.com/sindresorhus/editorconfig-sublime
[setuptools-entrypoints]: https://pythonhosted.org/setuptools/setuptools.html#automatic-script-creation
[cookiecutter]: https://github.com/audreyr/cookiecutter
