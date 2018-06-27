---
title       : Chuck Jungmann's GitHub
tagline     : Where does this tagline appear?
description : Home Page for Chuck Jungmann's Programming Projects and Artifacts
---

# Chuck Jungmann's GitHub Page

Several years ago, having finally committed to using source control and
learned how to use *git*, I created an account on GitHub to save my
projects.  My primary goal was to preserve access to earlier versions
of development in order to roll-back mistakes and to serve as an online
backup of my progress.

The secondary goal of using a public repository is that I thought
I could use it to showcase my programming style and aptitude.  But
my exclusive focus on a single project, [Schema Framework](#schema-framework),
which grew far beyond my original plans, contradicted that purpose.
The project was so large that it would be unreasonable to expect
someone to get an accurate impression.

So I have started to create smaller projects that solve smaller
problems.  I can more easily indulge my curiosity when I discover
unexpected features of a language or environment.  I strive to
write easily understood code and to leave a record of what I learn
when I push the projects to *GitHub*.

## GitHub Projects

- [Schema Framework](#schema-framework): A full-stack database-driven
  web application framework. (**C++, HTML, CSS, Javascript, XSLT,
   MySQL**)

- [Apache File Extension Handler Guide](#apache-file-handler-guide):
  A guide to setting up Apache to send requests to a custom handler
  based on the file extension of the requested page.
  (**Apache .conf files**)

- [C++ Lambda Presentation](#lambda-expressions-presentation):
  For a C/C++ Meetup, a slideshow and several C++ code experiments
  that explore the mechanics of C++11 lambda functions and closures.
  (**C++, with some Javascript for comparison**)

- [Projects *scrape* and *namegen* ](#web-scraping-for-weighted-names-lists)
  together provide a data sample issue for Schema Framework by
  collecting names statistics from the internet. (**Python, BASH, XSLT,
  libxml2**)

- [xsl-import](#xsl-import) creates a single XSLT file by incorporating
  xsl:import files.  (**Python, XSLT**)

- [libxmlsqlcb](https://github.com/cjungmann/libmysqlcb) is a shared
  library that executes MySQL queries and returns results to a lambda
  function. (**C++, MySQL, C-Api**)

- [gensfw](#gensfw-to-generate-schema-framework-scripts) is an ambitious
  BASH project that generates Schema Framework SRM and SQL scripts using
  [yad](https://github.com/v1cont/yad) (Yet Another Dialog)
  Schema Framework.  (**BASH, YAD, awk**)

- [pxml2ods](#pxml2ods-for-creating-spreadsheet-files-from-xml)
  creates a spreadsheet in a widely-recognized format from XML.
  (**Python, XSLT, zipfile**)

- [Hacker Rank](#hacker-rank-competiion-solutions)
  Playing around with C and purely stack-based memory allocation. (**C**)


## Schema Framework

[source](https://github.com/cjungmann/schemafw)

This very large project a full-stack web application framework.
It is implemented in two parts:
- a FastCGI server object, written in C++, that returns XML
  documents from MySQL query results, and
- a large and growing client framework that uses HTML, CSS,
  Javascript, XML-Http-Request, and XSLT stylesheets to generate
  pages through which users interact with the MySQL data.

As I write this page I am extracting the FastCGI server component
into its own project to improve version control because it is on a
different update schedule from the rest of the project.


## Apache File Handler Guide

[source](https://github.com/cjungmann/apache-file-handler)

I wrote this guide after I finally succeeded in getting Apache to
use my Schema Server object to process requests to files that had
an **.srm** extension.  It's surprisingly difficult.

## Lambda Expressions Presentation

[source](https://github.com/cjungmann/lambda_talk)

Having extensively used lambda expressions in Javascript, I also
used lambda functions in the Schema Server.  I agreed to make a
presentation on this topic for a new C/C++ Meetup group in the
Twin Cities.  Along with the slideshow, I performed several
experiments to confirm my assumptions about how closures work,
particularly with respect to variable lifetimes and visibility.

## Web Scraping for Weighted Names Lists

[namegen source](https://github.com/cjungmann/namegen)<br/>
[scrape source](https://github.com/cjungmann/scrape)

While testing Schema Framework with a very large dataset, very poor
performance reminded me that I had neglected keyed element access
in the XSL stylesheets.  Wanting an arbitrarily large life-like
dataset, I decided to write a program to generate it for me.

This program collects surnames and boys and girls names from internet
sources, using frequency values to make weighted lists of names.
The weighted lists are used to create families or student registration
lists with a somewhat realistic distribution of first and last names.
No attempt is made to match names according to suggested cultural
norms, that is Jose is no more likely to be assigned to a Lopez family
than a Johansen family.


## XSL-Import

[source](https://github.com/cjungmann/xsl-import)

The built-in XSLT processors of some browsers are unable to reconcile
stylesheets.  Although the XML processor of the Schema Framework is
prepared to consolidate the files, having to handle imports can
interfere with caching.

Both methods (Framework and xsl-import) recursively open import files
and, after discarding duplicate match attributes, insert the contents
of the import file into the importing file.  Neither method works
with [xsl:apply-imports](https://www.w3schools.com/xml/ref_xsl_el_apply-imports.asp)
because the resulting file no longer contains any xsl:import
elements.

## libmysqlcb

[source](https://github.com/cjungmann/libmysqlcb)

With an eye toward future development of the Schema Server, I wanted
to learn about shared-object libraries in order to break the large
project into smaller self-contained pieces for improved readability
and maintainability.  Although not currently a complete replacement
for the MySQL code in the Schema Server, this library provides most
of that functionality, and is successful in the goal of working as
a dynamically-loaded library.

The project includes a small C++
[source file](https://github.com/cjungmann/libmysqlcb/blob/master/xmlify.cpp)
that demonstrates how to use the library.

## gensfw to Generate Schema Framework Scripts

[gensfw source](https://github.com/cjungmann/gensfw)<br/>
[bashmysql source](https://github.com/cjungmann/bashmysql)
[yaddemo source](https://github.com/cjungmann/yaddemo)

The command, `gensfw` is a CI command that uses `mysql` to collect schema
information from MySQL tables to generate SRM and SQL scripts.  The
mission of this program is to ease the tedious process of writing the
standard procedure and response mode scripts, matching datatypes of the
tables with the parameters of the procedures, and creating scripts that
follow standard Schema Framework practices.

[bashmysql](https://github.com/cjungmann/bashmysql) runs a query
and makes its results and result schemas available in environment
arrays that are used by a callback function.

Because the setup and result of YAD dialogs, relying heavily on command
line arrays, made my customary XSLT methods too cumbersome, I decided
that this project would also serve as experiment for learning BASH.

Along the way, I discovered some unexpected language "features" that
suggested new programming approaches.  [yaddemo](https://github.com/cjungmann/yaddemo)
contains several experiments I conducted to confirm my suspicions,
especially about unusual variable scoping.

## pxml2ods for Creating Spreadsheet Files from XML.

[source](https://github.com/cjungmann/pxml2ods)

This project is an improved and standalone implementation of the export
feature of the Schema Server.  It seems that the ODS file format resides
in the sweet-spot between universal readability, effortless importing,
and ease of coding.  In fact, ODS is much more complicated to create
this format than the universally-accepted CVS, but is favored because
of its unambiguous presentation of rows and columns.

## Hacker Rank Competiion Solutions

[source](https://github.com/cjungmann/HackerRank_ProjectEuler_Solutions)

I played with this site for a few weeks, trying my hand at pure C code
to solve some programming challenges.  I wanted to test my unusual
preference for stack-exclusive memory allocation against some memory-
intensive programs.