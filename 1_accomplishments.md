Goals (JUST FOR INFORMATION)
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
success to the project. When the grant had been written we hoped to employ
programmers and system administrators of Encyclopedia of Life (EOL) Project.
By the time of funding EOL team had decreased to two programmers, and we needed
to find other high quality professionals. During our first round of hiring we
were not successful. However, Dmitry Mozzherin aquired the necessary systems
administration skills (in part by moving the EOL to the Smithsonian) and we
were also able to employ an advanced developer with experience in Scala.
Taxonomical and nomenclatural knowledge is provided by former lead coordinator
of Global Names project -- David Patterson. Ultimately we were able to get high
quality experts for all important aspects of our work.

Selection of a programming language platform
--------------------------------------------

Advances in CPU manufacturing in the recent years created a need for
multiprocess, multi-threaded programming solutions. Our choice for a
programming language narrowed down to 2 languages -- Go and Scala. Both are
created for modern multi-processor, connected to network computers, both are
fast, compiled languages. In the end we chose Scala, because it is based on
Java Virtual Machine environment. That means that the code we write in Scala
can be used in a wide variety of JVM-compatible languages -- Java, Scala, R,
Jython, JRuby.  It also allows us to take advantage of Spark -- a "Big
Data"-oriented multiprocessor, multi-computer framework.

Planning
--------

We developed the roadmap based on Scala, which includes the following major
steps:

  1. Creation of Scala-based parser for scientific names
  2. Creation of Scala-based name index, name resolution service
  3. Creation of Scala based name-finding service based on name
     parsing algorithm, and names selected from texts using heuristic and
     machine learning techniques.

Programming
-----------

The goals of the grant heavily depend on programming. Alexander Myltsev, our
primary Scala developer had been able to lead the technical aspects of the project. He
made significant progress in developing the required libraries, tools and services.
Dmitry Mozzherin had been working together with Alexander, writing the Scala-based
parser, rewriting the name finding code, and creating a cross-mapping tool for
lists of scientific names.

Writing Scientific Papers
-------------------------

Our team is preparing 3 papers for publication in biodiversity
informatics journals.

Community building
------------------

