Goals
=====

The overarching goal of this grant is to dramatically improve biodiversity
names handling to reveal currently ’hidden’ knowledge for research, nature
conservancy, industry, and general public. Since 1750 biological information
has been interconnected and organized by means of scientific names; however it
has become increasingly difficult to keep up with names changes, duplications,
spelling variants. NSF grant 1062387 funded the Global Names initiative in US,
creating working prototypes of name services that would form part of the
cyberinfrastructure for the Big Data world in Biology.  Global Names developed
new tools to discover scientific names in digitized sources (texts, PDFs, or
images) and to verify these names and where necessary resolve them to a name
currently endorsed by taxonomic authorities.  The major goals of this project
are to develop the name services to a scalable, stable production level; to
create replication mechanisms which will simplify creation of local name
services for interested parties; to rework underlying algorithms and increase
quality and speed of name finding, resolution, and reconciliation; and to
achieve tight integration with other components of the Global Names
Architecture such as GNUB and the Clearing House for Taxonomies, and with
partners in the US, Europe, and China.

Major Activities
================

Team building
-------------

We spent significant effort creating a dynamic, professional team to bring
success to the project. When grant had been written we hoped to employ
programmers and system administrators of Encyclopedia of Life (EOL) Project.
By the time of funding EOL team decreased to two programmers, and we needed to
find other high quality professionals. During first round of search we were not
successful. However Dmitry Mozzherin, had been funded by EOL to acquire system
administration skills to move EOL project to Smithsonian's National Museum of
Natural History. We also were able to employ a developer of core Scala
libraries for the project. Taxonomical and nomenclatural knowledge is provided
by former lead coordinator of Global Names project -- David Patterson. As a
result we were able to get high quality experts for all important parts
aspects.

Selection of a programming language platform
--------------------------------------------

Advances in CPU manufacturing in the recent years created a need for
multiprocess, multi-threaded programming solutions. Our choice for a
programming language had narrowed down to 2 languages -- Go and Scala. Both are
created for modern multi-processor computers, both are fast, compiled
languages. We chose Scala in the end, because it is based on Java Virtual
Machine environment. That means that the code we write in Scala can be used in
a wide variety of JVM-compatible languages -- Java, Scala, R, Jython, JRuby.
Also it allows to take advantage of such Big Data-oriented multiprocessor,
multi-computer systems as Spark.

Planning
--------

We developed the roadmap based on Scala, which includes the following major
steps:

  1. Creation of Scala-based parser for scientific names
  2. Creation of Scala-based name index, name resolution service
  3. Creation of Scala based name finding service which is based on name
  parsing algorithm, and names selected from texts based on heuristic and
  machine learning techniques.

Programming
-----------

The goals of the grant heavily depend on programming. Alexander Myltsev, our
primary Scala developer had been able to lead technical part of the project. He
made a significant progress in making necessary libraries, tools and services.
Dmitry Mozzherin had been working together with Alexander writing Scala-based
parser, and rewriting name finding code, creating a cross-mapping tool for
scientific names lists.

Writing Scientific Papers
-------------------------

Our team worked on preparation of 3 papers to place them to biodiversity
informatics journals.

Community building
------------------

Dmitry Mozzherin participated in writing a proposal for Phylotastic project,
and now provides technical managerial and programming service to the project
(NSF Avard Number #1458572). We rewrote http://globalnames.org page to make
clearly state goals of our project, introduce tools we built. Create a place to
share news of our progress. We also use Tweeter for disseminating information.
We participated in a number of hackathons, and workshops organized by Catalogue
of Life, iDigBio, Global Names Architecture, University of Arisona.

Dmitry Mozzherin was invited to a position at University of Illinois into
Species Group team, where he started cooperation with one of the leading
taxonomic projects -- Catalogue of Life. Dmitry became part of the Global Team
of Catalogue of Life. We continue to work closely with Encyclopedia of Life
project.

System administration
---------------------

Moving Global Names to University of Illinois, setting up servers, operating
systems, Chef, Docker, CoreOS, Kubernetes had been our activities in System
Administration.

Specific Objectives
===================

1. Creation of scalable, stable, high quality services in Scala language

2. Reworking of algorithims used in the services

3. Moving services to University of Illinois

4. Developing approaches whch would make our services easy to install locally

5. Integration with other components of Global Names Architecture

6. Integration with Catalogue of Life, exploration of  use cases for our
services

Significant Results
=====================

Scalable, stable, production level name services
------------------------------------------------

We used existing "prototype" name parsing, finding, resolving projects as a
guideline for creation of much faster, scalable new services written mostly in
Scala programming language.

In the first year we developed production-ready scientific name parsing library
-- gnparser. The library had point releases so far. To our knowledge it is a
state of the art parser which highest precision and recall statistics. It is
also able to parse 30million names per one cpu per hour, which is exaclty 10
times faster than parser we wrote in Ruby. Also it scales linearly up to 4
processors, which means we are able to parse 120 million names an hour very
cost-effectively. We wrote extensive documentation for the parser, and
developed examples how to use it in 5 different languages, made it available
for Spark BigData platform, created TCP/IP socket and REST services, as well as
  command line program for parsing.

We are in the process of developing Scala based name index and name resolution
service. We developed a proof of concept version so far. It is heavily based on
very fast name parser, and we hope to be able to process 1000 names in less
than a second. We also create architecture which should withstand massive load
on our servers.

Rework of underlying algorithms for name finding, resolution, reconciliation
---------------------------------------------------------------------------

We rewrote name parsing algorithm. We still use Parins Expression
Grammar approach, the same we used for our popular Ruby-based parser. Scala
version makes it possible to do the same work more about two orders of
magnitude faster and cheaper. We are in the process of dramatically increasing
speed of name resolution algorithms.

We are currently working on name resolution algorithms to make them
more than one order of magnitude faster.

We won participation as mentors in Google Summer of Code, and used it to create
novel arpproaches in quality estimation of scientific names

Replication mechanisms to simplify creation of local names services
-------------------------------------------------------------------

We moved to linux containers approach to increase scalability and at the same
time hugely simplify installation of our products in local environments. We
moved all our production services to Docker platform which allows to install
all services with a one command on a terminal instead of complex instructions.

We also in the process of configuring CoreOS cluster which together with
OpenSource project Kubernetes developed by Goggle and used by Google internally
to create a massive fault tolerant system for running our services. We
successfully tried this approach on Google Engine Cloud first and now we are
implementing it for bare-metal machines in University of Illinois Data center.
In spite of significant complexity of from system administration point of view
of name resolution, and especially name finding services -- Docker and
Kubernetes approach makes it at least order of magnitude easier.

Name finding is mostly a goal for 2nd year of the grant. In this year we
rewrote from scratch Ruby-based web service to make it compatible with future
scala-based name-finding algorithm, and to make it Docker-compatible.

Tight integration with other components of Global Names Architecture
--------------------------------------------------------------------

We had a workshop with Richard Pyle on coordinating efforts, and brining
together Global Name Usage Bank and our name resolution services. We coauthored
a new grant proposal with a main goal to populate GNUB with data. We are also
in the process of talks with Catalogue of Life to connect CoL taxonomic
services with name resolution, name finding services and with GNUB.
