# lucene-solr-4.10.4
How to build Lucene/Solr 4.10.4 on Linux on POWER LE (RHEL 7.1, Ubuntu 14.04)

Lucene/Solr v4.10.4 will compile and run on Power LINUX without modification of the Apache sources using the OpenJDK Java compiler and JVM.

The simplest way is to download the [Lucene](http://www.apache.org/dyn/closer.cgi/lucene/java/4.10.4) and [Solr](http://www.apache.org/dyn/closer.cgi/lucene/solr/4.10.4) source tarballs from Apache.

Alternatively clone the Apache Source from github: 

    git clone --branch lucene_solr_4_10_4 https://github.com/apache/lucene-solr.git


Create or edit file <code>~/.ant/ant.conf</code> to contain the line:

    rpm_mode=false

Initialize ivy with the command

    ant ivy-bootstrap

Then run the compile and test ant tasks

    ant compile
    ant test

logs held in: <code>./build/**/tests-report.txt</code>

##Test Results
The Lucene/Solr test environment generates variable results, sometimes, but not always, with failures or errors. These errors/failures rarely exceed 2 tests. Repeated runs of the [individual tests that fail/error](https://wiki.apache.org/solr/TestingSolr) results in pass 100% of the time for all the failing/error cases. We consider this a sign of instablility in the test suite and not a problem in the base product.
