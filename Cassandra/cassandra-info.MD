## **BigNotes on Cassandra**

### Basics

- **Project Name** : Apache Cassandra
- **Version**  
	- Latest Version: Apache Cassandra 3.9 [[cassandra][]]
	- Stable version: Apache Cassandra 3.0  
- **License** : Apache License 2.0 
- **Released on**  
	- Oldest Supported Version: v.2.1.6; Latest release on 2016-10-10 [[cassandra-release][]]
	- Latest Version Release: v.3.9; Latest release on 2016-09-29

### Organizations and Backers

- **Organization that made it** : 
	- Organization : Facebook
	- Original Authors : Avinash Lakshman and Prashant Malik [[cassandra-wikipedia][]]
- **Backed by known companies / individuals** :
	- Companies that actively provide Cassandra as a service and contribute to it 
    	- DataStax
    	- Impetus Technologies
    	- Instaclustr
    - Companies that use Cassandra extensively for analytics and user interface
    	- Apple 
    	- Discord 
    	- Facebook (for Instagram)
    	- Netflix
    	- Twitter
    	- Reddit
    	- Soundcloud
    	- Digg

- **Size of the community** :
	No solid numbers. IRC Link is down as well.

### State of the project

- **Is the product in active development?** : (How many issues closed recently, How many merge requests closed recently, How many commits happened recently)
- **Is this project safe to put in production?** : Production Ready [[Instructions for Production Settings - Linux][]]
- **Are there major known production deployments of this project?** : Yes, used as both OpenSource and Commercial Product by Datastax [[datastax][]]
- **Known big deployments and numbers** :
	- *Apple*: Uses 75,000 nodes storing over 10 PB of data ; Largest known cluster of 1000 nodes ; Used for iMessage
	- *Netflix*: Uses 2,500 nodes storing 420 TB with over 1 trillion requests per day ; Used for Netflix Data Benchmarking [[netflix-dbench][]]
	- *eBay*: Uses over 100 nodes storing transactional data of over 250 TB ; 500M+ Read/Writes per day ; Social Signals, Fraud Detection and Logging of Servers and Notifications [[datastax-ppt-ebay][]]


### Business Objectives

- **What is the use-case?** :
	Apache Cassandra is a highly scalable, high-performance distributed database designed to handle large amounts of data across many commodity servers, providing high availability with no single point of failure. It is a type of NoSQL database. [[cass-intro][]]

- **Plays well with what other relevant tools** :  
	Apache Cassandra works really well with most tools and projects in the Apache Big Data Stack viz.
	- Hadoop
	- Pig
	- Hive
	- Oozie
	- Spark
	- Integration with programming languages using drivers
		- Python
		- NodeJS
		- Ruby
		- GoLang
		- PHP
		- Java
		- C++

- **Plays well with what proprietary tools** : 
	DataStax as a provider has created a few proprietary tools, that Apache Cassandra integrates well with 
	- DataStax DevCenter
	- DataStax OpsCenter

- **What are the languages supported?** :  
	Essentially, use CQL (Cassandra Query Language) for operations on its database. Drivers have been made to support CQL over other Programming Languages, such as Python, PHP, C++, Java, GoLang.
	- *GoCQL* [[gocql][]] : 873 stars; Allows Cluster Management, Query Tracking and Full Support for different Cassandra Versions.
	- *NodeJS DataStax Cassandra Driver* [[node-datastax-cass][]] : 520 stars ; NodeJS support for CQL, supports Prepared statements, auto node discovery and load balancing.
	- *Java DataStax Cassandra Driver* [[java-datastax-cass][]] : 745 stars ; Java Support for CQL, similar capabilities as Node Driver.
	- *Python DataStax Cassandra Driver* [[python-datastax-cass][]] : 636 stars ; Python Support for CQL, similar capabilities as Node Driver.
	- *C++ DataStax Cassandra Driver* [[cpp-datastax-cass][]] : 202 stars ; Provides all features provided by Node Driver. Adds support for SSL and others.
	- *PHP DataStax Cassandra Driver* [[php-datastax-cass][]] : 240 stars ; Wrapper for C++ Datastax Cassandra Driver.

