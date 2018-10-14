## Distributed file system
10/14/2018

### Background
Today's machine learning research has created some new challenges to storage systems. Traditionally big data storage systems like HDFS can't satisfy these needs. To satisfy these new challenges, distributed file systems are needed.

### CephFS
Distributed file system which supports file, object and blob storage. It's is open-source, It has a fuse-fs client as well as a native ceph Linux kernel client. CephFS has good POSIX semantics support. In it's own words: when it comes to POSIX, `HDFS < NFS < CephFS < {XFS, ext4}`.

[CEPH AS A SCALABLE ALTERNATIVE TO HDFS ](https://www.usenix.org/system/files/login/articles/73508-maltzahn.pdf)

### GlusterFS
Very similar to CephFS in a lot of ways. Originally developed originally by Gluster, Inc. Then owned by RedHat. Interestingly, Inktank Storage (developer of CephFS) was also bought by RedHat. Key differences with CephFS can be seem from [here](https://drive.google.com/drive/folders/0B44EcgFDZNtXUUZnVUZkdTJzV0k)

### Alluxio
Memory-centric storage system for big data workloads.

* [[a16z] Tachyon: A File and Storage System for the Future of Computing](https://a16z.com/2015/03/17/tachyon/)
* [[Tech report] Alluxio: A Virtual Distributed File System](https://www2.eecs.berkeley.edu/Pubs/TechRpts/2018/EECS-2018-29.pdf)

### Amazon S3
Elastic relatively low cost storage. Works great if you already have compute instances on AWS. But performance will be limited of access S3 from remote. In this use case, it's performance usually will be lower than on-premise solutions.

### Colossus
GFS v2. Not much information is publicly available about it's details.

[Storage Architecture and Challenges](https://cloud.google.com/files/storage_architecture_and_challenges.pdf)

[Cluster-Level Storage @ Google How we use Colossus to improve storage efficiency](http://www.pdsw.org/pdsw-discs17/slides/PDSW-DISCS-Google-Keynote.pdf)

### HDFS
Good for traditional big data. Has a default block size of 128MB. Suitable for storing small amount of large files. Not suitable for storing a lot of small files. [Only append is possible](https://www.cs.cmu.edu/~srini/15-440/lectures/12-gfs_hdfs_spanner.pdf).

### Cassandra File System
Seems to be only used by Cassandra database. Like HDFS, tries to remove the single points of failure in the Hadoop NameNode.

[Cassandra File System Design](https://www.datastax.com/dev/blog/cassandra-file-system-design)

### Comparisons
* [Ceph vs Gluster vs Swift: Similarities and Differences](https://www.youtube.com/watch?v=fcnrkqbKDp0)
* [[wikipedia] Comparison of distributed file systems](https://en.wikipedia.org/wiki/Comparison_of_distributed_file_systems)
* [SMALL FILE PERFORMANCE ON DISTRIBUTED FILESYSTEMS - ROUND 2](https://www.jdieter.net/posts/2018/07/21/small-file-performance-on-distributed-filesystems-round-2/)
* [SnappyData vs Spark, Kudu, Alluxio & Cassandra: a Performance Benchmark](https://medium.com/@snappydata/snappydata-vs-spark-kudu-alluxio-cassandra-a-performance-benchmark-7df50cc2d2a7)
* [GFS / HDFS / Spanner](https://www.cs.cmu.edu/~srini/15-440/lectures/12-gfs_hdfs_spanner.pdf)
* [Apache Ignite vs Alluxio: Memory Speed Big Data Analytics](https://www.slideshare.net/Hadoop_Summit/apache-ignite-vs-alluxio-memory-speed-big-data-analytics)
* [Benchmarking Hadoop performance on different distributed storage systems](https://aaltodoc.aalto.fi/bitstream/handle/123456789/17713/master_Mukherjee_Alapan_2015.pdf?sequence=1&isAllowed=y)
* [BENCHMARKING APACHE SPARK WITH CASSANDRA, KUDU, ALLUXIO, SPARK CACHE AND SNAPPYDATA](https://www.snappydata.io/blog/snappydata-spark-kudu-alluxio-cassandra-performance-benchmark)

### Other related articles
* [Analyzing Google File System and Hadoop Distributed File System](https://scialert.net/fulltext/?doi=rjit.2016.66.74)
* [Distributed File Systems](http://www.engr.colostate.edu/ECE658/2013/onlinepresentation/Prabhakaran/Prabhakaran.pdf)
* [Linux Clusters Institute:High Performance Storage](http://www.linuxclustersinstitute.org/workshops/archive/21st/files/hpc_storage.pdf)
	* Note: [INTEL SHUTS DOWN LUSTRE FILE SYSTEM BUSINESS](https://www.nextplatform.com/2017/04/20/intel-shuts-lustre-file-system-business/)
