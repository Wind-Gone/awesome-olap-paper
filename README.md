# Awsome-OLAP-Paper
Welcome new PR, please conform to the committed rules: paperName(with link) [MeetingName Year]

If the paper has the open-source code, please supply its github links in Meeting.

- [Traditional-OLAP-Paper](#traditional-olap-paper)
  - [Query-Aware Database Generation](#query-aware-database-generation)
  - [Query Optimization](#query-optimization)
    - [Query Rewrite](#query-rewrite)
    - [Cardinality Estimation](#cardinality-estimation)
      - [Histogram](#histogram)
      - [Sampling](#sampling)
      - [Others](#others)
      - [Survey](#survey)
    - [Join Order](#join-order)
    - [Join Algorithms](#join-algorithms)
    - [Cost Model](#cost-model)
    - [View](#view)
    - [Survey](#survey-1)
    - [Index](#index)
  - [Query Exection](#query-exection)
  - [Query Compilation](#query-compilation)
  - [Logic Bugs Detection](#logic-bugs-detection)
  - [Storage](#storage)
  - [Proxy](#proxy)
  - [Data Loading](#data-loading)
  - [Database Kernel](#database-kernel)
  - [Others](#others-1)
    - [MVCC](#mvcc)
    - [HTAP](#htap)
      - [System Architecture](#system-architecture)
        - [Linear Consistency](#linear-consistency)
        - [Sequential Consistency](#sequential-consistency)
        - [Session Consistency](#session-consistency)
        - [Survey](#survey-2)
      - [Kernel Optimization](#kernel-optimization)
    - [Benchmark](#benchmark)
    - [Time Series](#time-series)
    - [Vector Data](#vector-data)
    - [OLTP](#oltp)
    - [AI4DB](#ai4db)
    - [Industry](#industry)

## Query-Aware Database Generation
1.  [QAGen: Generating Query-Aware Test Databases](https://cs.uwaterloo.ca/~tozsu/publications/other/sigmod07-final.pdf) [SIGMOD 07]
2.  [Generating Targeted Queries for Database Testing](https://dl.acm.org/doi/pdf/10.1145/1376616.1376668) [SIGMOD 08]
3. [Generating Databases for Query Workloads](https://dl.acm.org/doi/pdf/10.14778/1920841.1920950) [VLDB 10]
4. [Data Generation using Declarative Constraints](https://dl.acm.org/doi/pdf/10.1145/1989323.1989395) [SIGMOD 11]
5. [MyBenchmark: generating databases for query workloads](https://link.springer.com/article/10.1007/s00778-014-0354-1) [VLDB 14]
6. [Scalable and Dynamic Regeneration of Big Data Volumes](https://openproceedings.org/2018/conf/edbt/paper-114.pdf) [EDBT 18]
7. [Touchstone: Generating Enormous Query-Aware Test Databases](https://www.usenix.org/system/files/conference/atc18/atc18-li-yuming.pdf) [OSDI 18]
8. [Projection-Compliant Database Generation](https://www.vldb.org/pvldb/vol15/p998-sanghi.pdf) [VLDB 22]
9.  [SAM: Database Generation from Query Workloads with Supervised Autoregressive Models](https://dl.acm.org/doi/pdf/10.1145/3514221.3526168) [[SIGMOD 22](https://github.com/Jamesyang2333/SAM)]

## Query Optimization
1. [Sampling-Based Query Re-Optimization](https://pages.cs.wisc.edu/~wentaowu/papers/sigmod16-reoptimization.pdf) [SIGMOD 16]
2. [Kepler: Robust Learning for Parametric Query Optimization](https://dl.acm.org/doi/pdf/10.1145/3588963) [SIGMOD 23]
3. [Rethink Query Optimization in HTAP Databases](https://dl.acm.org/doi/pdf/10.1145/3626750) [SIGMOD 24]

### Query Rewrite
1. [QueryBooster: Improving SQL Performance Using Middleware
Services for Human-Centered Query Rewriting](https://www.vldb.org/pvldb/vol16/p2911-bai.pdf) [VLDB 23]
2. [SlabCity: Whole-Query Optimization using Program Synthesis](https://dl.acm.org/doi/pdf/10.14778/3611479.3611515) [VLDB 23]
3. [Proving Query Equivalence Using Linear Integer Arithmetic](https://dl.acm.org/doi/pdf/10.1145/3626768) [SIGMOD 24]



### Cardinality Estimation
#### Histogram
1. [Equi-Depth Histograms For Estimating Selectivity Factors For Multi-Dimensional Queries](https://dl.acm.org/doi/pdf/10.1145/971701.50205) [None 87]
2. [Optimal Histograms for Limiting Worst-Case Error Propagation in the Size of Join Results](https://dl.acm.org/doi/pdf/10.1145/169725.169708) [ACM Transactions on Database Systems 93]
3. [Independence is good: Dependency-based histogram synopses for high-dimensional data](https://dl.acm.org/doi/pdf/10.1145/376284.375685) [SIGMOD 01]
4. [STHoles: a multidimensional workload-aware histogram](http://www.cs.columbia.edu/~gravano/Papers/2001/sigmod01b.pdf) [SIGMOD 01]
5. [A multi-dimensional histogram for selectivity estimation and fast approximate query answering](https://dl.acm.org/doi/pdf/10.5555/961322.961374) [CASCON 03]
6. [The history of histograms (abridged)](https://www.vldb.org/conf/2003/papers/S02P01.pdf) [VLDB 03]
7. [ISOMER: Consistent histogram construction using query feedback](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=55708905fb9ecd1ffa2f41638410f672147ccdaa) [ICDE 06]
8. [Join Over Histograms](http://www.adellera.it/static_html/investigations/join_over_histograms/JoinOverHistograms.pdf) [Alberto Dell'Era 07]
9. [Improving accuracy and robustness of self-tuning histograms by subspace clustering](https://dbis.ipd.kit.edu/download/MineClusSTHoles_-_Minor_Revision.pdf) [ICDE 16]
10. [LHist: Towards Learning Multidimensional Histogram for Massive Spatial Data](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9458896) [ICDE 21]
#### Sampling
1. [Two-Level Sampling for Join Size Estimation](https://15721.courses.cs.cmu.edu/spring2023/papers/18-costmodels/p759-chen.pdf) [SIGMOD 17]
2. [Combining Aggregation and Sampling (Nearly) Optimally for Approximate Query Processing](https://arxiv.org/pdf/2103.15994.pdf) [SIGMOD 21]
#### Others
1. [Access path selection in a relational database management system](https://courses.cs.duke.edu/compsci516/cps216/spring03/papers/selinger-etal-1979.pdf) [SIGMOD 79]
2. [Approximating multi-dimensional aggregate range queries over real attributes](https://dl.acm.org/doi/pdf/10.1145/335191.335448) [SIGMOD 00]
3. [Selectivity estimators for multidimensional range queries over real attributes](https://cs.gmu.edu/~carlotta/publications/vldb090.pdf) [VLDB 05]
4.  [Plan Bouquets: Query Processing without Selectivity Estimation](https://dsl.cds.iisc.ac.in/~course/DBMS/papers/planBouquet.pdf) [SIGMOD 14]
5.  [Exact Cardinality Query Optimization with Bounded Execution Cost](https://dl.acm.org/doi/pdf/10.1145/3299869.3300087) [SIGMOD 19]
6.  [JoinSketch: A Sketch Algorithm for Accurate and Unbiased Inner-Product Estimation](https://yangtonghome.github.io/uploads/JoinSketch_2023.pdf) [SIGMOD 23]
7.  [Efficient and Effective Cardinality Estimation for Skyline Family](https://dl.acm.org/doi/abs/10.1145/3588958) [SIGMOD 23]

#### Survey
1. [Analyzing the Impact of Cardinality Estimation on Execution Plans in Microsof SQL Server](https://www.vldb.org/pvldb/vol16/p2871-dutt.pdf) [VLDB 23]

### Join Order
1. [Join Order Selection with Deep Reinforcement Learning: Fundamentals, Techniques, and Challenges](https://www.vldb.org/pvldb/vol16/p3882-yan.pdf) [VLDB 23]
2. [Efficiently Computing Join Orders with Heuristic Search](https://dl.acm.org/doi/pdf/10.1145/3588927) [SIGMOD 23]
3. [Ready to Leap (by Co-Design)? Join Order Optimisation on Quantum Hardware](https://dl.acm.org/doi/pdf/10.1145/3588946) [SIGMOD 23]
4. [Quantum-Inspired Digital Annealing for Join Ordering](https://www.vldb.org/pvldb/vol17/p511-schonberger.pdf) [[VLDB 24](https://github.com/lfd/vldb24)]

### Join Algorithms
1. [Massively Parallel Sort-Merge Joins in Main Memory Multi-Core Database Systems](https://15721.courses.cs.cmu.edu/spring2023/papers/12-sortmergejoins/p1064-albutiu.pdf) [VLDB 12]
2. [Leapfrog Triejoin: a worst-case optimal join algorithm](https://arxiv.org/pdf/1210.0481.pdf) [International Conference on Database Theory 12]
3. [An Experimental Comparison of Thirteen Relational Equi-Joins in Main Memory](https://15721.courses.cs.cmu.edu/spring2018/papers/19-hashjoins/schuh-sigmod2016.pdf) [SIGMOD 16]
4. [Worst-Case Optimal Join Algorithms: Techniques, Results, and Open Problems](https://arxiv.org/pdf/1803.09930.pdf) [SIGMOD 18]
5. [Adopting Worst-Case Optimal Joins in Relational Database Systems](https://www.vldb.org/pvldb/vol13/p1891-freitag.pdf) [VLDB 20]
6. [Free Join: Unifying Worst-Cast Optimal and Traditional Joins](https://arxiv.org/pdf/2301.10841.pdf) [arXiv 23]

### Cost Model
1. [LEO – DB2’s LEarning Optimizer](https://15721.courses.cs.cmu.edu/spring2023/papers/18-costmodels/stillger-vldb2001.pdf) [VLDB 11]
2. [Predicting query execution time: are optimizer cost models really unusable?](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6544899) [ICDE 13]
3. [Towards Predicting Query Execution Time for Concurrent and Dynamic Database Workloads](https://pages.cs.wisc.edu/~wentaowu/papers/vldb13-prediction-cc.pdf) [VLDB 13]
4. [Forecasting the cost of processing multi-join queries via hashing for main-memory databases](https://arxiv.org/pdf/1507.03049.pdf) [SoCC 15]
5. [Query Performance Prediction for Concurrent Queries using Graph Embedding](http://www.vldb.org/pvldb/vol13/p1416-zhou.pdf) [VLDB 20]
6. [Efficient Deep Learning Pipelines for Accurate Cost Estimations Over Large Scale Query Workload](https://arxiv.org/pdf/2103.12465.pdf) [arXiv 21]
7. [Rethinking Learned Cost Models: Why Start from Scratch?](https://dl.acm.org/doi/pdf/10.1145/3626769) [SIGMOD 24]


### View
1. [Foreign Keys Open the Door for Faster Incremental View Maintenance](https://dl.acm.org/doi/pdf/10.1145/3588720) [SIGMOD 23]

### Survey
1. [How Good Are Query Optimizers, Really?](https://www.vldb.org/pvldb/vol9/p204-leis.pdf) [VLDB 15]
2. [Cardinality Estimation: An Experimental Survey](https://www.vldb.org/pvldb/vol11/p499-harmouch.pdf) [VLDB 17]
3. [A Survey on Advancing the DBMS Query Optimizer: Cardinality Estimation, Cost Model, and Plan Enumeration](https://arxiv.org/pdf/2101.01507.pdf) [VLDB 21]
4. [Have query optimizers hit the wall?](https://link.springer.com/article/10.1007/s00778-021-00689-y) [VLDB Journal 22]
5. [Cardinality Estimation in DBMS: A Comprehensive Benchmark Evaluation](https://dl.acm.org/doi/pdf/10.14778/3503585.3503586) [VLDB 22]
6. [Data dependencies for query optimization: a survey](https://link.springer.com/article/10.1007/s00778-021-00676-3) [VLDB Journal 22]
7. [Simple Adaptive Query Processing vs. Learned Query Optimizers:
Observations and Analysis](https://www.vldb.org/pvldb/vol16/p2962-zhang.pdf) [VLDB 23]

### Index
1. [SQL Server Column Store Indexes](https://15721.courses.cs.cmu.edu/spring2023/papers/04-olapindexes/p1177-larson.pdf) [SIGMOD 11]
2. [Column Sketches: A Scan Accelerator for Rapid and Robust Predicate Evaluation](https://15721.courses.cs.cmu.edu/spring2023/papers/04-olapindexes/hentschel-sigmod18.pdf) [SIGMOD 18]

## Query Exection
1. [MonetDB/X100: Hyper-Pipelining Query Execution](https://www.cidrdb.org/cidr2005/papers/P19.pdf) [CIDR 05] 
2. [Materialization Strategies in the Vertica Analytic Database: Lessons Learned](https://15721.courses.cs.cmu.edu/spring2023/papers/06-execution/shrinivas-icde2013.pdf) [ICDE 13] 
3. [Rethinking SIMD Vectorization for In-Memory Databases](https://15721.courses.cs.cmu.edu/spring2024/papers/06-vectorization/p1493-polychroniou.pdf) [SIGMOD 15]
4. [Access Path Selection in Main-Memory Optimized Data Systems: Should I Scan or Should I Probe?](https://15721.courses.cs.cmu.edu/spring2023/papers/06-execution/kester-sigmod17.pdf) [SIGMOD 17]
5. [Building Advanced SQL Analytics From Low-Level Plan Operators](https://db.in.tum.de/~kohn/papers/lolepops-sigmod21.pdf) [SIGMOD 21]
6. [Velox: Meta’s Unified Execution Engine](https://15721.courses.cs.cmu.edu/spring2024/papers/05-execution2/p3372-pedreira.pdf) [VLDB 23]

## Query Compilation
1. [How to Architect a Query Compiler](https://15721.courses.cs.cmu.edu/spring2023/papers/09-compilation/shaikhha-sigmod2016.pdf) [SIGMOD 16]
2. [Adaptive Execution of Compiled Queries](https://15721.courses.cs.cmu.edu/spring2023/papers/09-compilation/kohn-icde2018.pdf) [ICDE 18]

## Logic Bugs Detection
1. [Detecting Logic Bugs of Join Optimizations in DBMS](https://dl.acm.org/doi/pdf/10.1145/3588909) [SIGMOD 23 Best Paper]

## Storage
1. [Dissecting, Designing, and Optimizing LSM-based Data Stores](https://dl.acm.org/doi/pdf/10.1145/3514221.3522563) [SIGMOD 22 Tutorial]
2. [What Modern NVMe Storage Can Do, And How To Exploit It: High-Performance I/O for High-Performance Storage Engines](https://www.vldb.org/pvldb/vol16/p2090-haas.pdf) [VLDB 23]
3. [An Empirical Evaluation of Columnar Storage Formats](https://www.vldb.org/pvldb/vol17/p148-zeng.pdf) [VLDB 24]

## Proxy
1. [Tigger: A Database Proxy That Bounces With User-Bypass](https://www.vldb.org/pvldb/vol16/p3335-butrovich.pdf) [[VLDB 23](https://github.com/mbutrovich/tigger)]

## Data Loading
1. [ConnectorX: Accelerating Data Loading From Databases to Dataframes](https://15721.courses.cs.cmu.edu/spring2024/papers/12-networking/p2994-wang.pdf) [VLDB 22]

## Database Kernel
1. [Lakehouse: A New Generation of Open Platforms that Unify Data Warehousing and Advanced Analytics](https://www.cidrdb.org/cidr2021/papers/cidr2021_paper17.pdf) [CIDR 21]
2. [GPU Database Systems Characterization and Optimization](https://www.vldb.org/pvldb/vol17/p441-cao.pdf) [[VLDB 24](https://github.com/jiashenC/gpudb-char-and-opt)]
3. [The Art of Latency Hiding in Modern Database Engines](https://www.vldb.org/pvldb/vol17/p577-huang.pdf) [[VLDB 24](https://github.com/sfu-dis/mosaicdb)]
4. [Disaggregated Database Systems](https://www.cs.purdue.edu/homes/csjgwang/pubs/SIGMOD23_Tutorial_DisaggregatedDB.pdf) [VLDB 23 Tutorial]

## Others
### MVCC
1. [Scalable Garbage Collection for In-Memory MVCC Systems](https://users.cs.utah.edu/~pandey/courses/cs6530/fall22/papers/mvcc/p128-bottcher.pdf) [VLDB 13]
2. [Rethinking serializable multiversion concurrency control](https://browse.arxiv.org/pdf/1412.2324.pdf) [VLDB 15]
3. [An Empirical Evaluation of In-Memory Multi-Version Concurrency Control](https://www.vldb.org/pvldb/vol10/p781-Wu.pdf) [VLDB 17]
4. [Accelerating Analytical Processing in MVCC using Fine-Granular High-Frequency Virtual Snapshotting](https://bigdata.uni-saarland.de/publications/AnKer_SIGMOD2018.pdf) [SIGMOD 18]
5. [Long-lived Transactions Made Less Harmful](https://dl.acm.org/doi/pdf/10.1145/3318464.3389714) [SIGMOD 20]
6. [Rethink the Scan in MVCC Databases](https://dl.acm.org/doi/pdf/10.1145/3448016.3452783) [SIGMOD 21]
7. [Diva: Making MVCC Systems HTAP-Friendly](https://dl.acm.org/doi/pdf/10.1145/3514221.3526135) [SIGMOD 22]
8. [Memory-Optimized Multi-Version Concurrency Control for Disk-Based Database Systems](https://db.in.tum.de/~freitag/papers/p2797-freitag.pdf) [VLDB 22]
9. [Scalable and Robust Snapshot Isolation for High-Performance Storage Engines](https://www.vldb.org/pvldb/vol16/p1426-alhomssi.pdf) [VLDB 23]
10. [One-shot Garbage Collection for In-memory OLTP through Temporality-aware Version Storage](https://dl.acm.org/doi/pdf/10.1145/3588699) [SIGMOD 23]

### HTAP
#### System Architecture
##### Linear Consistency
1. [HyPer: A Hybrid OLTP&OLAP Main Memory Database System Based on Virtual Memory Snapshots](https://cs.brown.edu/courses/cs227/archives/2012/papers/olap/hyper.pdf) [ICDE 12]
2. [TiDB: A raft-based htap database](https://www.vldb.org/pvldb/vol13/p3072-huang.pdf) [VLDB 20]
3. [OceanBase Paetica: A Hybrid Shared-Nothing/Shared-Everything Database for Supporting Single Machine and Distributed Cluster](https://dl.acm.org/doi/pdf/10.14778/3611540.3611560) [VLDB 23]


##### Sequential Consistency
1. [BatchDB: Efficient Isolated Execution of Hybrid OLTP+OLAP Workloads for Interactive Applications](https://db.in.tum.de/~giceva/papers/SIGMOD_batchdb.pdf?lang=de) [SIGMOD 17]
2. [F1 Lightning: HTAP as a Service](http://www.vldb.org/pvldb/vol13/p3313-yang.pdf) [VLDB 20]
3. [Retrofitting High Availability Mechanism to Tame Hybrid Transaction/Analytical Processing](https://www.usenix.org/system/files/osdi21-shen.pdf) [ATC 21]
4. [ByteHTAP: ByteDance’s HTAP System with High Data Freshness and Strong Data Consistency](https://www.vldb.org/pvldb/vol15/p3411-chen.pdf) [VLDB 22]


##### Session Consistency
1. [PolarFS: An Ultra-low Latency and Failure Resilient Distributed File System for Shared Storage Cloud Database](https://www.vldb.org/pvldb/vol11/p1849-cao.pdf) [VLDB 18]
2. [PolarDB-IMCI: A Cloud-Native HTAP Database System at Alibaba](https://browse.arxiv.org/pdf/2305.08468.pdf) [SIGMOD 23]


##### Survey
1. [HTAP Databases: What is New and What is Next](https://dl.acm.org/doi/pdf/10.1145/3514221.3522565) [SIGMOD 22]
2. [Data Sharing Model and Optimization Strategies in HTAP Database Systems](https://www.jos.org.cn/josen/article/pdf/6901) [Journal of Software 23]

#### Kernel Optimization
1. [Log Replaying for Real-Time HTAP: An Adaptive Epoch-based Two-Stage Framework]() [ICDE 24]

### Benchmark
1. [How Good is My HTAP System?](https://dl.acm.org/doi/pdf/10.1145/3514221.3526148) [SIGMOD 22]
2. [OLxPBench: Real-time, Semantically Consistent, and Domain-specific are Essential in Benchmarking, Designing, and Implementing HTAP Systems](https://ieeexplore.ieee.org/document/9835647) [ICDE 22]
3. [Dike: A Benchmark Suite for Distributed Transactional Databases](https://dl.acm.org/doi/pdf/10.1145/3555041.3589710) [SIGMOD 23]
4. [M2Bench: A Database Benchmark for Multi-Model Analytic Workloads](https://www.vldb.org/pvldb/vol16/p747-moon.pdf) [VLDB 23]
5. [Cloud Analytics Benchmark](https://www.vldb.org/pvldb/vol16/p1413-renen.pdf) [VLDB 23]
6. [Pollock: A Data Loading Benchmark](https://www.vldb.org/pvldb/vol16/p1870-vitagliano.pdf) [VLDB 23]
7. [VeriBench: Analyzing the Performance of Database Systems with Verifiability](https://www.vldb.org/pvldb/vol16/p2145-ooi.pdf) [VLDB 23]
8. [TSM-Bench: Benchmarking Time Series Database Systems for Monitoring Applications](https://www.vldb.org/pvldb/vol16/p3363-khelifati.pdf) [VLDB 23]
9. [CDSBen: Benchmarking the Performance of Storage Services in Cloud-native Database System at ByteDance](https://www.vldb.org/pvldb/vol16/p3584-tang.pdf) [VLDB 23]
10. [FEBench: A Benchmark for Real-Time Relational Data Feature Extraction](https://www.vldb.org/pvldb/vol16/p3597-lu.pdf) [VLDB 23]
11. [TPCx-AI - An Industry Standard Benchmark for Artificial Intelligence and Machine Learning Systems](https://www.vldb.org/pvldb/vol16/p3649-rabl.pdf) [VLDB 23]
12. [ScienceBenchmark: A Complex Real-World Benchmark for Evaluating Natural Language to SQL Systems](https://www.vldb.org/pvldb/vol17/p685-stockinger.pdf) [[VLDB 23](https://sciencebenchmark.cloudlab.zhaw.ch/)]
13. [DBPA: A Benchmark for Transactional Database Performance Anomalies](https://dl.acm.org/doi/pdf/10.1145/3588926) [SIGMOD 23]
14. [HyBench: A New Benchmark for HTAP Databases](https://www.vldb.org/pvldb/vol17/p939-zhang.pdf) [[VLDB 24](https://github.com/Rucchao/HyBench-2023)]

### Time Series
1. [An Experimental Evaluation of Anomaly Detection in Time Series](https://www.vldb.org/pvldb/vol17/p483-zhang.pdf) [VLDB 24]

### Vector Data
1. [Are There Fundamental Limitations in Supporting Vector Data Management in Relational Databases? A Case Study of PostgreSQL](https://www.cs.purdue.edu/homes/csjgwang/pubs/ICDE24_VecDB.pdf) [ICDE 24]

### [OLTP](https://github.com/wengsy150943/Paper4OLTPandConcurrencyTesting)
### [AI4DB](https://github.com/Wind-Gone/Ai4DB-Paper)
### [Industry](https://github.com/Wind-Gone/DBGiant-Industry-Paper)