- **Competitors in the same space** :
	According to surveys, the top four NoSQL databases in the market are MongoDB, Apache HBase, CouchDB and Apache Cassandra. Of these, we believe CouchDB is less Distributed oriented, in terms of the fact that it uses database per node, for replication, unlike true replication per object for the others on this list, heavily reducing the impact that adding new nodes should have on the performance. [[top3nosql][]] We will describe the competition using parameters as defined in this benchmark study by Endpoint Solutions. [[benchmark][]]

	- *HBase* : [[hbase][]]
		HBase is a sister-project of Apache Cassandra, in the way that they are both based on Google's BigTables paper in 2006. However, they differ in certain key factors in terms of the way they work. Cassandra handle inter-processor communication using Gossip Protocol, in-built into the Cassandra package, itself. HBase needs to use Zookeeper, another distributed application to handle IPC. HBase has atomicity, in terms of row-level consistency, while, Cassandra lacks the same, as a result of which, timestamp conflicts may lead to data having cell-level inconsistencies. HBase uses co-processor mechanism to evaluate user code along with its own code, akin to the RDBMS' features like stored procedures (triggers have been added as of 2.1/2.2). However [[benchmark-datastax][]] as a study shows Cassandra to be a clear leader in terms of performance scaling with respect to number of nodes, especially in terms of read-heavy jobs.

	- *MongoDB* : [[mongodb][]] 
		MongoDB is fairly similar to Apache Cassandra in the fact that they are both NoSQL databases and are weak engines, in terms of enforcing a replacement to RDBMS' ACID properties. Cassandra has a richer ecosystem to sit in. MongoDB on the other hand, provides a richer data model, a more flexible query model (by using secondary indices as a first class supported data type) and perform in-tool aggregation using in-built aggregation framework, for which Cassandra needs Spark and/or Hadoop. Cassandra on the other hand, is way better at scaling write-heavy jobs and its architecture of maintaining multiple, critical yet not absolutely necessary seed nodes for communication, ensures no-downtime, even when masters go down. 

- **Paid vs OpenSource comparison** :
	While, Apache Cassandra is free-to-use and Open Source under Apache 2.0 licence, a few major contributors on the project such as, DataStax, Impetus and InstaClustr provide Paid Services for implementations of Apache Cassandra with a few custom, propreitary tools built on top of the vanilla Cassandra Installation.

	These tools mostly provide ways to either automate the installation and monitoring of the Apache Cassandra Clusters, or provide rich User Interface as a substitute to the CQLSH of the Apache Cassandra installation, for better visualization of queries and their results as per user demand.

- **Is this part of any ecosystem?** :  
	Cassandra can integrate into a number of big-data ecosystems. It may be typically used to absorb data pulled in from various social data sources into Hadoop or Spark Processing Engine Clusters, which may themselves be managed by YARN or Mesos. Cassandra may then be used alone or in conjunction with a traditional RDBMS such as MySQL or Oracle, to establish a structure where updates are done on the RDBMS and the updates are pushed as a batch onto the Cassandra database for large, analytics-based queries.

### What weight class do you fight in?

- **What is too big for tool scenario** : -- When would you definitely not use this tool
- **What are good data loads that this product handles?** :
- **What is overkill scenario?** : -- When this tool is just too big for the problem and shouldn't be used


### Comparison and Benchmarks

- **Comparitive Benchmarks** :
	
	Both DataStax (provider of Cassandra Implementation as a Service) and MongoDB, two of the leading NoSQL databases, have done their surveys which include each other as well as a couple of other NoSQL providers as highlighted in the Competitors section above.

	- *YCSB and its parameters*
	
		Both the benchmark studies use YCSB (Yahoo! Cloud Servicing Benchmark) for testing the Node Clusters of the databases. 
		
		- YCSB Parameters for [[benchmark-datastax][]]
			-  Server Configuration : 30.5 GB RAM, 4 CPU cores, and a single volume of 800 GB of SSD local storage.
			-  Client Configuration : 7.5GB RAM, 4 CPU cores.
			-  Ubuntu 14.04 LTS + Oracle Java 7
			-  Cassandra v.2.1.0
			-  MongoDB v.3.0
			-  Data input : 500 million records per data node. Size of each data item = 100 bytes.
			-  9 million operations. 
			-  Maximum Execution time : Capped at 60 minutes.
			-  Five Types of Workloads 
				-	A : 50% Read; 50% Update 
				-	B : 95% Read; 5% Update
				-	F : 50% Read; 50% Read-Modify-Write
				-	C : 60% Read; 25% Update; 10% Insert; 5% Scan
				-	D : 90% Insert; 10% Read

		- YCSB Parameters for [[benchmark-mongo][]]
			-  Server Configuration : 96 GB RAM, 2x6 CPU cores, and 2 x 960 GB of SSD local storage.
			-  Ubuntu 14.04 LTS + Oracle Java 7
			-  Cassandra v.2.1.2
			-  MongoDB v.3.0.1
			-  Data input : 20 million records per data node.
			-  20 million operations.
			-  Maximum Execution time : Capped at 15 minutes.
			-  Two types of Workloads
				- A : 50% Read; 50% Update
				- B : 95% Read; 5% Update

	- *Observations of the Test*

		The test results are too huge to be simply demonstrated here in this document. They can be viewed in the reports of each of the benchmark tests, [[benchmark-mongo][]] and [[benchmark-datastax][]].

	- *Conclusions from the tests*

		-  In terms of update latency, Cassandra has all of its updates around the 20-40ms mark, which is higher than the peak update latency that MongoDB achieves at 5-10ms. However, MongoDB has a widely-spread distribution. So, if you need a really low latency for as long as possible, but are tolerant to higher latencies, MongoDB would be preferred. However, if you need a cap on the highest value latencies can have, Apache Cassandra is a better bet. [[benchmark-mongo][]]

		- The huge difference in the throughput conclusions and test results of the two benchmark studies, reflect the effect of optimizing the databases to particular setup and resource allocation. Higher the RAM usage and CPU processing power, the better MongoDB performs than Apache Cassandra. However, it also reflects that Apache Cassandra can perform the same tasks MongoDB does with lesser resources.


