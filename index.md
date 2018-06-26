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
  web application framework.

  C++, HTML, CSS, Javascript, XSLT, MySQL

- [Apache File Extension Handler Guide](#apache-file-handler-guide):
  A guide to setting up Apache to send requests to a custom handler
  based on the file extension of the requested page.

- [C++ Lambda Presentation](#lambda-expressions-presentation):
  For a C/C++ Meetup, a slideshow and several C++ code experiments
  that explore the mechanics of C++11 lambda functions and closures.

  C++, with some Javascript for comparison.
  

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