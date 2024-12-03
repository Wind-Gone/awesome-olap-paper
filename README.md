# Awesome-OLAP-Paper [![666](https://awesome.re/badge.svg)](https://awesome.re)

[![Awesome OLAP Paper](https://img.shields.io/static/v1?label=&message=Awesome+OLAP+Paper&color=black&logo=awesomelists)](https://github.com/Wind-Gone/awesome-olap-paper)
![](https://img.shields.io/github/last-commit/Wind-Gone/awesome-olap-paper?color=green)
![visitor badge](https://visitor-badge.lithub.cc/badge?page_id=Wind-Gone.awesome-olap-paper)
[![GitHub Repo stars](https://img.shields.io/github/stars/Wind-Gone/awesome-olap-paper?style=social)](https://github.com/Wind-Gone/awesome-olap-paper)
[![GitHub Repo forks](https://img.shields.io/github/forks/Wind-Gone/awesome-olap-paper?style=social)](https://github.com/Wind-Gone/awesome-olap-paper)
## Introduction

A curated paper list of awesome Online Analytical Processing <b>database systems, theory, frameworks, resources, tools</b> and other awesomeness, for database researchers/engineers.

## Contributing

The repository is under construction.  Welcome new PR, please conform to the committed rules: 

```bash
paperName(with pdf link) [MeetingName Year] Github link if it has open-sourced code (optional)
```
## Acknowledge
Thanks to all authors of the paper/repository I cite :D

## Table of Content


- [Awesome-OLAP-Paper ](#awesome-olap-paper-)
  - [Introduction](#introduction)
  - [Contributing](#contributing)
  - [Acknowledge](#acknowledge)
  - [Table of Content](#table-of-content)
  - [Query-Aware Database Generation](#query-aware-database-generation)
    - [Privacy](#privacy)
    - [Survey](#survey)
  - [Query Schedule](#query-schedule)
  - [Query Optimization](#query-optimization)
    - [Query Rewrite](#query-rewrite)
    - [Cardinality Estimation](#cardinality-estimation)
      - [Histogram](#histogram)
      - [Sampling](#sampling)
      - [Others](#others)
      - [Survey](#survey-1)
    - [Join Order](#join-order)
    - [Join Algorithms](#join-algorithms)
    - [Cost Model](#cost-model)
    - [View](#view)
    - [Survey](#survey-2)
    - [Index](#index)
  - [Query Execution](#query-execution)
  - [Data Dependency Search](#data-dependency-search)
  - [Query Compilation](#query-compilation)
  - [Bugs Detection](#bugs-detection)
    - [Static Analysis](#static-analysis)
  - [Storage](#storage)
    - [LSM-Tree](#lsm-tree)
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
        - [Survey](#survey-3)
      - [Kernel Optimization](#kernel-optimization)
    - [Result Replay](#result-replay)
    - [Benchmark](#benchmark)
      - [OLTP](#oltp)
      - [OLAP](#olap)
      - [HTAP](#htap-1)
      - [Others](#others-2)
      - [Multi-Model](#multi-model)
    - [Time Series](#time-series)
    - [Vector Database](#vector-database)
      - [Survey](#survey-4)
    - [Algorithm](#algorithm)
    - [Distributed Systems](#distributed-systems)
    - [OLTP](#oltp-1)
    - [AI4DB](#ai4db)
    - [Industry](#industry)
  - [Star History](#star-history)

## Query-Aware Database Generation
1.  [QAGen: Generating Query-Aware Test Databases](https://cs.uwaterloo.ca/~tozsu/publications/other/sigmod07-final.pdf) [SIGMOD 07]
2.  [Generating Targeted Queries for Database Testing](https://dl.acm.org/doi/pdf/10.1145/1376616.1376668) [SIGMOD 08]
3. [Generating Databases for Query Workloads](https://dl.acm.org/doi/pdf/10.14778/1920841.1920950) [VLDB 10]
4. [Data Generation using Declarative Constraints](https://dl.acm.org/doi/pdf/10.1145/1989323.1989395) [SIGMOD 11]
5. [MyBenchmark: generating databases for query workloads](https://link.springer.com/article/10.1007/s00778-014-0354-1) [VLDB 14]
6. [Scalable and Dynamic Regeneration of Big Data Volumes](https://openproceedings.org/2018/conf/edbt/paper-114.pdf) [EDBT 18]
7. [Touchstone: Generating Enormous Query-Aware Test Databases](https://www.usenix.org/system/files/conference/atc18/atc18-li-yuming.pdf) [OSDI 18]
8. [Synthesizing Linked Data Under Cardinality and Integrity Constraints](https://dl.acm.org/doi/pdf/10.1145/3448016.3457242) [SIGMOD 21]
9. [Projection-Compliant Database Generation](https://www.vldb.org/pvldb/vol15/p998-sanghi.pdf) [VLDB 22]
10. [SAM: Database Generation from Query Workloads with Supervised Autoregressive Models](https://dl.acm.org/doi/pdf/10.1145/3514221.3526168) [SIGMOD 22] [![](https://img.shields.io/github/stars/Jamesyang2333/SAM?style=social&label=Code+Stars)](https://github.com/Jamesyang2333/SAM)
11. [Mirage: Generating Enormous Databases for Complex Workloads]() [ICDE 24]

### Privacy
1. [PrivSyn: Differentially Private Data Synthesis](https://www.usenix.org/system/files/sec21-zhang-zhikun.pdf) [ATC 21]
2. [Synthesizing Linked Data Under Cardinality and Integrity Constraints](https://arxiv.org/pdf/2103.14435) [SIGMOD 21]
3.  [Data Synthesis via Differentially Private Markov Random Fields](https://dl.acm.org/doi/pdf/10.14778/3476249.3476272#page=9.47) [VLDB 21]
4. [PrivLava: Synthesizing Relational Data with Foreign Keys under Differential Privacy](https://dl.acm.org/doi/pdf/10.1145/3589287) [SIGMOD 23]
5. [Privacy-Enhanced Database Synthesis for Benchmark Publishing](https://arxiv.org/pdf/2405.01312#page=3.51) [arXiv 24]

### Survey
1. [Synthetic Data Generation for Enterprise DBMS](https://dsl.cds.iisc.ac.in/publications/conference/ICDE_DataGen_Tutorial.pdf) [ICDE 23]

## Query Schedule
1. [Self-Tuning Query Scheduling for Analytical Workloads](https://15721.courses.cs.cmu.edu/spring2024/papers/08-scheduling/wagner-sigmod21.pdf) [SIGMOD 21]
2. [Memory Efficient Scheduling of Query Pipeline Execution](https://www.cidrdb.org/cidr2022/papers/p82-landgraf.pdf) [CIDR 22]
3. [LSched: A Workload-Aware Learned Query Scheduler for Analytical Database Systems](https://dl.acm.org/doi/pdf/10.1145/3514221.3526158) [SIGMOD 22]
4. [Rotary: A Resource Arbitration Framework for Progressive Iterative Analytics](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10184533) [ICDE 23]
   

## Query Optimization
1. [Sampling-Based Query Re-Optimization](https://pages.cs.wisc.edu/~wentaowu/papers/sigmod16-reoptimization.pdf) [SIGMOD 16]
2. [Kepler: Robust Learning for Parametric Query Optimization](https://dl.acm.org/doi/pdf/10.1145/3588963) [SIGMOD 23]
3. [Rethink Query Optimization in HTAP Databases](https://dl.acm.org/doi/pdf/10.1145/3626750) [SIGMOD 24]
4. [Optimizing Nested Recursive Queries](https://dl.acm.org/doi/pdf/10.1145/3639271) [SIGMOD 24]
5. [Efficient Enumeration of Recursive Plans in Transformation-based Query Optimizers](https://www.vldb.org/pvldb/vol17/p3095-geneves.pdf) [VLDB 24]
6. [ROME: Robust Query Optimization via Parallel Multi-Plan Execution](https://dl.acm.org/doi/10.1145/3654973) [SIGMOD 24]
7. [Presto’s History-based Query Optimizer](https://www.vldb.org/pvldb/vol17/p4077-shankhdhar.pdf) [VLDB 24]

### Query Rewrite
1. [QueryBooster: Improving SQL Performance Using Middleware
Services for Human-Centered Query Rewriting](https://www.vldb.org/pvldb/vol16/p2911-bai.pdf) [VLDB 23]
2. [SlabCity: Whole-Query Optimization using Program Synthesis](https://dl.acm.org/doi/pdf/10.14778/3611479.3611515) [VLDB 23]
3. [GEqO: ML-Accelerated Semantic Equivalence Detection](https://dl.acm.org/doi/pdf/10.1145/3626710) [SIGMOD 24]
4. [Proving Query Equivalence Using Linear Integer Arithmetic](https://dl.acm.org/doi/pdf/10.1145/3626768) [SIGMOD 24]
5. [QED: A Powerful Query Equivalence Decider for SQL](https://www.vldb.org/pvldb/vol17/p3602-wang.pdf) [VLDB 24]
6. [VeriEQL: Bounded Equivalence Verification for Complex SQL Queries with Integrity Constraints](https://pinhanzhao.com/papers/oopsla24.pdf) [OOPSLA 24]


### Cardinality Estimation
#### Histogram
1. [Equi-Depth Histograms For Estimating Selectivity Factors For Multi-Dimensional Queries](https://dl.acm.org/doi/pdf/10.1145/971701.50205) [None 87]
2. [Optimal Histograms for Limiting Worst-Case Error Propagation in the Size of Join Results](https://dl.acm.org/doi/pdf/10.1145/169725.169708) [ACM Transactions on Database Systems 93]
3. [On Rectangular Partitionings in Two Dimensions: Algorithms, Complexity, and Applications](https://link.springer.com/chapter/10.1007/3-540-49257-7_16) [ICDT 99]
4. [Independence is good: Dependency-based histogram synopses for high-dimensional data](https://dl.acm.org/doi/pdf/10.1145/376284.375685) [SIGMOD 01]
5. [STHoles: a multidimensional workload-aware histogram](http://www.cs.columbia.edu/~gravano/Papers/2001/sigmod01b.pdf) [SIGMOD 01]
6. [A multi-dimensional histogram for selectivity estimation and fast approximate query answering](https://dl.acm.org/doi/pdf/10.5555/961322.961374) [CASCON 03]
7. [The history of histograms (abridged)](https://www.vldb.org/conf/2003/papers/S02P01.pdf) [VLDB 03]
8. [ISOMER: Consistent histogram construction using query feedback](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=55708905fb9ecd1ffa2f41638410f672147ccdaa) [ICDE 06]
9. [Join Over Histograms](http://www.adellera.it/static_html/investigations/join_over_histograms/JoinOverHistograms.pdf) [Alberto Dell'Era 07]
10. [Improving accuracy and robustness of self-tuning histograms by subspace clustering](https://dbis.ipd.kit.edu/download/MineClusSTHoles_-_Minor_Revision.pdf) [ICDE 16]
11. [LHist: Towards Learning Multidimensional Histogram for Massive Spatial Data](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9458896) [ICDE 21]

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
1. [Preventing bad plans by bounding the impact of cardinality estimation errors](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=986d26dd8fa2355e9356ab2740b76e691cb22a15) [VLDB 09]
2. [Analyzing the Impact of Cardinality Estimation on Execution Plans in Microsof SQL Server](https://www.vldb.org/pvldb/vol16/p2871-dutt.pdf) [VLDB 23]

### Join Order
1. [Join Order Selection with Deep Reinforcement Learning: Fundamentals, Techniques, and Challenges](https://www.vldb.org/pvldb/vol16/p3882-yan.pdf) [VLDB 23]
2. [Efficiently Computing Join Orders with Heuristic Search](https://dl.acm.org/doi/pdf/10.1145/3588927) [SIGMOD 23]
3. [Ready to Leap (by Co-Design)? Join Order Optimisation on Quantum Hardware](https://dl.acm.org/doi/pdf/10.1145/3588946) [SIGMOD 23]
4. [Quantum-Inspired Digital Annealing for Join Ordering](https://www.vldb.org/pvldb/vol17/p511-schonberger.pdf) [[VLDB 24](https://github.com/lfd/vldb24)]
5. [POLAR: Adaptive and Non-invasive Join Order Selection via Plans of Least Resistance](https://www.vldb.org/pvldb/vol17/p1350-justen.pdf) [VLDB 24] [![](https://img.shields.io/github/stars/damslab/reproducibility?style=social&label=Code+Stars)](https://github.com/damslab/reproducibility/tree/master/vldb2024-POLAR)
6. [Sub-optimal Join Order Identification with L1-error](https://dl.acm.org/doi/pdf/10.1145/3639272) [SIGMOD 24]

### Join Algorithms
1. [Massively Parallel Sort-Merge Joins in Main Memory Multi-Core Database Systems](https://15721.courses.cs.cmu.edu/spring2023/papers/12-sortmergejoins/p1064-albutiu.pdf) [VLDB 12]
2. [Leapfrog Triejoin: a worst-case optimal join algorithm](https://arxiv.org/pdf/1210.0481.pdf) [International Conference on Database Theory 12]
3. [An Experimental Comparison of Thirteen Relational Equi-Joins in Main Memory](https://15721.courses.cs.cmu.edu/spring2018/papers/19-hashjoins/schuh-sigmod2016.pdf) [SIGMOD 16]
4. [Worst-Case Optimal Join Algorithms: Techniques, Results, and Open Problems](https://arxiv.org/pdf/1803.09930.pdf) [SIGMOD 18]
5. [Adopting Worst-Case Optimal Joins in Relational Database Systems](https://www.vldb.org/pvldb/vol13/p1891-freitag.pdf) [VLDB 20]
6. [Free Join: Unifying Worst-Cast Optimal and Traditional Joins](https://arxiv.org/pdf/2301.10841.pdf) [arXiv 23]
7. [Reservoir Sampling over Joins](https://arxiv.org/pdf/2404.03194.pdf#page=1.48) [SIGMOD 24]

### Cost Model
1. [LEO – DB2’s LEarning Optimizer](https://15721.courses.cs.cmu.edu/spring2023/papers/18-costmodels/stillger-vldb2001.pdf) [VLDB 11]
2. [Predicting query execution time: are optimizer cost models really unusable?](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6544899) [ICDE 13]
3. [Towards Predicting Query Execution Time for Concurrent and Dynamic Database Workloads](https://pages.cs.wisc.edu/~wentaowu/papers/vldb13-prediction-cc.pdf) [VLDB 13]
4. [Forecasting the cost of processing multi-join queries via hashing for main-memory databases](https://arxiv.org/pdf/1507.03049.pdf) [SoCC 15]
5. [Query Performance Prediction for Concurrent Queries using Graph Embedding](http://www.vldb.org/pvldb/vol13/p1416-zhou.pdf) [VLDB 20]
6. [Efficient Deep Learning Pipelines for Accurate Cost Estimations Over Large Scale Query Workload](https://arxiv.org/pdf/2103.12465.pdf) [arXiv 21]
7. [Rethinking Learned Cost Models: Why Start from Scratch?](https://dl.acm.org/doi/pdf/10.1145/3626769) [SIGMOD 24]
8. [Cackle: Analytical Workload Cost and Performance Stability With Elastic Pools](https://dl.acm.org/doi/pdf/10.1145/3626720) [SIGMOD 24]


### View
1. [Foreign Keys Open the Door for Faster Incremental View Maintenance](https://dl.acm.org/doi/pdf/10.1145/3588720) [SIGMOD 23]

### Survey
1. [How Good Are Query Optimizers, Really?](https://www.vldb.org/pvldb/vol9/p204-leis.pdf) [VLDB 15]
2. [Cardinality Estimation: An Experimental Survey](https://www.vldb.org/pvldb/vol11/p499-harmouch.pdf) [VLDB 17]
3. [A Survey on Advancing the DBMS Query Optimizer: Cardinality Estimation, Cost Model, and Plan Enumeration](https://arxiv.org/pdf/2101.01507.pdf) [VLDB 21]
4. [Have query optimizers hit the wall?](https://link.springer.com/article/10.1007/s00778-021-00689-y) [VLDB Journal 22]
5. [Cardinality Estimation in DBMS: A Comprehensive Benchmark Evaluation](https://dl.acm.org/doi/pdf/10.14778/3503585.3503586) [VLDB 22]
6. [Data dependencies for query optimization: a survey](https://link.springer.com/article/10.1007/s00778-021-00676-3) [VLDB Journal 22]
7. [Simple Adaptive Query Processing vs. Learned Query Optimizers: Observations and Analysis](https://www.vldb.org/pvldb/vol16/p2962-zhang.pdf) [VLDB 23]

### Index
1. [SQL Server Column Store Indexes](https://15721.courses.cs.cmu.edu/spring2023/papers/04-olapindexes/p1177-larson.pdf) [SIGMOD 11]
2. [Column Sketches: A Scan Accelerator for Rapid and Robust Predicate Evaluation](https://15721.courses.cs.cmu.edu/spring2023/papers/04-olapindexes/hentschel-sigmod18.pdf) [SIGMOD 18]

## Query Execution
1. [MonetDB/X100: Hyper-Pipelining Query Execution](https://www.cidrdb.org/cidr2005/papers/P19.pdf) [CIDR 05] 
2. [Materialization Strategies in the Vertica Analytic Database: Lessons Learned](https://15721.courses.cs.cmu.edu/spring2023/papers/06-execution/shrinivas-icde2013.pdf) [ICDE 13] 
3. [Rethinking SIMD Vectorization for In-Memory Databases](https://15721.courses.cs.cmu.edu/spring2024/papers/06-vectorization/p1493-polychroniou.pdf) [SIGMOD 15]
4. [Access Path Selection in Main-Memory Optimized Data Systems: Should I Scan or Should I Probe?](https://15721.courses.cs.cmu.edu/spring2023/papers/06-execution/kester-sigmod17.pdf) [SIGMOD 17]
5. [Building Advanced SQL Analytics From Low-Level Plan Operators](https://db.in.tum.de/~kohn/papers/lolepops-sigmod21.pdf) [SIGMOD 21]
6. [SkinnerMT: Parallelizing for Efficiency and Robustness in Adaptive Query Processing on Multicore Platforms](https://www.vldb.org/pvldb/vol16/p905-wei.pdf) [VLDB 22]
7. [ChainedFilter: Combining Membership Filters by Chain Rule](https://dl.acm.org/doi/pdf/10.1145/3626721) [SIGMOD 24]
8. [Saving Money for Analytical Workloads in the Cloud](https://www.vldb.org/pvldb/vol17/p3602-wang.pdf) [VLDB 24]
9.  [Adaptive and Robust Query Execution for Lakehouses at Scale](https://www.vldb.org/pvldb/vol17/p3947-bu.pdf) [VLDB 24]

## Data Dependency Search
1. [Discovering Functional Dependencies through Hitting Set Enumeration](https://dl.acm.org/doi/pdf/10.1145/3639298) [SIGMOD 24]

## Query Compilation
1. [How to Architect a Query Compiler](https://15721.courses.cs.cmu.edu/spring2023/papers/09-compilation/shaikhha-sigmod2016.pdf) [SIGMOD 16]
2. [Adaptive Execution of Compiled Queries](https://15721.courses.cs.cmu.edu/spring2023/papers/09-compilation/kohn-icde2018.pdf) [ICDE 18]

## Bugs Detection
1. [Finding Bugs in Database Systems via Query Partitioning](https://dl.acm.org/doi/pdf/10.1145/3428279) [OOPSLA 20]
2. [Detecting Optimization Bugs in Database Engines via Non-Optimizing Reference Engine Construction]() [FSE 20]
3. [Sequence-Oriented DBMS Fuzzing](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10184875) [ICDE 23]
4. [Detecting Logic Bugs of Join Optimizations in DBMS](https://dl.acm.org/doi/pdf/10.1145/3588909) [SIGMOD 23 Best Paper]
5. [Detecting Metadata-Related Logic Bugs in Database Systems via Raw Database Construction](https://www.vldb.org/pvldb/vol17/p1884-song.pdf) [VLDB 24]
6. [Keep It Simple: Testing Databases via Differential Query Plans](https://bajinsheng.github.io/assets/pdf/dqp_sigmod24.pdf) [SIGMOD 24]
7. [Sedar: Obtaining High-Quality Seeds for DBMS Fuzzing via Cross-DBMS SQL Transfer](https://dl.acm.org/doi/abs/10.1145/3597503.3639210) [ICSE 24]
8. [Plume: Efficient and Complete Black-Box Checking of Weak Isolation Levels](https://dl.acm.org/doi/pdf/10.1145/3689742) [OOPSLA2 2024]
9. [CERT: Finding Performance Issues in Database Systems Through the Lens of Cardinality Estimation](https://arxiv.org/pdf/2306.00355) [ICSE 24]
10. [PUPPY: Finding Performance Degradation Bugs in DBMSs via Limited-Optimization Plan Construction](http://www.wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_25/Puppy_ICSE25.pdf) [ICSE 25]
11. [Understanding and Detecting SQL Function Bugs](http://wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_25/soft_eurosys25.pdf) [EuroSys 25]
12. [Understanding and Reusing Test Suites Across Database Systems](https://arxiv.org/pdf/2410.21731) [SIGMOD 25]
13. [SQLaser: Detecting DBMS Logic Bugs with Clause-Guided Fuzzing](https://arxiv.org/pdf/2407.04294) [arXiv 24]
14. [THANOS: DBMS Bug Detection via Storage Engine Rotation Based Differential Testing](http://www.wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_25/Thanos_ICSE25.pdf) [ICSE 25]
15. [Conformance Testing of Relational DBMS Against SQL Specifications](https://arxiv.org/pdf/2406.09469) [ICSE 25]
16. [Automatic Database Configuration Debugging using Retrieval-Augmented Language Models]() [SIGMOD 25]
  


### Static Analysis
1. [Enhancing Static Analysis for Practical Bug Detection: An LLM-Integrated Approach](https://dl.acm.org/doi/pdf/10.1145/3649828) [PACMPL 24]

## Storage
1. [What Modern NVMe Storage Can Do, And How To Exploit It: High-Performance I/O for High-Performance Storage Engines](https://www.vldb.org/pvldb/vol16/p2090-haas.pdf) [VLDB 23]
2. [An Empirical Evaluation of Columnar Storage Formats](https://www.vldb.org/pvldb/vol17/p148-zeng.pdf) [VLDB 24]
### LSM-Tree
1. [Dissecting, Designing, and Optimizing LSM-based Data Stores](https://dl.acm.org/doi/pdf/10.1145/3514221.3522563) [SIGMOD 22 Tutorial]
2. [Magma: A High Data Density Storage Engine Used in Couchbase](https://www.vldb.org/pvldb/vol15/p3496-lakshman.pdf#page=1.23) [VLDB 22]
3. [CaaS-LSM: Compaction-as-a-Service for LSM-based Key-Value Stores in Storage Disaggregated Infrastructure](https://qiaolin-yu.github.io/pubs/V2mod124-yu.pdf) [SIGMOD 24]
4. [CAMAL: Optimizing LSM-trees via Active Learning](https://arxiv.org/pdf/2409.15130) [SIGMOD 25]

## Proxy
1. [Tigger: A Database Proxy That Bounces With User-Bypass](https://www.vldb.org/pvldb/vol16/p3335-butrovich.pdf) [[VLDB 23](https://github.com/mbutrovich/tigger)]

## Data Loading
1. [ConnectorX: Accelerating Data Loading From Databases to Dataframes](https://15721.courses.cs.cmu.edu/spring2024/papers/12-networking/p2994-wang.pdf) [VLDB 22]

## Database Kernel
1. [Lakehouse: A New Generation of Open Platforms that Unify Data Warehousing and Advanced Analytics](https://www.cidrdb.org/cidr2021/papers/cidr2021_paper17.pdf) [CIDR 21]
2. [Disaggregated Database Systems](https://www.cs.purdue.edu/homes/csjgwang/pubs/SIGMOD23_Tutorial_DisaggregatedDB.pdf) [VLDB 23 Tutorial]
3. [GPU Database Systems Characterization and Optimization](https://www.vldb.org/pvldb/vol17/p441-cao.pdf) [[VLDB 24](https://github.com/jiashenC/gpudb-char-and-opt)]
4. [The Art of Latency Hiding in Modern Database Engines](https://www.vldb.org/pvldb/vol17/p577-huang.pdf) [[VLDB 24](https://github.com/sfu-dis/mosaicdb)]
5. [DoppelGanger++: Towards Fast Dependency Graph Generation for Database Replay](https://dl.acm.org/doi/pdf/10.1145/3639322#page=2.12) [SIGMOD 24]


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
3. [HTAP Databases: A Survey](https://arxiv.org/pdf/2404.15670) [TKDE 24]
4. [ A survey on hybrid transactional and analytical processing](https://link.springer.com/article/10.1007/s00778-024-00858-9) [VLDB Journal 24]
5. [Survey on Benchmarking Ability of HTAP Benchmarks](https://www.jos.org.cn/jos/article/abstract/7225) [Journal of Software 24]

#### Kernel Optimization
1. [TiQuE: Improving the Transactional Performance of Analytical Systems for True Hybrid Workloads](https://www.vldb.org/pvldb/vol16/p2274-faria.pdf) [VLDB 23]
2. [Log Replaying for Real-Time HTAP: An Adaptive Epoch-based Two-Stage Framework](https://www.computer.org/csdl/proceedings-article/icde/2024/171500c096/1YOtqw9cWJ2) [ICDE 24]
3. [Two Birds With One Stone: Designing a Hybrid Cloud Storage Engine for HTAP](https://vldb.org/pvldb/vol17/p3290-schmidt.pdf) [VLDB 24]

### Result Replay
1. [DoppelGanger++: Towards Fast Dependency Graph Generation for Database Replay](https://dl.acm.org/doi/pdf/10.1145/3639322) [SIGMOD 24]

### Benchmark
#### OLTP
1. [Dike: A Benchmark Suite for Distributed Transactional Databases](https://dl.acm.org/doi/pdf/10.1145/3555041.3589710) [SIGMOD 23]
2. [DBPA: A Benchmark for Transactional Database Performance Anomalies](https://dl.acm.org/doi/pdf/10.1145/3588926) [SIGMOD 23]
#### OLAP
1. [Why You Should Run TPC-DS: A Workload Analysis](https://www.vldb.org/conf/2007/papers/industrial/p1138-poess.pdf) [VLDB 07]
2. [The Making of TPC-DS](https://vldb.org/conf/2006/p1049-othayoth.pdf) [VLDB 06]
3. [TPC-DS, Taking Decision Support Benchmarking to the Next Level](https://dl.acm.org/doi/abs/10.1145/564691.564759) [SIGMOD 02]
4. [Generating Thousands of Benchmark Queries in Seconds](https://www.vldb.org/archives/website/2004/protected/eProceedings/contents/pdf/IND2P3.PDF) [VLDB 04]
#### HTAP 
1. [How Good is My HTAP System?](https://dl.acm.org/doi/pdf/10.1145/3514221.3526148) [SIGMOD 22] [![](https://img.shields.io/github/stars/UWHustle/HATtrick?style=social&label=Code+Stars)](https://github.com/UWHustle/HATtrick)
2. [OLxPBench: Real-time, Semantically Consistent, and Domain-specific are Essential in Benchmarking, Designing, and Implementing HTAP Systems](https://ieeexplore.ieee.org/document/9835647) [ICDE 22]
#### Others 
1. [M2Bench: A Database Benchmark for Multi-Model Analytic Workloads](https://www.vldb.org/pvldb/vol16/p747-moon.pdf) [VLDB 23]
2. [Cloud Analytics Benchmark](https://www.vldb.org/pvldb/vol16/p1413-renen.pdf) [VLDB 23]
3. [Pollock: A Data Loading Benchmark](https://www.vldb.org/pvldb/vol16/p1870-vitagliano.pdf) [VLDB 23]
4. [VeriBench: Analyzing the Performance of Database Systems with Verifiability](https://www.vldb.org/pvldb/vol16/p2145-ooi.pdf) [VLDB 23]
5. [TSM-Bench: Benchmarking Time Series Database Systems for Monitoring Applications](https://www.vldb.org/pvldb/vol16/p3363-khelifati.pdf) [VLDB 23]
6. [CDSBen: Benchmarking the Performance of Storage Services in Cloud-native Database System at ByteDance](https://www.vldb.org/pvldb/vol16/p3584-tang.pdf) [VLDB 23]
7.  [FEBench: A Benchmark for Real-Time Relational Data Feature Extraction](https://www.vldb.org/pvldb/vol16/p3597-lu.pdf) [VLDB 23]
8.  [TPCx-AI - An Industry Standard Benchmark for Artificial Intelligence and Machine Learning Systems](https://www.vldb.org/pvldb/vol16/p3649-rabl.pdf) [VLDB 23]
9.  [ScienceBenchmark: A Complex Real-World Benchmark for Evaluating Natural Language to SQL Systems](https://www.vldb.org/pvldb/vol17/p685-stockinger.pdf) [VLDB 23] [![](https://img.shields.io/github/stars/yizhang-unifr/nl-ql-data-augmentation?style=social&label=Code+Stars)](https://github.com/yizhang-unifr/nl-ql-data-augmentation)

#### Multi-Model
1. [Multi-model Databases: A New Journey to Handle the Variety of Data](https://www.cs.helsinki.fi/u/jilu/documents/Multi_model_Databases__A__New_Journey_to_Handle_the_Variety_of_DataFinal.pdf) [CSUR 19]
2. [M2Bench: A Database Benchmark for Multi-Model Analytic Workloads](https://www.vldb.org/pvldb/vol16/p747-moon.pdf) [VLDB 23]
3. [MMSBench-Net: Scenario-Based Evaluation of Multi-Model Database Systems](https://gvdb23.informatik.uni-stuttgart.de/wp-content/uploads/2023/06/GvDB2023_Lengweiler.pdf) [23]
4. [MMDBench: A Benchmark for Hybrid Query in Multimodal Database](https://bluejoe2008.github.io/pub/MMDBench__A_Benchmark_for_Hybrid_Query_in_Multimodal_Database.pdf) [24]

### Time Series
1. [An Experimental Evaluation of Anomaly Detection in Time Series](https://www.vldb.org/pvldb/vol17/p483-zhang.pdf) [VLDB 24]

### Vector Database
#### Survey
1. [Are There Fundamental Limitations in Supporting Vector Data Management in Relational Databases? A Case Study of PostgreSQL](https://www.cs.purdue.edu/homes/csjgwang/pubs/ICDE24_VecDB.pdf) [ICDE 24]
2. [Survey of Vector Database Management Systems](https://arxiv.org/pdf/2310.14021#page=3.39) [VLDBJ 24]
3. [Vector Database Management Techniques and Systems](https://dl.acm.org/doi/pdf/10.1145/3626246.3654691) [SIGMOD 24]

### Algorithm
1. [FlowWalker: A Memory-efficient and High-performance GPU-based Dynamic Graph Random Walk Framework](https://www.vldb.org/pvldb/vol17/p1788-mei.pdf) [VLDB 24]

### Distributed Systems
1. [Consistency in Non-Transactional Distributed Storage Systems](https://arxiv.org/pdf/1512.00168) [arXiv 15]
2. [NOC-NOC: Towards Performance-optimal Distributed Transactions](https://dl.acm.org/doi/pdf/10.1145/3639264#page=1.52) [SIGMOD 24]
3. [Native Distributed Databases: Problems, Challenges and Opportunities](https://www.vldb.org/pvldb/vol17/p4217-xu.pdf) [VLDB 24 Tutorial]

### [OLTP](https://github.com/wengsy150943/Paper4OLTPandConcurrencyTesting)
### [AI4DB](https://github.com/Wind-Gone/Ai4DB-Paper)
### [Industry](https://github.com/Wind-Gone/DBGiant-Industry-Paper)


## Star History

<a href="https://star-history.com/#Wind-Gone/awesome-olap-paper&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=Wind-Gone/awesome-olap-paper&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=Wind-Gone/awesome-olap-paper&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=Wind-Gone/awesome-olap-paper&type=Date" />
  </picture>
</a>