### High Points

- **What's good about Cassandra?** :
	- Cassandra excels at online transactions, also known as real time transactions: requests that need to fully execute in a small amount of time that the end user views as real time. In other words, queries need to execute at the single millisecond level, not the hundreds or thousands of milliseconds area. With Cassandra’s multiple caching levels, your data can be served incredibly quickly. Every write is fast with Cassandra thanks to the log-structured storage design, and each write is persisted with a commit log. Cassandra is an excellent choice when downtime or data loss is unacceptable.

	- Cassandra does well in the other area of data management – analytics. With the current release, MapReduce is supported across your stored data. MapReduce is an algorithm popularized by Google that allows for analytical queries to be run on large data sets across large numbers of servers in parallel. It’s not real time – typical jobs can take minutes if not hours – but it’s capable of processing gigantic data sets to scour your data for the information you need.

	- Because Cassandra provides both online and analytical solutions, you can use a single technology to accomplish the majority of your data needs. This is beneficial for both development and operational teams because it reduces the number of systems you need. Given that Cassandra has shown to work at scale, you know you can trust it to perform well as your needs grow.
	[[cass-good][]]



### Red Flags
- **Reasons for concern** :
	
	While, Cassandra is being used in huge clusters by various influential organizations, it has its fallacies. We have listed a few down below:

	- *No support for joins, subqueries*: 

	Unlike traditional RDBMS, Cassandra does not support joins for searching. Searches are limited to primary key-based searches. This means, limited support for specific queries without use of Specialized Query processing engines, such as Spark SQL or Hive.

	- *Not recommended for Aggregations*:

	While, Cassandra is heavily used for analytics, the lack of in-tool native aggregation support means, it is not recommended for aggregations, and such tasks, are best left to overlaying query processing engines.

	- *Lack of Row level Consistency*:

	If timestamp clash occurs during insert or update phase (known as timestamp tie), value for each cell in a row is decided independently, using a logic known as "Lexical larger value". However, this means, that dropping off certain cells in a row and updating other cells in a row, might lead to semantic inconsistencies in the information implied by the entire row taken together. This is inherently, due to the columnar nature of Cassandra Database Operations.

- **Vulnerabilities** :
	
	Only one serious vulnerability has been listed for Apache Cassandra. This is only valid for old releases. Beware while installing old versions of the Tool.

	The default configuration in Apache Cassandra 1.2.0 through 1.2.19, 2.0.0 through 2.0.13, and 2.1.0 through 2.1.3 binds an unauthenticated JMX/RMI interface to all network interfaces, which allows remote attackers to execute arbitrary Java code via an RMI request. [[cassandra-vuln][]]


### Reviews and Articles
- **Review articles** :

	- "Cassandra, hands-on review, after 4 years of serious use" [[trust-radius][]]
	- "Cassandra Mythology" [[cass-myth-buster][]]
	- Other Reviews [[review-g2crowd][]]

- **Praise articles** :

	- "Five Reasons to use Cassandra" [[5-reasons][]]
	- "Cassandra lowers the barriers to big data" [[infoworld][]]
	- "Fulfilling Promise: Apache Cassandra" [[opencredo][]]

- **Complain articles** :  

	- WAT - Cassandra [[wat-cass][]]
	- "Why I decided not to use Cassandra" [[bozho-blog][]] (Authored by the creator of Helenus - first NodeJS driver for Cassandra)

### Other Cool Stuff

- **Other Projects by the Creators** :
	- Avinash Lakshman (Original Author of Cassandra) is also the author of Apache Dynamo [[dynamo][]]

- **Installation Procedure** :
	Installing Cassandra on a Single Node Cluster is given in the following link [[install-cassandra-single-digitalocean][]]

