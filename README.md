# lucene-solr-4.10.4
How to build Lucene/Solr 4.10.4 on Linux on POWER LE (RHEL 7.1, Ubuntu 14.04)

Lucene/Solr v4.10.4 will run without modification of the Apache sources.

To build clone the Apache Source: 

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
The Lucene/Solr test environment generates variable results, sometimes, but not always, with failures or errors. These errors/failures rarely exceed 2 tests. Repeated runs of the [individual tests that fail/error](https://wiki.apache.org/solr/TestingSolr) results in pass 100% of the time for all the failing/error cases.
