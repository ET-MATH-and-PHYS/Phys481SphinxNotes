.. _sphinxDoc:

**Sphinx Documentation**
========================

http://www.sphinx-doc.org/en/master/

Sphinx is a tool that makes it easy to create intelligent and beautiful documentation.

It was originally created for the Python documentation, and it has excellent facilities for the documentation of software projects in a range of languages.  Useful features include

 * Multiple output formats: HTML (including Windows HTML Help), LaTeX (for printable PDF versions), ePub, Texinfo, manual pages, plain text

 * Extensive cross-references: semantic markup and automatic links for functions, classes, citations, glossary terms and similar pieces of information

 * Hierarchical structure: easy definition of a document tree, with automatic links to siblings, parents and children

 * Automatic indices: general index as well as a language-specific module indices

 * Code handling: automatic highlighting using the Pygments highlighter

 * Extensions: automatic testing of code snippets, inclusion of docstrings from Python modules (API docs), and more

 * Contributed extensions: more than 50 extensions contributed by users in a second repository; most of them installable from PyPI

Sphinx uses reStructuredText as its markup language, and many of its strengths come from the power and straightforwardness of reStructuredText and its parsing and translating suite, the Docutils.


Configuration
-------------
Each sphinx document will be managed using the following four files

  
    conf.py               # document configuration

    index.rst		  # top level document index

    make.bat              # windows command file

    Makefile              # unix command file
 

Content may also be provided in '.rst' (markup) format.  The 'nbsphinx' extension

  https://nbsphinx.readthedocs.io/en/0.4.2/

is used to automatically include Jupyter notebooks inside Sphinx documents.


Sphinx can generate a wide range of document types; these are located under the "_build" directory.
The '_static' and '_templates' subdirectories can be useful for developing more complex documents.

   _build
      epub
      html
      latex
      singlehtml

   _static

   _templates   
 
Document dependencies and auto-generation is managed under Linux with the classic "make" tool.  A LaTeX installation is also required in order to generate PDF.