- **Hello world** :

	Type cqlsh in your shell to create an instance of cqlshell where you can make cql queries

	`cqlsh > ___`

	First we establish a namespace
	
	`cqlsh > CREATE KEYSPACE test WITH replication = {'class': 'SimpleStrategy', 'replication_factor' : 1};`

	Use the keyspace

	`cqlsh > CREATE KEYSPACE test WITH replication = {'class': 'SimpleStrategy', 'replication_factor' : 1};`

	Create a table

	`cqlsh > CREATE TABLE test1(emp_id int PRIMARY KEY, emp_name text, emp_city text);`

	Display the table

	`cqlsh > SELECT * FROM test1`



[Cassandra]: <http://cassandra.apache.org> "Apache Cassandra Website"
[cassandra-release]: <http://cassandra.apache.org/download/> "Apache Cassandra Downloads and Releases"
[dynamo]: <https://aws.amazon.com/dynamodb/> "Apache DynamoDB"
[Instructions for Production Settings - Linux]: <https://docs.datastax.com/en/landing_page/doc/landing_page/recommendedSettingsLinux.html> "Apache Cassandra Linux Production Ready Settings"
[cassandra-wikipedia]: <https://en.wikipedia.org/wiki/Apache_Cassandra> "Apache Cassandra on Wikipedia"
[netflix-dbench]: <https://github.com/Netflix/ndbench> "Netflix Data Benchmarking Architecture"
[datastax-ppt-ebay]: <http://www.datastax.com/wp-content/uploads/2012/08/C2012-BuyItNow-JayPatel.pdf> "eBay Use-Case of Cassandra"
[datastax]: <http://www.datastax.com/> "Datastax Intro"
[gocql]: <https://gocql.github.io/> "GoCQL Github IO"
[node-datastax-cass]: <https://github.com/datastax/nodejs-driver> "DataStax Driver for CQL over Node"
[java-datastax-cass]: <https://github.com/datastax/java-driver> "DataStax Driver for CQL over Java"
[php-datastax-cass]: <http://datastax.github.io/php-driver/> "DataStax Driver for CQL over PHP"
[cpp-datastax-cass]: <http://datastax.github.io/cpp-driver/> "DataStax Driver for CQL over C++"
[python-datastax-cass]: <https://github.com/datastax/python-driver> "DataStax Driver for CQL over Python"
[cass-intro]: <https://www.tutorialspoint.com/cassandra/cassandra_introduction.htm> "Introduction to Apache Cassandra"
[cass-good]: <http://www.datastax.com/dev/blog/what-cassandra-good> "what is good about using cassandra"
[mongodb]: <https://www.mongodb.com/> "MongoDB Introduction"
[hbase]: <https://hbase.apache.org> "HBase Introduction"
[top3nosql]: <http://www.infoworld.com/article/2848722/nosql/mongodb-cassandra-hbase-three-nosql-databases-to-watch.html> "top three nosql databases"
[benchmark-datastax]: <https://www.datastax.com/wp-content/themes/datastax-2014-08/files/NoSQL_Benchmarks_EndPoint.pdf?2> "Benchmarking of NoSQL databases by DataStax"
[benchmark-mongo]: <http://info-mongodb-com.s3.amazonaws.com/High%2BPerformance%2BBenchmark%2BWhite%2BPaper_final.pdf> "Benchmarking White paper of NoSQL databases by MongoDB"
[couchdb]: <http://www.couchbase.com/nosql-databases> "CouchDB introduction"
[install-cassandra-single-digitalocean]: <https://www.digitalocean.com/community/tutorials/how-to-install-cassandra-and-run-a-single-node-cluster-on-ubuntu-14-04> "Install Cassandra Standalone"
[cassandra-vuln]: <https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-0225> "Cassandra Vulnerability on CVE - DB"
[trust-radius]: <https://www.trustradius.com/reviews/cassandra-2015-10-16-15-53-59> "Cassandra hands-on Review"
[infoworld]: <http://www.infoworld.com/article/2610676/database/review--cassandra-lowers-the-barriers-to-big-data.html?page=2> "Info world cassandra Review"
[review-g2crowd]: <https://www.g2crowd.com/products/cassandra/reviews> "G2Crowd Reviews on Cassandra"
[5-reasons]: <http://exponential.io/blog/2015/01/13/5-reasons-why-you-should-use-cassandra/> "Five reasons to use cassandra"
[cass-myth-buster]: <https://www.infoq.com/articles/cassandra-mythology> "Busting Myths about Cassandra"
[opencredo]: <https://opencredo.com/fulfilling-promise-apache-cassandra/> "Fulfilling Promise: Apache Cassandra at OpenCredo"
[wat-cass]: <http://datanerds.io/post/WAT-cassandra-1/> "WAT - Apache Cassandra"
[bozho-blog]: <https://techblog.bozho.net/why-i-decided-not-to-use-cassandra/> "Bozho Blog"