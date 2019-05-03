---
layout: page
title: Documentation
permalink: /docs/
---


### Downloading

Get Tarql latest releases from the [dowloads page](https://github.com/tarql/tarql/releases) of the project.

Tarql runs on both Windows and Unix systems. It runs locally in a single machine --- all you need is to have `java` version 1.7 or above installed on your system, 
and configure `PATH`, or the `JAVA_HOME` environment variables pointing to the Java installation.

### Building from Source Code

Get the code from by forking the [Tarql GitHub Project](http://github.com/cygri/tarql).

{% highlight bash %}
~$ git clone https://github.com/cygri/tarql
{% endhighlight %}

Tarql uses Maven and there is an `assember.xml` file to package the code. To create executable scripts for Windows and Unix:

{% highlight bash %}
~$ mvn clean install -DskipTests
{% endhighlight %}

By doing that you will generate the folder `/target/appassembler/bin/` which contains the executables.

### Running the Examples

To run the examples you need to first create the executable scripts as explained in last point.

{% highlight bash %}
~$ cd tarql/target/appassembler
~$ sh bin/tarql --ntriples ../../examples/sample-2.sparql ../../examples/TechCrunchcontinentalUSA.csv
{% endhighlight %}

### Code Documentation

Java documentation is also available [here](/javadocs/index.html).

### Community

Mailing list: [tarql-mailing-list](https://groups.google.com/d/forum/tarql) <br>
Group email: [tarql@googlegroups.com](mailto:tarql@googlegroups.com)

#### Reporting Issues

If you'd like to report a bug in Tarql or ask for a new feature, open an issue on the [Tarql GitHub Project](https://github.com/cygri/tarql/issues). For general usage help, you should email the user [mailing list](https://groups.google.com/d/forum/tarql).

#### Contribute Code

You can contribute to the project submitting GitHub pull requests. Start by opening an issue for your change on the [Tarql GitHub Project](https://github.com/cygri/tarql/issues) (and make sure to search whether
there is an existing issue). Please use descriptive names in your pull requests. You can always check the code in the [https://github.com/cygri/tarql](https://github.com/cygri/tarql) repository.

Currently there are some points in the **TO DO** list listed below:

* Writing to file instead of stdout
* Allow feeding of triples from RDF files into the mapping process
* Optionally generate VoID/PROV triples
* Find a way of producing consistent blank nodes from strings (esp. in multiple CONSTRUCT clauses)
* Find a way of using the table multiple times, e.g.: `{ { SELECT ?author1 { TABLE } } UNION { SELECT ?author2 { TABLE } } }`
* Handle tables where repeated values within a column are omitted, maybe tarql:valueFromPreviousRow(?a))
* Support Excel files?
* Read input from stdin?
* Web service?


Last Update: {{ site.time | date: '%B %d, %Y' }}