Dmitry Mozzherin participated in writing a proposal for the Phylotastic project,
and now provides technical, managerial and programming service to the project
(NSF Avard Number #1458572). We are collaborating with OpenTree to get crosslinking
services and solutions implemented. We rewrote the
http://globalnames.org page to clearly state the goals of our project and to
introduce the tools we built. The site now includes a blog to convey news of our
progress. We also use Twitter to disseminate information.  We participated
in a number of hackathons, and workshops organized by Catalogue of Life,
iDigBio, Global Names Architecture, and the University of Arisona.

Dmitry Mozzherin was invited to a position at University of Illinois with the
Species File Group team, where he started cooperation with one of the leading
taxonomic projects -- Catalogue of Life, and with the projects of the SFG that
presently supports individuals in over 60 projects biodiversity informatics
projects. Dmitry became part of the Global Team of Catalogue of Life. We
continue to work closely with Encyclopedia of Life project.

System administration
---------------------

Moved Global Names to University of Illinois, set up servers, operating
systems, Chef, Docker, CoreOS, Kubernetes on the (re)built cluster.

Specific Objectives
===================

1. Creation of scalable, stable, high quality services in the Scala language

2. Reworking of algorithms used in the services

3. Development of approaches which would make our services easy to install locally

4. Integration with other components of Global Names Architecture

5. Integration with the Catalogue of Life, exploration of use cases for our
services

Significant Results
=====================

Scalable, stable, production level name services
------------------------------------------------

We used our existing prototype name parsing, finding, and resolving projects as a
guideline for the creation of new, faster, and scalable services written primarily in Scala.

In the first year we developed a production-ready scientific name parsing library
-- gnparser. The library went through 3 official releases. To our knowledge it
is a state of the art parser with the highest precision and recall for parsing
scientific names. It is able to parse 30 million names per one CPU per hour,
which is 10 times faster than our Ruby-based parser. Also it scales linearly up
to 4 processors, which means we are able to parse 120 million names an hour
very cost-effectively. Taking in account increased scalability, throughput for
name parsing increases by 2 orders of magnitude removing previously existing
bottlenecks in performance. We wrote extensive documentation for the parser, and
developed examples of how to use it in 5 different programming languages, made it
available for the Spark platform, created TCP/IP socket and REST services, as well
as command line application.

We are in the process of developing a Scala based name index and name resolution
service. We developed a proof of concept version so far. It is heavily based on a
very fast name parser, and we hope to be able to process 1000 names in less
than a second. We also created an architecture which should withstand massive load
on our servers.

Rework of underlying algorithms for name finding, resolution, reconciliation
---------------------------------------------------------------------------

We rewrote our name parsing algorithm. We still use the Parsing Expression Grammar
approach, the same we used for our popular Ruby-based parser.  We are in the
process of dramatically increasing the speed of name resolution algorithms.

We won participation as mentors in Google Summer of Code in 2015, and used it
to create novel machine learning approaches to estimate the quality of
scientific names

Simplify creation of local names services
-------------------------------------------------------------------

We moved to Linux containers to increase the scalability and at the same
time hugely simplify installation of our products in local environments. We
moved all our production services to the Docker platform which allows to install
each of our services with just one command.

We are also in the process of configuring CoreOS cluster which together with Open
source project Kubernetes developed by Goggle and used by Google internally to
create a massive fault tolerant system for running our services. We
successfully tried this approach on Google Engine Cloud first and now we are
implementing it for bare-metal machines in the University of Illinois Advanced
Computing center.

Papers in peer review journals
------------------------------

Paper "Challenges with using names to link digital biodiversity information"
submitted to ZooKeys and in the process of incorporating suggestions from
reviewers

Paper "gnparser: A powerful scientific name parser based on parsing expression
grammars" is on the final stages for submission to BMC Bioinformatics

Paper "gn-crossmap: A Tool to Verify Scientic NamesChecklists" is in
preparation

Tight integration with other components of Global Names Architecture
--------------------------------------------------------------------

We had a workshop with Richard Pyle on coordinating efforts, bringing
together the Global Name Usage Bank and our name resolution services. We coauthored
a new grant proposal with a main goal to populate GNUB with data.

Integration with Catalogue of Life
----------------------------------

This year we had a breakthrough in relationship with Catalogue of Life
taxonomic database. We consider it to be extremely important to coordinate our
efforts with Catalogue of Life, as the project is manually curated collection
with an aim to aggregate currently names for "valid" taxonomic concepts along
with their synonyms for all species on Earth. Our algorithmic approach in name
parsing, lexical reconciliation, nomenclatural intelligence (through GNUB) is
naturally extended by the manually curated list of currently used species
names. We are very excited about cooperation with Catalogue of Life. Dmitry
Mozzherin is working close with their team.

Key outcomes and other achievements
===================================

1. Creation of gnparser -- an accurate, scalable, fast parsing library and service

2. Exploration of machine learning techniques to estimate the quality of
scientific names and collections of scientific names

3. Participation in Phylotastic project, providing a name-finding/resolution
services for creation of phylogenetic trees from lists, photographic images,
creation of mobile applications which are able to recognize and scientific
names, find useful information about species etc.

4. Creation of computing cluster, acquiring experience in usage of Chef, Docker,
Linux Containers, Kubernetes technologies to make highly scalable, fault
tolerant name services.

5. Migration of Global Names services from Marine Biological Laboratory to
University of Illinois

6. Rewriting of name finding service making it Docker compatible, future proof,
well tested, ready for Scala name-finding libraries.

7. Work with Catalogue of Life, on tight integration of our services

8. Finding a new stable home for Global Names project at University of
Illinois.

9. Creation of sysopia -- a computer cluster monitoring program developed by a
student during Google Summer of Code.

10. Creation of gn-crossmapper -- an application for comparison large lists of
scientific names between two different datasets.


What opportunities for training and professional development has the project provided?
======================================================================================

We participated in Google Summer of Code in 2015 and mentored two students in
machine learning techniques and creation of web-based system administration
tools

We participated in Phylotastic project and in training students about
programming techniques, test-driven development, agile programming techniques.
Also we trained students in using Global Names tools.

We participated in 3 hackathons and 2 workshops sharing the approaches we use, and
learning from other groups about usage of Scala and Spark technologies.

How have the results been disseminated to communities of interest?
==================================================================

We disseminated results of our research and development through video meetings,
participation in workshops and hackathons, publishing news about developments
in the Global Names project, posting messages on GitHub, Gitter, Twitter
