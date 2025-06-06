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
paperName(with pdf link) (alias) [MeetingName Year] Github link if it has open-sourced code (optional)
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
    - [Robust Query Optimization](#robust-query-optimization)
    - [Query Rewrite](#query-rewrite)
    - [Cardinality Estimation](#cardinality-estimation)
      - [Histogram](#histogram)
      - [Sampling](#sampling)
      - [Learn Data Distribution Function](#learn-data-distribution-function)
      - [Others](#others)
      - [Survey](#survey-1)
      - [Special Case](#special-case)
    - [Join Order](#join-order)
    - [Join Algorithms](#join-algorithms)
    - [Sub-Query](#sub-query)
    - [Cost Model](#cost-model)
    - [View](#view)
    - [Survey](#survey-2)
    - [Index](#index)
  - [Query Execution](#query-execution)
  - [Data Dependency Search](#data-dependency-search)
  - [Query Compilation](#query-compilation)
  - [Bugs Detection](#bugs-detection)
    - [Functional Bug](#functional-bug)
      - [Logical Bug](#logical-bug)
      - [Crash Bug](#crash-bug)
    - [Performance Bug](#performance-bug)
    - [Survey](#survey-3)
    - [Static Analysis](#static-analysis)
    - [Casual Inference](#casual-inference)
    - [Code Location](#code-location)
  - [Storage](#storage)
    - [LSM-Tree](#lsm-tree)
    - [Kd-Tree](#kd-tree)
  - [Proxy](#proxy)
  - [Data Loading](#data-loading)
  - [Database Kernel](#database-kernel)
    - [Transactions](#transactions)
    - [Survey](#survey-4)
  - [Others](#others-1)
    - [MVCC](#mvcc)
    - [HTAP](#htap)
      - [System Architecture](#system-architecture)
        - [Linear Consistency](#linear-consistency)
        - [Sequential Consistency](#sequential-consistency)
        - [Session Consistency](#session-consistency)
        - [Survey](#survey-5)
      - [Kernel Optimization](#kernel-optimization)
    - [Result Replay](#result-replay)
    - [Benchmark](#benchmark)
      - [Survey](#survey-6)
      - [AI](#ai)
      - [OLTP](#oltp)
      - [OLAP](#olap)
      - [HTAP](#htap-1)
      - [Others](#others-2)
    - [Time Series](#time-series)
    - [Multi-Model](#multi-model)
      - [Benchmark](#benchmark-1)
    - [Vector Database](#vector-database)
      - [Survey](#survey-7)
    - [Algorithm](#algorithm)
    - [Distributed Systems](#distributed-systems)
    - [OLTP](#oltp-1)
      - [Survey](#survey-8)
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
11. [Mirage: Generating Enormous Databases for Complex Workloads](https://www.computer.org/csdl/proceedings-article/icde/2024/171500d989/1YOtBpuCaTS) [ICDE 24]
12. [Query Aware Database Generation for Match Operators](https://link.springer.com/chapter/10.1007/978-981-97-5552-3_18) [DASFAA 24]
13. [Controllable Tabular Data Synthesis Using Diffusion Models](https://dl.acm.org/doi/pdf/10.1145/3639283#page=1.57) [SIGMOD 24]
14. [A Query-Aware Enormous Database Generator For System Performance Evaluation]() [SIGMOD 25]

### Privacy
1. [PrivSyn: Differentially Private Data Synthesis](https://www.usenix.org/system/files/sec21-zhang-zhikun.pdf) [ATC 21]
2. [Synthesizing Linked Data Under Cardinality and Integrity Constraints](https://arxiv.org/pdf/2103.14435) [SIGMOD 21]
3.  [Data Synthesis via Differentially Private Markov Random Fields](https://dl.acm.org/doi/pdf/10.14778/3476249.3476272#page=9.47) [VLDB 21]
4. [PrivLava: Synthesizing Relational Data with Foreign Keys under Differential Privacy](https://dl.acm.org/doi/pdf/10.1145/3589287) [SIGMOD 23]
5. [Privacy-Enhanced Database Synthesis for Benchmark Publishing](https://www.vldb.org/pvldb/vol18/p413-zheng.pdf) [VLDB 25]

### Survey
1. [Synthetic Data Generation for Enterprise DBMS](https://dsl.cds.iisc.ac.in/publications/conference/ICDE_DataGen_Tutorial.pdf) [ICDE 23]

## Query Schedule
1. [Self-Tuning Query Scheduling for Analytical Workloads](https://15721.courses.cs.cmu.edu/spring2024/papers/08-scheduling/wagner-sigmod21.pdf) [SIGMOD 21]
2. [Memory Efficient Scheduling of Query Pipeline Execution](https://www.cidrdb.org/cidr2022/papers/p82-landgraf.pdf) [CIDR 22]
3. [LSched: A Workload-Aware Learned Query Scheduler for Analytical Database Systems](https://dl.acm.org/doi/pdf/10.1145/3514221.3526158) [SIGMOD 22]
4. [Rotary: A Resource Arbitration Framework for Progressive Iterative Analytics](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10184533) [ICDE 23]
5. [Laser: Buffer-Aware Learned Query Scheduling in Master-Standby Databases](https://www.vldb.org/pvldb/vol18/p743-li.pdf) [VLDB 25]
   

## Query Optimization
1. [Sampling-Based Query Re-Optimization](https://pages.cs.wisc.edu/~wentaowu/papers/sigmod16-reoptimization.pdf) [SIGMOD 16]
2. [Leveraging Re-costing for Online Optimization of Parameterized Queries with Guarantees](https://15799.courses.cs.cmu.edu/spring2025/papers/16-parametric/dutt-sigmod2017.pdf) [SIGMOD 17]
3. [Adaptive Optimization of Very Large Join Queries](https://15799.courses.cs.cmu.edu/spring2025/papers/07-joins1/neumann-sigmod2018.pdf) [SIGMOD 18]
4. [Efficient Massively Parallel Join Optimization for Large Queries](https://15799.courses.cs.cmu.edu/spring2025/papers/09-parallelization1/mancini-sigmod2022.pdf) [SIGMOD 22]
5. [Leveraging Query Logs and Machine Learning for Parametric Query Optimization](https://15799.courses.cs.cmu.edu/spring2025/papers/16-parametric/vaidya-vldb2022.pdf) [VLDB 22]
6. [Rethink Query Optimization in HTAP Databases](https://dl.acm.org/doi/pdf/10.1145/3626750) [SIGMOD 24]
7. [SPQO: Learning to Safely Reuse Cached Plans for Dynamic Workloads](https://link.springer.com/chapter/10.1007/978-981-97-5552-3_21) [DASFAA 24]
8. [Optimizing Nested Recursive Queries](https://dl.acm.org/doi/pdf/10.1145/3639271) [SIGMOD 24]
9.  [Efficient Enumeration of Recursive Plans in Transformation-based Query Optimizers](https://www.vldb.org/pvldb/vol17/p3095-geneves.pdf) [VLDB 24]
11. [Presto's History-based Query Optimizer](https://www.vldb.org/pvldb/vol17/p4077-shankhdhar.pdf) [VLDB 24]
12. [RankPQO: Learning-to-Rank for Parametric Query Optimization](https://www.vldb.org/pvldb/vol18/p863-mo.pdf) [VLDB 25]

### Robust Query Optimization
1. [Robust query processing through progressive optimization](https://dl.acm.org/doi/abs/10.1145/1007568.1007642) [SIGMOD 04]
2. [Robust Query Optimization Methods With Respect to Estimation Errors: A Survey](https://dl.acm.org/doi/pdf/10.1145/2854006.2854012) [SIGMOD 15]
3. [Efficient Query Re-optimization with Judicious Subquery Selections]() [SIGMDO 23]
4. [ROME: Robust Query Optimization via Parallel Multi-Plan Execution](https://dl.acm.org/doi/10.1145/3654973) [SIGMOD 24]

### Query Rewrite
1. [QueryBooster: Improving SQL Performance Using Middleware Services for Human-Centered Query Rewriting](https://www.vldb.org/pvldb/vol16/p2911-bai.pdf) [VLDB 23]
2. [SlabCity: Whole-Query Optimization using Program Synthesis](https://dl.acm.org/doi/pdf/10.14778/3611479.3611515) [VLDB 23]
3. [GEqO: ML-Accelerated Semantic Equivalence Detection](https://dl.acm.org/doi/pdf/10.1145/3626710) [SIGMOD 24]
4. [Proving Query Equivalence Using Linear Integer Arithmetic](https://dl.acm.org/doi/pdf/10.1145/3626768) [SIGMOD 24]
5. [QED: A Powerful Query Equivalence Decider for SQL](https://www.vldb.org/pvldb/vol17/p3602-wang.pdf) [VLDB 24]
6. [VeriEQL: Bounded Equivalence Verification for Complex SQL Queries with Integrity Constraints](https://pinhanzhao.com/papers/oopsla24.pdf) [OOPSLA 24]
7. [PoneglyphDB: Efficient Non-interactive Zero-Knowledge Proofs for Arbitrary SQL-Query Verification](https://dl.acm.org/doi/pdf/10.1145/3709713) [SIGMOD 25]
8. [Query Weak Equivalence and Its Verification in Analytical Databases]() [ICDE 25]
9. [Proving Cypher Query Equivalence]() [ICDE 25]


### Cardinality Estimation
#### Histogram
1. [Equi-Depth Histograms For Estimating Selectivity Factors For Multi-Dimensional Queries](https://dl.acm.org/doi/pdf/10.1145/971701.50205) [None 87]
2. [Optimal Histograms for Limiting Worst-Case Error Propagation in the Size of Join Results](https://dl.acm.org/doi/pdf/10.1145/169725.169708) [ACM Transactions on Database Systems 93]
3. [Selectivity Estimation Without the  Attribute Value Independence Assumption](https://www.madgik.di.uoa.gr/sites/default/files/2018-06/vldb97_pp486-495.pdf) (**MHIST**) [SIGMOD 97]
4. [On Rectangular Partitionings in Two Dimensions: Algorithms, Complexity, and Applications](https://link.springer.com/chapter/10.1007/3-540-49257-7_16) [ICDT 99]
5. [Approximating multi-dimensional aggregate range queries over real attributes](https://dl.acm.org/doi/pdf/10.1145/335191.335448) (**GENHIST**) [SIGMOD 00]
6. [Independence is good: Dependency-based histogram synopses for high-dimensional data](https://dl.acm.org/doi/pdf/10.1145/376284.375685) (**DBHist**) [SIGMOD 01]
7. [STHoles: a multidimensional workload-aware histogram](http://www.cs.columbia.edu/~gravano/Papers/2001/sigmod01b.pdf) [SIGMOD 01]
8. [Selectivity Estimation using Probabilistic Models](https://dl.acm.org/doi/pdf/10.1145/375663.375727)[SIGMOD 01]
9. [A multi-dimensional histogram for selectivity estimation and fast approximate query answering](https://dl.acm.org/doi/pdf/10.5555/961322.961374) [CASCON 03]
10. [The history of histograms (abridged)](https://www.vldb.org/conf/2003/papers/S02P01.pdf) [VLDB 03]
11. [SASH: A Self-Adaptive Histogram Set for Dynamically Changing Workloads](https://www.ittc.ku.edu/~jsv/Papers/LWV03.sash.pdf)[VLDB 03]
12. [Selectivity estimators for multidimensional range queries over real attributes](https://cs.gmu.edu/~carlotta/publications/vldb090.pdf) (**GENHIST**) [VLDB 03]
13. [ISOMER: Consistent histogram construction using query feedback](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=55708905fb9ecd1ffa2f41638410f672147ccdaa) [ICDE 06]
14. [Join Over Histograms](http://www.adellera.it/static_html/investigations/join_over_histograms/JoinOverHistograms.pdf) [Alberto Dell'Era 07]
15. [Consistent Histograms In The Presence of Distinct Value Counts](https://dl.acm.org/doi/pdf/10.14778/1687627.1687723) [VLDB 08]
16. [Lightweight Graphical Models for Selectivity Estimation Without Independence Assumptions](https://dl.acm.org/doi/pdf/10.14778/3402707.3402724) [VLDB 11]
17. [Efficiently adapting graphical models for selectivity estimation](https://www.cl.cam.ac.uk/~ey204/teaching/ACS/R244_2020_2021/papers/tzoumas_VLDB_2013.pdf) [VLDB 13]
18. [Improving Accuracy and Robustness of Self-Tuning Histograms by Subspace Clustering](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7067401) [TKDE 15]

#### Sampling
1. [Two-Level Sampling for Join Size Estimation](https://15721.courses.cs.cmu.edu/spring2023/papers/18-costmodels/p759-chen.pdf) [SIGMOD 17]
2. [Combining Aggregation and Sampling (Nearly) Optimally for Approximate Query Processing](https://arxiv.org/pdf/2103.15994.pdf) [SIGMOD 21]

#### Learn Data Distribution Function
1. [Self-Tuning, GPU-Accelerated Kernel Density Models for Multidimensional Selectivity Estimation](https://dl.acm.org/doi/pdf/10.1145/2723372.2749438) [SIGMOD 15]
2. [Estimating Join Selectivities using  Bandwidth-Optimized Kernel Density Models](https://www.vldb.org/pvldb/vol10/p2085-kiefer.pdf) [VLDB 17]
3. [QuickSel: Quick Selectivity Learning  with Mixture Models](https://dl.acm.org/doi/pdf/10.1145/3318464.3389727) [SIGMOD 20]
4. [LHist: Towards Learning Multidimensional Histogram for Massive Spatial Data](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9458896) [ICDE 21]

#### Others

1. [Access path selection in a relational database management system](https://courses.cs.duke.edu/compsci516/cps216/spring03/papers/selinger-etal-1979.pdf) [SIGMOD 79]
4.  [Plan Bouquets: Query Processing without Selectivity Estimation](https://dsl.cds.iisc.ac.in/~course/DBMS/papers/planBouquet.pdf) [SIGMOD 14]
5.  [Exact Cardinality Query Optimization with Bounded Execution Cost](https://dl.acm.org/doi/pdf/10.1145/3299869.3300087) [SIGMOD 19]
6.  [JoinSketch: A Sketch Algorithm for Accurate and Unbiased Inner-Product Estimation](https://yangtonghome.github.io/uploads/JoinSketch_2023.pdf) [SIGMOD 23]
7.  [Efficient and Effective Cardinality Estimation for Skyline Family](https://dl.acm.org/doi/abs/10.1145/3588958) [SIGMOD 23]
8.  [Cardinality Estimation for Having-Clauses](https://www.vldb.org/pvldb/vol18/p28-moerkotte.pdf) [VLDB 25]

#### Survey
1. [Synopses for Massive Data: Samples, Histograms, Wavelets, Sketches](https://dsf.berkeley.edu/cs286/papers/synopses-fntdb2012.pdf) [A detailed book published in 2012]
2. [Preventing bad plans by bounding the impact of cardinality estimation errors](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=986d26dd8fa2355e9356ab2740b76e691cb22a15) [VLDB 09]
3. [Analyzing the Impact of Cardinality Estimation on Execution Plans in Microsof SQL Server](https://www.vldb.org/pvldb/vol16/p2871-dutt.pdf) [VLDB 23]

#### Special Case
12. [Selectivity Estimation for Queries Containing Predicates over Set-Valued Attributes](https://dl.acm.org/doi/pdf/10.1145/3626755) [SIGMOD 24]

### Join Order
1. [Optimal Top-Down Join Enumeration](https://15799.courses.cs.cmu.edu/spring2025/papers/08-joins2/dehaan-sigmod2007.pdf) [SIGMOD 07]
2. [A New, Highly Efficient, and Easy To Implement Top-Down Join Enumeration Algorithm](https://15799.courses.cs.cmu.edu/spring2025/papers/08-joins2/fender-icde2011.pdf) [VLDB 11]
3. [Counter Strike: Generic Top-Down Join Enumeration for Hypergraphs](https://15799.courses.cs.cmu.edu/spring2025/papers/08-joins2/fender-vldb2013.pdf) [VLDB 13]
4. [Join Order Selection with Deep Reinforcement Learning: Fundamentals, Techniques, and Challenges](https://www.vldb.org/pvldb/vol16/p3882-yan.pdf) [VLDB 23]
5. [Efficiently Computing Join Orders with Heuristic Search](https://dl.acm.org/doi/pdf/10.1145/3588927) [SIGMOD 23]
6. [Ready to Leap (by Co-Design)? Join Order Optimisation on Quantum Hardware](https://dl.acm.org/doi/pdf/10.1145/3588946) [SIGMOD 23]
7. [Quantum-Inspired Digital Annealing for Join Ordering](https://www.vldb.org/pvldb/vol17/p511-schonberger.pdf) [[VLDB 24](https://github.com/lfd/vldb24)]
8. [POLAR: Adaptive and Non-invasive Join Order Selection via Plans of Least Resistance](https://www.vldb.org/pvldb/vol17/p1350-justen.pdf) [VLDB 24] [![](https://img.shields.io/github/stars/damslab/reproducibility?style=social&label=Code+Stars)](https://github.com/damslab/reproducibility/tree/master/vldb2024-POLAR)
9. [Sub-optimal Join Order Identification with L1-error](https://dl.acm.org/doi/pdf/10.1145/3639272) [SIGMOD 24]
10. [DPconv: Super-Polynomially Faster Join Ordering](https://15799.courses.cs.cmu.edu/spring2025/papers/07-joins1/stoian-sigmod2025.pdf) [SIGMOD 25]
11. [Debunking the Myth of Join Ordering: Toward Robust SQL Analytics](https://arxiv.org/pdf/2502.15181) [SIGMOD 25]
12. [AJOSC: Adaptive join order selection for continuous queries on data streams]() [SIGMOD 25]

### Join Algorithms
1. [Massively Parallel Sort-Merge Joins in Main Memory Multi-Core Database Systems](https://15721.courses.cs.cmu.edu/spring2023/papers/12-sortmergejoins/p1064-albutiu.pdf) [VLDB 12]
2. [Leapfrog Triejoin: a worst-case optimal join algorithm](https://arxiv.org/pdf/1210.0481.pdf) [International Conference on Database Theory 12]
3. [Lightning Fast and Space Efficient Inequality Joins](https://vldb.org/pvldb/vol8/p2074-khayyat.pdf) [VLDB 15]
4. [An Experimental Comparison of Thirteen Relational Equi-Joins in Main Memory](https://15721.courses.cs.cmu.edu/spring2018/papers/19-hashjoins/schuh-sigmod2016.pdf) [SIGMOD 16]
5. [Worst-Case Optimal Join Algorithms: Techniques, Results, and Open Problems](https://arxiv.org/pdf/1803.09930.pdf) [SIGMOD 18]
6. [Adopting Worst-Case Optimal Joins in Relational Database Systems](https://www.vldb.org/pvldb/vol13/p1891-freitag.pdf) [VLDB 20]
7. [Free Join: Unifying Worst-Cast Optimal and Traditional Joins](https://arxiv.org/pdf/2301.10841.pdf) [arXiv 23]
8. [Reservoir Sampling over Joins](https://arxiv.org/pdf/2404.03194.pdf#page=1.48) [SIGMOD 24]
9. [Predicate Transfer: Efficient Pre-Filtering on Multi-Join Queries](https://www.cidrdb.org/cidr2024/papers/p22-yang.pdf) [CIDR 24]
10. [Efficiently Processing Joins and Grouped Aggregations on GPUs](https://dl.acm.org/doi/pdf/10.1145/3709689) [SIGMOD 25]
11. [HoneyComb: A Parallel Worst-Case Optimal Join on Multicores]() [SIGMOD 25]
12. [SwiftSpatial: Spatial Joins on Modern Hardware]() [SIGMOD 25]
13. [Accelerate Distributed Joins with Predicate Transfer]() [SIGMOD 25]

### Sub-Query
1. [Unnesting Arbitrary Queries](https://btw-2015.informatik.uni-hamburg.de/res/proceedings/Hauptband/Wiss/Neumann-Unnesting_Arbitrary_Querie.pdf) [15]

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
3. [Query optimization through the looking glass, and what we found running the Join Order Benchmark](https://15799.courses.cs.cmu.edu/spring2025/papers/13-cardinalities1/leis-vldbj2017.pdf) [VLDBJ 17]
4. [A Survey on Advancing the DBMS Query Optimizer: Cardinality Estimation, Cost Model, and Plan Enumeration](https://arxiv.org/pdf/2101.01507.pdf) [VLDB 21]
5. [Have query optimizers hit the wall?](https://link.springer.com/article/10.1007/s00778-021-00689-y) [VLDBJ 22]
6. [Cardinality Estimation in DBMS: A Comprehensive Benchmark Evaluation](https://dl.acm.org/doi/pdf/10.14778/3503585.3503586) [VLDB 22]
7. [Data dependencies for query optimization: a survey](https://link.springer.com/article/10.1007/s00778-021-00676-3) [VLDBJ 22]
8. [Simple Adaptive Query Processing vs. Learned Query Optimizers: Observations and Analysis](https://www.vldb.org/pvldb/vol16/p2962-zhang.pdf) [VLDB 23]

### Index
1. [SQL Server Column Store Indexes](https://15721.courses.cs.cmu.edu/spring2023/papers/04-olapindexes/p1177-larson.pdf) [SIGMOD 11]
2. [The Adaptive Radix Tree: ARTful Indexing for Main-Memory Databases](https://db.in.tum.de/~leis/papers/ART.pdf) [ICDE 13]
3. [Column Sketches: A Scan Accelerator for Rapid and Robust Predicate Evaluation](https://15721.courses.cs.cmu.edu/spring2023/papers/04-olapindexes/hentschel-sigmod18.pdf) [SIGMOD 18]
4. [CUBIT: Concurrent Updatable Bitmap Indexing](https://www.vldb.org/pvldb/vol18/p399-athanassoulis.pdf) [VLDB 25]

## Query Execution
1. [MonetDB/X100: Hyper-Pipelining Query Execution](https://www.cidrdb.org/cidr2005/papers/P19.pdf) [CIDR 05] 
2. [DSM vs. NSM: CPU performance tradeoffs in block-oriented query processing](https://dl.acm.org/doi/10.1145/1457150.1457160) [DaMoN 08]
3. [Materialization Strategies in the Vertica Analytic Database: Lessons Learned](https://15721.courses.cs.cmu.edu/spring2023/papers/06-execution/shrinivas-icde2013.pdf) [ICDE 13]
4. [Adaptive Query Processing in the Looking Glass](https://15799.courses.cs.cmu.edu/spring2025/papers/18-aqp/babu-cidr2015.pdf) [CIDR 15]
5. [Rethinking SIMD Vectorization for In-Memory Databases](https://15721.courses.cs.cmu.edu/spring2024/papers/06-vectorization/p1493-polychroniou.pdf) [SIGMOD 15]
6. [Efficient Processing of Window Functions in Analytical SQL Queries](https://www.vldb.org/pvldb/vol8/p1058-leis.pdf) [VLDB 15]
7. [Access Path Selection in Main-Memory Optimized Data Systems: Should I Scan or Should I Probe?](https://15721.courses.cs.cmu.edu/spring2023/papers/06-execution/kester-sigmod17.pdf) [SIGMOD 17]
8. [Looking Ahead Makes Query Plans Robust](https://15799.courses.cs.cmu.edu/spring2025/papers/18-aqp/p889-zhu.pdf) [VLDB 17]
9. [Building Advanced SQL Analytics From Low-Level Plan Operators](https://db.in.tum.de/~kohn/papers/lolepops-sigmod21.pdf) [SIGMOD 21]
10. [SkinnerMT: Parallelizing for Efficiency and Robustness in Adaptive Query Processing on Multicore Platforms](https://www.vldb.org/pvldb/vol16/p905-wei.pdf) [VLDB 22]
11. [ChainedFilter: Combining Membership Filters by Chain Rule](https://dl.acm.org/doi/pdf/10.1145/3626721) [SIGMOD 24]
12. [Saving Money for Analytical Workloads in the Cloud](https://www.vldb.org/pvldb/vol17/p3602-wang.pdf) [VLDB 24]
13. [Adaptive and Robust Query Execution for Lakehouses at Scale](https://www.vldb.org/pvldb/vol17/p3947-bu.pdf) [VLDB 24]
14. [DuckDB-SGX2: The Good, The Bad and The Ugly within Confidential Analytical Query Processing](https://dl.acm.org/doi/pdf/10.1145/3662010.3663447) [DaMoN 24]
15. [The Key to Effective UDF Optimization: Before Inlining, First Perform Outlining](https://www.vldb.org/pvldb/vol18/p1-arch.pdf) [VLDB 25]
16. [High-Performance Query Processing with NVMe Arrays: Spilling without Killing Performance](https://www.cs.cit.tum.de/fileadmin/w00cfj/dis/papers/umami.pdf) [SIGMOD 25]
17. [Data Chunk Compaction in Vectorized Execution](https://dl.acm.org/doi/pdf/10.1145/3709676) [SIGMOD 25]
18. [FAAQP: Fast and Accurate Approximate Query Processing based on Bitmap-augmented Sum-Product Network]() [SIGMOD 25]

## Data Dependency Search
1. [Discovering Functional Dependencies through Hitting Set Enumeration](https://dl.acm.org/doi/pdf/10.1145/3639298) [SIGMOD 24]

## Query Compilation
1. [How to Architect a Query Compiler](https://15721.courses.cs.cmu.edu/spring2023/papers/09-compilation/shaikhha-sigmod2016.pdf) [SIGMOD 16]
2. [Adaptive Execution of Compiled Queries](https://15721.courses.cs.cmu.edu/spring2023/papers/09-compilation/kohn-icde2018.pdf) [ICDE 18]

## Bugs Detection

### Functional Bug
#### Logical Bug
1. [Search-Based Test Data Generation for SQL Queries](https://dl.acm.org/doi/10.1145/3180155.3180202) [ICSE 18]
2. [Finding Bugs in Database Systems via Query Partitioning](https://dl.acm.org/doi/pdf/10.1145/3428279) [OOPSLA 20]
3. [Detecting Optimization Bugs in Database Engines via Non-Optimizing Reference Engine Construction](https://arxiv.org/pdf/2007.08292) [FSE 20]
4. [Testing Database Engines via Query Plan Guidance](https://dl.acm.org/doi/10.1109/ICSE48619.2023.00174) [ICSE 23]
5. [GDsmith: Detecting Bugs in Cypher Graph Database Engines](https://taoxiease.github.io/publications/issta23-gdsmith.pdf) [ISSTA 23]
6. [Snowcat: Efficient Kernel Concurrency Testing using a Learned Coverage Predictor](https://dl.acm.org/doi/pdf/10.1145/3600006.3613148) [SOSP 23]
7. [Detecting Isolation Bugs via Transaction Oracle Construction](https://wsdou.github.io/papers/2023-icse-troc.pdf) [ICSE 23]
8. [Detecting Logic Bugs of Join Optimizations in DBMS](https://dl.acm.org/doi/pdf/10.1145/3588909) [SIGMOD 23 Best Paper]
9. [Detecting Metadata-Related Logic Bugs in Database Systems via Raw Database Construction](https://www.vldb.org/pvldb/vol17/p1884-song.pdf) [VLDB 24]
10. [CONI: Detecting Database Connector Bugs via State-Aware Test Case Generation](http://www.wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_25/coni_ICSE25.pdf) [ICSE 24]
11. [Keep It Simple: Testing Databases via Differential Query Plans](https://bajinsheng.github.io/assets/pdf/dqp_sigmod24.pdf) [SIGMOD 24]
12. [Plume: Efficient and Complete Black-Box Checking of Weak Isolation Levels](https://dl.acm.org/doi/pdf/10.1145/3689742) [OOPSLA2 2024]
13. [DBStorm: Generating Various Effective Workloads for Testing Isolation Levels](https://dl.acm.org/doi/10.1145/3650212.3680318) [ISSTA 24]
14. [SQLaser: Detecting DBMS Logic Bugs with Clause-Guided Fuzzing](https://arxiv.org/pdf/2407.04294) [arXiv 24]
15. [Understanding and Detecting SQL Function Bugs](http://wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_25/soft_eurosys25.pdf) [EuroSys 25]
16. [Understanding and Reusing Test Suites Across Database Systems](https://arxiv.org/pdf/2410.21731) [SIGMOD 25]
17. [Detecting Logic Bugs in Database Engines via Equivalent Expression Transformation](https://www.usenix.org/system/files/osdi24-jiang.pdf) [ATC 24]
18. [THANOS: DBMS Bug Detection via Storage Engine Rotation Based Differential Testing](http://www.wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_25/Thanos_ICSE25.pdf) [ICSE 25]
19. [Semantic Conformance Testing of Relational DBMS](https://dl.acm.org/doi/pdf/10.14778/3712221.3712247) [VLDB 25]
20. [Automatic Database Configuration Debugging using Retrieval-Augmented Language Models]() [SIGMOD 25]
21. [Finding Logic Bugs in Spatial Database Engines via Affine Equivalent Input](https://www.arxiv.org/pdf/2410.12496) [SIGMOD 25]
22. [Constant Optimization Driven Database System Testing](https://dl.acm.org/doi/pdf/10.1145/3709674) [SIGMOD 25]
23. [Blackbox Fuzzing of Distributed Systems with Multi-Dimensional Inputs and Symmetry-Based Feedback Pruning](https://jzuming.github.io/paper/ndss25-zou.pdf) [NDSS 25]
24. [Finding Logic Bugs in Graph-processing Systems via Graph-cutting]() [SIGMOD 25]
25. [Detecting Schema-Related Logic Bugs in Relational DBMSs via Equivalent Database Construction]() [VLDB 25]
26. [Simple Testing Can Expose Most Critical Transaction Bugs: Understanding and Detecting Write-Specific Serializability Violations in Database Systems]() [VLDB 25]
27. [Detecting Isolation Anomalies in Relational DBMSs]() [ISSTA 25]
28. [Model Checking Guided Incremental Testing for Distributed Systems]() [ISSTA 25]
29. [Scaling Automated Database System Testing](https://arxiv.org/pdf/2503.21424) [arXiv 25]
30. [Testing Database Systems with Large Language Model Synthesized Fragments](https://arxiv.org/pdf/2505.02012) [arXiv 25]
31. [Detecting Schema-Related Logic Bugs in Relational DBMSs via Equivalent Database Construction](https://wsdou.github.io/papers/2025-vldb-ddlcheck.pdf) [VLDB 25]
32. [Simple Testing Can Expose Most Critical Transaction Bugs: Understanding and Detecting Write-Specific Serializability Violations in Database Systems](https://wsdou.github.io/papers/2025-vldb-writecheck.pdf) [VLDB 25]
33. [Detecting Isolation Anomalies in Relational DBMSs](https://wsdou.github.io/papers/2025-issta-isorel.pdf) [ISSTA 25]

#### Crash Bug
1. [Sequence-Oriented DBMS Fuzzing](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10184875) [ICDE 23]
2. [DynSQL: Stateful Fuzzing for Database Management Systems with Complex and Valid SQL Query Generation](https://www.usenix.org/system/files/usenixsecurity23-jiang-zu-ming.pdf) [ATC 23]
3. [Sedar: Obtaining High-Quality Seeds for DBMS Fuzzing via Cross-DBMS SQL Transfer](https://dl.acm.org/doi/abs/10.1145/3597503.3639210) [ICSE 24]

### Performance Bug
1. [APOLLO: automatic detection and diagnosis of performance regressions in database systems](https://dl.acm.org/doi/pdf/10.14778/3357377.3357382) [VLDB 19]
2.  [CERT: Finding Performance Issues in Database Systems Through the Lens of Cardinality Estimation](https://arxiv.org/pdf/2306.00355) [ICSE 24]
3.  [PUPPY: Finding Performance Degradation Bugs in DBMSs via Limited-Optimization Plan Construction](http://www.wingtecher.com/themes/WingTecherResearch/assets/papers/paper_from_25/Puppy_ICSE25.pdf) [ICSE 25]

### Survey
1. [A Comprehensive Survey on Database Management System Fuzzing: Techniques, Taxonomy and Experimental Comparison](https://arxiv.org/pdf/2311.06728) [arXiv 23]
2. [Survey on Database Management System Fuzzing Techniques](https://jos.org.cn/jos/article/pdf/7048) [Journal of Software 24]

### Static Analysis
1. [Enhancing Static Analysis for Practical Bug Detection: An LLM-Integrated Approach](https://dl.acm.org/doi/pdf/10.1145/3649828) [PACMPL 24]

### Casual Inference
1. [Substructure-aware Log Anomaly Detection](https://www.vldb.org/pvldb/vol18/p213-tang.pdf) [VLDB 25]
2. [From Logs to Causal Inference: Diagnosing Large Systems]() [VLDB 25]
3. [RCRank: Multimodal Ranking of Root Causes of Slow Queries in Cloud Database Systems]() [VLDB 25]
4. [OpDiag: Unveiling Database Performance Anomalies through Query Operator Attribution](https://github.com/hjhhsy120/opdiag) [TKDE 25]

### Code Location
1. [Fault Localization via Fine-tuning Large Language Models with Mutation Generated Stack Traces](https://arxiv.org/pdf/2501.18005) [arXiv 25]

## Storage
1. [What Modern NVMe Storage Can Do, And How To Exploit It: High-Performance I/O for High-Performance Storage Engines](https://www.vldb.org/pvldb/vol16/p2090-haas.pdf) [VLDB 23]
2. [An Empirical Evaluation of Columnar Storage Formats](https://www.vldb.org/pvldb/vol17/p148-zeng.pdf) [VLDB 24]
3. [Apache Arrow DataFusion: A Fast, Embeddable, Modular Analytic Query Engine](https://dl.acm.org/doi/pdf/10.1145/3626246.3653368) [SIGMOD 24]
4. [Boosting OLTP Performance with Per-Page Logging on NVDIMM](https://dl.acm.org/doi/pdf/10.1145/3709667) [SIGMOD 25]
### LSM-Tree
1. [Dissecting, Designing, and Optimizing LSM-based Data Stores](https://dl.acm.org/doi/pdf/10.1145/3514221.3522563) [SIGMOD 22 Tutorial]
2. [Magma: A High Data Density Storage Engine Used in Couchbase](https://www.vldb.org/pvldb/vol15/p3496-lakshman.pdf#page=1.23) [VLDB 22]
3. [CaaS-LSM: Compaction-as-a-Service for LSM-based Key-Value Stores in Storage Disaggregated Infrastructure](https://qiaolin-yu.github.io/pubs/V2mod124-yu.pdf) [SIGMOD 24]
4. [NULLS! Revisiting Null Representation in Modern Columnar Formats](https://db.cs.cmu.edu/papers/2024/zeng-damon24.pdf) [DaMoN 24]
5. [CAMAL: Optimizing LSM-trees via Active Learning](https://arxiv.org/pdf/2409.15130) [SIGMOD 25]
6. [Disco: A Compact Index for LSM-trees](https://dl.acm.org/doi/pdf/10.1145/3709683) [SIGMOD 25]
7. [Randomized Sketches for Quantile in LSM-tree based Store](https://dl.acm.org/doi/pdf/10.1145/3709717) [SIGMOD 25]
8. [Rethinking The Compaction Policies in LSM-trees]() [SIGMOD 25]
9. [DFlush: DPU-Offloaded Flush for Disaggregated LSM-based Key-Value Stores]() [SIGMOD 25]

### Kd-Tree
1. [Parallel kd-tree with Batch Updates](https://dl.acm.org/doi/pdf/10.1145/3709712) [SIGMOD 25]

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
6. [Rapid Data Ingestion through DB-OS Co-design](https://dl.acm.org/doi/pdf/10.1145/3709718) [SIGMOD 25]
7. [Practical DB-OS Co-Design with Privileged Kernel Bypass](https://dl.acm.org/doi/pdf/10.1145/3709714) [SIGMOD 25]

### Transactions
1. [Low-Latency Transaction Scheduling via Userspace Interrupts: Why Wait or Yield When You Can Preempt?]() [SIGMOD 25]
2. [Are database system researchers making correct assumptions about transaction workloads?]() [SIGMOD 25]
3. [BPF-DB: A Kernel-Embedded Transactional Database Management System For eBPF Applications]() [SIGMOD 25]
4. [Styx: Transactional Stateful Functions on Streaming Dataflows]() [SIGMOD 25]
5. [GTX: A Write-Optimized Latch-free Graph Data System with Transactional Support]() [SIGMOD 25]
6. [Wait and See: A Delayed Transactions Partitioning Approach in Deterministic Database Systems for Better Performance]() [SIGMOD 25]
7. [Moving on From Group Commit: Autonomous Commit Enables High Throughput and Low Latency on NVMe SSDs]() [SIGMOD 25]
8. [A Hybrid Approach to Integrating Deterministic and Non-deterministic Concurrency Control in Database Systems](https://www.vldb.org/pvldb/vol18/p1376-lu.pdf) [VLDB 25]
9. [VerIso: Verifiable Isolation Guarantees for Database Transactions](https://www.vldb.org/pvldb/vol18/p1362-ghasemirad.pdf#page=1.25) [VLDB 25]

### Survey
1. [What Goes Around Comes Around... And Around...](https://db.cs.cmu.edu/papers/2024/whatgoesaround-sigmodrec2024.pdf) [SIGMOD 24]
2. [Cloud-Native Database Systems and Unikernels: Reimagining OS Abstractions for Modern Hardware](https://www.vldb.org/pvldb/vol17/p2115-leis.pdf) [VLDB 24]

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
1. [Adaptive HTAP through elastic resource scheduling](https://arxiv.org/pdf/2004.05437) [SIGMOD 20]
2. [Proteus: Autonomous Adaptive Storage for Mixed Workloads](https://cs.uwaterloo.ca/~mtabebe/publications/abebeProteus2022TR.pdf) [SIGMOD 22]
3. [TiQuE: Improving the Transactional Performance of Analytical Systems for True Hybrid Workloads](https://www.vldb.org/pvldb/vol16/p2274-faria.pdf) [VLDB 23]
4. [Deploying Computational Storage for HTAP DBMSs Takes More Than Just Computation Offloading](https://www.vldb.org/pvldb/vol16/p1480-jung.pdf) [VLDB 23]
5. [Log Replaying for Real-Time HTAP: An Adaptive Epoch-based Two-Stage Framework](https://www.computer.org/csdl/proceedings-article/icde/2024/171500c096/1YOtqw9cWJ2) [ICDE 24]
6. [Two Birds With One Stone: Designing a Hybrid Cloud Storage Engine for HTAP](https://vldb.org/pvldb/vol17/p3290-schmidt.pdf) [VLDB 24]

### Result Replay
1. [DoppelGanger++: Towards Fast Dependency Graph Generation for Database Replay](https://dl.acm.org/doi/pdf/10.1145/3639322) [SIGMOD 24]
2. [Fast Parallel Recovery for Transactional Stream Processing on Multicores](https://ieeexplore.ieee.org/document/10597762/) [ICDE 24]

### Benchmark
#### Survey
1. [Surprise Benchmarking: The Why, What, and How](https://dl.acm.org/doi/pdf/10.1145/3662165.3662763) [DBTest 24]

#### AI
1. [TPCx-AI - An Industry Standard Benchmark for Artificial Intelligence and Machine Learning Systems](https://dl.acm.org/doi/pdf/10.14778/3611540.3611554) [VLDB 23]

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
10. [CloudyBench: A Testbed for A Comprehensive Evaluation of Cloud-Native Databases]() [ICDE 25]

### Time Series
1. [An Experimental Evaluation of Anomaly Detection in Time Series](https://www.vldb.org/pvldb/vol17/p483-zhang.pdf) [VLDB 24]

### Multi-Model
1. [Practical and Asymptotically Optimal Quantization of High-Dimensional Vectors in Euclidean Space for Approximate Nearest Neighbor Search]() [SIGMOD 25]
2. [MIRAGE-ANNS: Mixed Approach Graph-based Indexing for Approximate Nearest Neighbor Search]() [SIGMOD 25]
#### Benchmark
1. [Multi-model Databases: A New Journey to Handle the Variety of Data](https://www.cs.helsinki.fi/u/jilu/documents/Multi_model_Databases__A__New_Journey_to_Handle_the_Variety_of_DataFinal.pdf) [CSUR 19]
2. [M2Bench: A Database Benchmark for Multi-Model Analytic Workloads](https://www.vldb.org/pvldb/vol16/p747-moon.pdf) [VLDB 23]
3. [MMSBench-Net: Scenario-Based Evaluation of Multi-Model Database Systems](https://gvdb23.informatik.uni-stuttgart.de/wp-content/uploads/2023/06/GvDB2023_Lengweiler.pdf) [23]
4. [MMDBench: A Benchmark for Hybrid Query in Multimodal Database](https://bluejoe2008.github.io/pub/MMDBench__A_Benchmark_for_Hybrid_Query_in_Multimodal_Database.pdf) [24]

### Vector Database
#### Survey
1. [Are There Fundamental Limitations in Supporting Vector Data Management in Relational Databases? A Case Study of PostgreSQL](https://www.cs.purdue.edu/homes/csjgwang/pubs/ICDE24_VecDB.pdf) [ICDE 24]
2. [Survey of Vector Database Management Systems](https://arxiv.org/pdf/2310.14021#page=3.39) [VLDBJ 24]
3. [Vector Database Management Techniques and Systems](https://dl.acm.org/doi/pdf/10.1145/3626246.3654691) [SIGMOD 24]
4. [BigVectorBench: Heterogeneous Data Embedding and Compound Queries are Essential in Evaluating Vector Databases](https://www.vldb.org/pvldb/vol18/p1536-zhan.pdf) [VLDB 25]

### Algorithm
1. [FlowWalker: A Memory-efficient and High-performance GPU-based Dynamic Graph Random Walk Framework](https://www.vldb.org/pvldb/vol17/p1788-mei.pdf) [VLDB 24]
2. [Practical and Asymptotically Optimal Quantization of High-Dimensional Vectors in Euclidean Space for Approximate Nearest Neighbor Search](https://arxiv.org/pdf/2409.09913) [SIGMOD 25]

### Distributed Systems
1. [Consistency in Non-Transactional Distributed Storage Systems](https://arxiv.org/pdf/1512.00168) [arXiv 15]
2. [NOC-NOC: Towards Performance-optimal Distributed Transactions](https://dl.acm.org/doi/pdf/10.1145/3639264#page=1.52) [SIGMOD 24]
3. [Native Distributed Databases: Problems, Challenges and Opportunities](https://www.vldb.org/pvldb/vol17/p4217-xu.pdf) [VLDB 24 Tutorial]

### [OLTP](https://github.com/wengsy150943/Paper4OLTPandConcurrencyTesting)
#### Survey
1. [A survey on transactional stream processing](https://link.springer.com/article/10.1007/s00778-023-00814-z) [VLDBJ 23]
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
