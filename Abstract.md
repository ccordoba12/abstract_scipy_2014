<!-- -*- mode: markdown; mode: flyspell; mode: auto-fill -*- -->


# Brief description

Our aim in this talk is to present a new library (tentatively called oinspect)
which would take a docstring written in reStructured Text (or otherwise) and
create two different representations of it: a rich one (based on HTML and
including images, highlighted doctests and rendered Latex) and a plain text one
(including extra information, like an object's class and constructor
docstrings).


# Towards a better documentation system for Scientific Python

*Author*: Carlos Cordoba <ccordoba12@gmail.com>

*Affiliation*: The Spyder Project


Since version 2.0 Spyder has had a plugin called *Object Inspector* to
interactively view docstrings rendered as beautiful HTML pages. To the best of
our knowledge it is the only system of this kind within the Scientific Python
ecosystem and hence it has become one of best Spyder selling points.

However its current implementation has two major limitations:

1. It's tied to Spyder's configuration system and utility modules. This doesn't
let other projects (e.g. IPython, IEP or Canopy) use it as a library.

2. It's not fully exploiting all Sphinx and HTML have to offer. On the one
hand, it could do a much better job by using the `numpydoc` and `plot` Sphinx
extensions to better render docstrings written with them. On the other hand, it
could also link standard library objects' help to their respective
documentation in docs.python.org. This is an important issue any documentation
system has to solve because the inability to quickly access those docs hampers
the pretty powerful *batteries included* Python philosophy.

Our aim in this talk is to present a new library (tentatively called
`oinspect`) which would be based in Spyder's `sphinxify` module and also
IPython's `oinspect` one. The first one already provides the bridge between
plain text Rst and HTML. The second is used by IPython to successfully extract
class and constructor docstrings for objects that permit it. In many cases
(e.g. Pandas `DataFrame`'s) the real source of an object's help is one or both
of those docstrings instead of its own one.

This library would constitute a good foundation on which a more powerful and
richer documentation system could be built in the future, and we consider SciPy
the perfect place to publicly release it and get feedback about it from the
community.


# Additional notes

A good documentation system is a must for any scientific platform, given its
interactive and exploratory nature because users want to quickly and readily
consult how to use the libraries they have imported. The idea of this proposal
is to show how we could start building this system for Scientific Python by
improving how docstrings are rendered in the IPython Notebook and other
projects like Spyder, IEP and Canopy.


# Further thoughts

`oinspect` would provide a public API to ask for two different representations
of a docstring:

- A plain text version, to be used by the IPython terminal and which would be
  mostly the same as the current IPython representation.

- And a rich HTML one to be used by Spyder and the IPython Notebook.


<!--  LocalWords:  Spyder css numpy Scipy MathJax metadata Mathematica Ipython
 -->
<!--  LocalWords:  Ipython's LocalWords IPython's accesible docstring IPython
 -->
<!-- LocalWords: IDE plugin docstrings lookfor ccordoba gmail Spyder's IEP Rst
 -->
<!--  LocalWords: sphinxify markdown flyspell oinspect numpydoc ipython API
 -->
<!--  LocalWords:  DataFrame qtconsole SciPy frontend reStructured Javascript
 -->
<!--  LocalWords:  doctests
 -->
