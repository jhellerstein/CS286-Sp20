---
layout: default
---


# Graduate Database Systems (Spring 2020)

* **When**: *Tuesday/Thursday 9:30-12:00*
* **Where**: *Soda 320*
* **Instructor**: [Joe Hellerstein](https://dsf.berkeley.edu/jmh)
   * **Office Hours:** Friday@11, Tuesday@2:30 in 789 Soda.
* **Announcements**: [Piazza](https://piazza.com/class/k5mxqow7ugc42v)
<!-- * **Sign Up** [Google Form at http://bit.ly/cs286-20](http://bit.ly/cs286-20) -->
<!-- * **Sign-up to Present**: [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1p8q7vnds821-_w43H-IppjMKPV5KpOl3fVPZCY27RpM/edit#gid=0) Later in the semester we will be doing student presentations which we will fill in here. -->
* If you have reading suggestions please send a pull request to this course website on [Github](https://github.com/jhellerstein/CS286-Sp20) by modifying the [index.md](https://github.com/jhellerstein/CS286-Sp20/blob/master/index.md) file.



## Course Description
The Database Systems field has been exploring issues in data 
storage, management, processing and analysis for over 50 years. In our data-rich 21st century, the lessons of the field apply broadly across Computer Science and beyond.

In this course we will study a range of papers from the distant and recent
past. The goal is to provide a strong foundation for applied computer 
scientists of many stripes, whether or not they plan to use the techniques
in the context of traditional database systems. Given the breadth and history 
of the field, it is not possible to cover it comprehensively. Our focus
will largely be on core database systems topics, and while the emphasis will
be on systems work we will not shy away from theory. The readings will mix
classic papers with emerging results, and revisit topics that may be ripe for revival given current technology trends.



## Course Format
The course will have two phases. For the first few weeks, we will read papers
from some of the foundational systems in the field. Classes will be in lecture
format for this phase, with class discussion. This will give an overview of 
recurring themes in the field at a relatively high level, and provide a common
basis for subsequent papers.

In the second phase, we will follow a weekly pattern used in other
Berkeley graduate courses in recent years. The Thursday lecture will be presented by Prof. Hellerstein and will cover the context of the topic as well as a high-level overview of the reading for the week.  The Tuesday lecture will be organized around a mini program committee meeting for the weeks readings.  Students will be required to submit detailed reviews for a subset of the papers and lead the paper review discussions.  The goal of this format is to both build a mastery of the material and develop your ability to evaluate and review research--including your own.

As a template, we will use these ["program committee" template slides](https://docs.google.com/presentation/d/1bxGL9cQziVhGQzhq-rBXxuYnuP3745Ye3PRg_1QZj3I/edit#slide=id.g62c62a7e48_0_75) from Joseph Gonzalez.


## Syllabus



<!-- This is the dates for all the lectures -->
{% capture dates %}
1/21/20
1/23/20
1/28/20
1/30/20
2/4/20
2/6/20
2/11/20
2/13/20
2/18/20
2/20/20
2/25/20
2/27/20
3/3/20
3/5/20
3/10/20
3/12/20
3/17/20
3/19/20
3/24/20
3/26/20
3/31/20
4/2/20
4/7/20
4/9/20
4/14/20
4/16/20
4/21/20
4/23/20
4/30/20
5/5/20
5/7/20
{% endcapture %}
{% assign dates = dates | split: " " %}

This is a tentative schedule.  Specific readings are subject to change as new material is published.

<a href="#today"> Jump to Today </a>

<table class="table table-striped syllabus">
<thead>
   <tr>
      <th style="width: 5%"> Week </th>
      <th style="width: 10%"> Date (Lec.) </th>
      <th style="width: 85%"> Topic </th>
   </tr>
</thead>
<tbody>


{% include syllabus_entry %}
## Introduction and Course Overview

This lecture will be an overview of the class and requirements. We will go over the history of the field and review some core architectural questions that need to be addressed in any data serving system.

* [Lecture notes](https://docs.google.com/document/d/1xYb_nHPbjmVAF_ahUvdRx2OOxI_m9fUP0bpdOUepqXk/edit#)

<div class="reading">
<div class="required_reading" markdown="1">
* [Architecture of a Database System](https://scholar.google.com/scholar?cluster=11466590537214723805), *Sections 1-3 only*.

<div class="optional_reading" markdown="1">
* [A History and Evaluation of System R](https://scholar.google.com/scholar?cluster=9472628621431764243&hl=en&as_sdt=0,5)
* [The Design and Implementation of INGRES](https://scholar.google.com/scholar?cluster=4436012605119588041&hl=en&as_sdt=0,5)
* [Database System Geneaology Map](https://hpi.de/naumann/projects/rdbms-genealogy.html)
* [How to read a paper](https://web.stanford.edu/class/ee384m/Handouts/HowtoReadPaper.pdf) provides some pretty good advice on how to read papers effectively.
* Timothy Roscoe's [writing reviews for systems conferences](https://people.inf.ethz.ch/troscoe/pubs/review-writing.pdf) will also help you in the reviewing process.
</div>
</div>
</div>


{% include syllabus_entry %}
## Pioneering Systems Group #1: IBM
After the landmark success of System R in the 1970s (which you hopefully 
studied in CS262A), IBM Almaden's database group
was among the first to tackle the challenge of Distributed Databases in the 1980s. We'll read two detailed papers from the project, one on transaction processing (specifically two-phase commit) and one on query optimization.

* [Lecture notes](https://docs.google.com/document/d/1rOt8eAwTf4iIX-qzIRhatgbOmSJ--mh9Z7F0-ywjo3c/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [Transaction Management in the R* Distributed Database Management System](http://scholar.google.com/scholar?cluster=6135007404184895390)
* [R* optimizer validation and performance evaluation for distributed queries](https://scholar.google.com/scholar?cluster=3445654609264687962&hl=en&as_sdt=0,5)

<div class="optional_reading" markdown="1">
* [Extensions to Starburst: Objects, Types, Functions and Rules](https://scholar.google.com/scholar?cluster=1563874908496372865&hl=en&as_sdt=0,5) Following R*, the Almaden team shifted its focus in the late '80s and '90s to database system extensibility in the Starburst project. Many of the ideas in Starburst were also explored in the Postgres and Exodus projects we'll be reading about shortly. Starburst had significant impact on IBM's DB2 database through the 1990s and 2000s.   
</div>
</div>
</div>

{% include syllabus_entry %}
## Pioneering Systems Group #2: Berkeley
Berkeley's INGRES project was the competitor to System R in the 1970s.
Postgres was the follow-on project in the 1980's and '90s, focusing on
building an *extensible* database system that could handle new data types, richer queries and even ad hoc computation (UDFs) "close to the data". The programmability of Postgres UDFs presaged the big data movement of the 2000's. Postgres was a classic "second system", rich in ideas, not all of which panned out. But Postgres' extensible architecture arguably saved it from the [second system effect](https://en.wikipedia.org/wiki/Second-system_effect), and its architecture today is quite similar to how it looked in the early 1990s.

* [Lecture notes](https://docs.google.com/document/d/14LTjziRp3gCI_g8C8RQzx7dZeUx7PlsOYKX6kWutqiQ/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [The POSTGRES Next-Generation Database System](http://scholar.google.com/scholar?cluster=6521586065605065941)
* [The Design of the Postgres Storage System](https://scholar.google.com/scholar?cluster=6675294870941893293&hl=en&as_sdt=0,5)

<div class="optional_reading" markdown="1">
* [Looking Back at Postgres](https://arxiv.org/abs/1901.01973) A retrospective on the Postgres project from the eyes of a former graduate student.   
</div>
</div>
</div>

{% include syllabus_entry %}
## Pioneering Systems Group #3: Wisconsin
Historically the database systems field was relatively small in academia. 
One of the largest and most influential academic groups was at the University of Wisconsin. In addition to a range of theory work, Wisconsin in the 1980's and 1990's pursued themes in both Parallel Databases in the Gamma project (presaging the data warehouse and big data movements) and Object-Oriented Databases in the Exodus and SHORE projects (the "losing side" in the database extensibility wars. Or was it?)

* [Lecture notes](https://docs.google.com/document/d/1L9siK1VQn6e9tUWoA3TF16Y6lnEdEnsGte31NuxkdVM/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [The Gamma Database Machine Project](http://scholar.google.com/scholar?cluster=8912521541627865753)
* [The Architecture of the Exodus Extensible DBMS](https://scholar.google.com/scholar?cluster=8382804381348901729&hl=en&as_sdt=0,5)

<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

{% include syllabus_entry %}
## Foundations of Concurrency Control: Bernstein and Goodman
Bernstein and Goodman's 1981 Computing Surveys paper covers nearly every trick imaginable in concurrency control. Everything since is very likely a combination of techniques in this paper. 

* [Lecture notes](https://docs.google.com/document/d/1mrS7GSb9GYhMo7PyUunfXdS79ZOXIhIoE5OZe9SWr0c/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [Concurrency Control in Distributed Database Systems](http://db.cs.berkeley.edu/cs286/papers/bernstein-csur1981.pdf)

<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

{% include syllabus_entry %}
## Concurrency Control Performance
Our first paper is a classic example of good performance work, which cleaned up controversies in prior work by questioning their assumptions and building the right simulation.

Our second paper is a seminal but largely overlooked work by Kung and Papadimitriou defining what "optimality" might mean for concurrency control performance. It embraces au courant ideas like exploiting program semantics and integrity constraints into the definition and looks at how much they can help in theory.


* [Lecture notes](https://docs.google.com/document/d/1Huu1zMfD0Zh0rkQ0KoVomLd5RQr5hJdqhrFRMN32bWg/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [Concurrency control performance modeling: alternatives and implications](https://dsf.berkeley.edu/cs286/papers/carey-tods1987.pdf)
 * [An optimality theory of concurrency control for Databases](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.433.7591&rep=rep1&type=pdf)
<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

{% include syllabus_entry %}
## Indexing
Our first paper is a classic reference on B-tree concurrency, a surprisingly tricky topic. Later in the semester we will likely see more recent adaptations of this work for main-memory database. The next two papers represent classic and widely-used indexing techniques, both of which are due to the late [Pat O'Neil](https://en.wikipedia.org/wiki/Patrick_O%27Neil), who passed away this past year. His wife Betty was a frequent co-author.

Optional reading for those who are curious about concurrency and recovery for extensible DBMSs.

* [Slides for class discussion](https://docs.google.com/presentation/d/1yD3-v_9YCfKYirHcjf0SgxHFqZMsBfGj2KUKJocG0N4/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [Efficient locking for concurrent operations on B-trees](https://scholar.google.com/scholar?cluster=4919657903329720293&hl=en&as_sdt=0,5)
* [Improved query performance with variant indexes](http://scholar.google.com/scholar?cluster=3279297021955127822)
* [The log-structured merge-tree (LSM-tree)](http://scholar.google.com/scholar?cluster=5832040552580693098)
<div class="optional_reading" markdown="1">
   [Concurrency and recovery in generalized search trees](https://scholar.google.com/scholar?cluster=425098644227477639&hl=en&as_sdt=0,5)
</div>
</div>
</div>

{% include syllabus_entry %}
## Introduction to Weak Isolation and Replica Consistency
I will be out at Microsoft on a RISE faculty expedition. [Chenggang Wu](http://cgwu.io/) will present the lecture.

* [Chenggang's slides on Isolation Levels](https://drive.google.com/file/d/1hxAO9HCmcICEEgBmo4sPT8-JHMCF870P/view?usp=sharing)

{% include syllabus_entry %}
## Weak Isolation
Three papers. A classic, co-authored by Atul Adya and occasional database research contributor and Turing winner [Barbara Liskov](https://en.wikipedia.org/wiki/Barbara_Liskov), a brand new look at the problem co-authored by incoming Berkeley faculty [Natacha Crooks](https://nacrooks.github.io/), and yet another appearance from Pat and Betty O'Neil discussing a very common weak isolation mode: Snapshot Isolation.

Optional reading from then-Berkeley PhD student [Peter Bailis](http://www.bailis.org/), which identifies and pushes the boundary of what's possible with coordination-free isolation levels.

* [Slides for class discussion](https://docs.google.com/presentation/d/1yd6Hh7oLOrOHWQ6QLfvvCv4w-MCf-I8tugDdtXgMnE4/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [Generalized Isolation Level Definitions](http://db.cs.berkeley.edu/cs286/papers/adya-icde2000.pdf)
* [Seeing is believing: A client-centric specification of database isolation](https://scholar.google.com/scholar?cluster=12578509121254706480&hl=en&as_sdt=0,5)
* [Precisely Serializable Snapshot Isolation](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.307.6793&rep=rep1&type=pdf)
<div class="optional_reading" markdown="1">
 * [Scalable Atomic Visibility with RAMP Transactions](http://www.bailis.org/papers/ramp-sigmod2014.pdf)
 * [Highly Available Transactions: Virtues and Limitations](https://www.vldb.org/pvldb/vol7/p181-bailis.pdf)
</div>
</div>
</div>

{% include syllabus_entry %}
## Introduction to Application-Level Consistency
To introduce this lecture, I'll start with two conjectures in distributed computing: Eric Brewer's CAP Conjecture, and my own CALM Conjecture. Each of these was subsequently formalized and proven. I'll talk about the two conjectures, the two theorems, and the distance between conjecture and theorem in both cases. We will also discuss the relationship between all four.

* [Lecture Notes](https://docs.google.com/document/d/1eYKGgqRfhB-KQRD2mC_E8Hm-YVgMkZO2JFd5mfAxJ3E/edit?usp=sharing)

<div class="reading">
<div class="optional_reading" markdown="1">
* [CAP twelve years later: How the" rules" have changed](https://scholar.google.com/scholar?cluster=17642052422667212790&hl=en&as_sdt=0,5)
* [Keeping CALM: When Distributed Consistency is Easy](https://arxiv.org/abs/1901.01930)
</div>
</div>

{% include syllabus_entry %}
## Application-Level Consistency

In Kung & Papadimitriou, we looked in the (very) abstract at the idea that higher levels of concurrency could be allowed with more application information. This week we look at concrete examples of this idea including an influential design pattern paper from industry (Helland/Campbell) and papers from two of the leading academic efforts of the last decade: Berkeley's Bloom language and INRIA's CRDT efforts (which you may have read about in CS262A.)

Additional background reading is offered for each of the papers we're reading. 

* [Slides for class discussion](https://docs.google.com/presentation/d/18AcwyRI_RnLgdpfrV0XT4zomI-gtDem1XdveUiyEeMw/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [Building on Quicksand](https://arxiv.org/pdf/0909.1788)
* [Logic and Lattices for Distributed Systems](http://db.cs.berkeley.edu/papers/socc12-blooml.pdf)
* [Logoot-Undo: Distributed Collaborative Editing System on P2P Networks](http://www.academia.edu/download/39769048/Logoot-Undo_Distributed_Collaborative_Ed20151107-5753-e8mgn.pdf)
<div class="optional_reading" markdown="1">
 * [Dynamo: Amazon's Highly Available Key Value Store](https://scholar.google.com/scholar?cluster=5432858092023181552&hl=en&as_sdt=0,5)
 * [Consistency Analysis in Bloom: a CALM and Collected Approach](https://dsf.berkeley.edu/papers/cidr11-bloom.pdf)
 * [Conflict-Free Replicated Data Types](https://hal.inria.fr/inria-00609399/document)
</div>
</div>
</div>

{% include syllabus_entry %}
## Introduction to Learning and Database Systems

* [Notes: ML+DB, ML+QO, Neo](https://docs.google.com/document/d/1fu-ihMbefbQErcRPcds5Bi2TxF4CxLmamWhvqMN3Mig/edit?usp=sharing)
* [Slides on CARDLearner](https://drive.google.com/file/d/18DMsYodshkmSmJJFS50LfbZK0vIyIqfn/view?usp=sharing)
* [Slides on Naru](https://drive.google.com/file/d/19f3smK7tHueBciHa5I0FAQEXFG_ZHJQc/view?usp=sharing)


{% include syllabus_entry %}
## Learning-Based Query Optimization
Class-led discussion; Prof H will be away.

* [Slides for class discussion](https://docs.google.com/presentation/d/1gB6eN3B06EZ82kunpftCco6_dJMcaVUKdcit0-7yN88/edit?usp=sharing)

<div class="reading">
<div class="required_reading" markdown="1">
* [Deep Unsupervised Cardinality Estimation](http://www.vldb.org/pvldb/vol13/p279-yang.pdf)
* [Neo: A Learned Query Optimizer](http://www.vldb.org/pvldb/vol12/p1705-marcus.pdf)
* [Towards a Learning Optimizer for Shared Clouds](http://www.vldb.org/pvldb/vol12/p210-wu.pdf)
<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

{% include syllabus_entry %}
## Query Processing Revisited

* [Lecture Notes](https://docs.google.com/document/d/1clzcplQ_CwQttAlyDmudbyMzmGZywYE9jK9E-zNADwQ/edit?usp=sharing)

{% include syllabus_entry %}
## New Approaches to Join Processing

* [Slides for class discussion]()

<div class="reading">
<div class="required_reading" markdown="1">
* [Leapfrog Triejoin: A Worst-Case Optimal Join Algorithm](https://arxiv.org/abs/1210.0481)
* [Eddies: Continuously Adaptive Query Processing](https://dsf.berkeley.edu/cs286/papers/eddies-sigmod2000.pdf)
* [Lifting the Burden of History from Adaptive Query Processing](http://www.vldb.org/conf/2004/RS24P2.PDF)
<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

{% include syllabus_entry %}
## Introduction to Approximate Query Processing
As background, you might want to skim the light optional reading for this day.

* [Lecture Notes](https://docs.google.com/document/d/19IJFdcP_41G9eXDxrTlkyfN9WXzt0l0sUMHd0I0JnHc/edit?usp=sharing)

<div class="reading">
   <div class="optional_reading" markdown="1">
* [Data Sketching](https://dl.acm.org/ft_gateway.cfm?id=3104030&ftid=1877912&dwn=1)
* [Interactive Data Analysis: The CONTROL Project](https://scholar.google.com/scholar?cluster=12516415207233566357&hl=en&as_sdt=0,5)
</div>
</div>

{% include syllabus_entry %}
## Approximate Query Processing
* [Slides for class discussion](https://docs.google.com/presentation/d/11kTKq7AW4HHiqv0zva8RRYHbulS1xehbhK-9mB6ywME/edit)

<div class="reading">
<div class="required_reading" markdown="1">
* [Wander Join: Online Aggregation via Random Walks](https://dl.acm.org/doi/pdf/10.1145/2882903.2915235?casa_token=UkiEtIJPRx8AAAAA:rdaB3XDEJk8-1HJsta-t4mkEG4ZSLNFRsvZsarvgSBPsoK4W2h1TkqxysncsDBbbF-bAMsTSHUnUzg)
* [I've Seen Enough: Incrementally Improving Visualizations to Support Rapid Decision Making.](http://data-people.cs.illinois.edu/papers/incvisage-paper.pdf)
* [VerdictDB: Universalizing Approximate Query Processing](https://dl.acm.org/doi/pdf/10.1145/3183713.3196905?casa_token=HVn_ZtcZi9AAAAAA:yN6EyK9rzodimErAw40qTs3P9wW0BcnZDLDYRO3Dbqr2m2Bin8Hx3R2rpAYZCSrFjUSy-r7lCyQDHg)
<div class="optional_reading" markdown="1">
 * [Online Aggregation](http://control.cs.berkeley.edu/online/online.pdf)
 * [Partial Results for Online Query Processing](https://dsf.berkeley.edu/papers/sigmod02-partial.pdf)
 * [Approximate Query Engines: Commercial Challenges and Research Opportunities](https://dl.acm.org/doi/pdf/10.1145/3035918.3056098?casa_token=yO91tBSqKIgAAAAA:eVCEbaTV1bDMPUDl9sn_ABlQqJGi2IfKYBFrHvd63jewlapnbIhgCWbFfJxKZ7Rfu_cYWlGvDm3w5Q)
</div>
</div>
</div>

{% include syllabus_entry %}
## Introduction to Main-Memory Query Processing
**Lecture Cancelled** (Faculty Retreat!)

{% include syllabus_entry %}
Spring Break


{% include syllabus_entry %}
Spring Break

{% include syllabus_entry %}
## Main Memory Query Processing

* [Slides for class discussion](https://docs.google.com/presentation/d/1F5cnPePRN8OrlrVI6h2S7GPxUd2CApNjRy0B3BGkdM4/edit)

<div class="reading">
<div class="required_reading" markdown="1">
* [Efficiently Compiling Efficient Query Plans for Modern Hardware](https://www.vldb.org/pvldb/vol4/p539-neumann.pdf)
* [Morsel-Driven Parallelism: a NUMA-aware query evaluation framework for the many-core age](https://dl.acm.org/doi/pdf/10.1145/2588555.2610507?casa_token=4dDLr5__N10AAAAA:XvnxPOr99fPkZtDfjyOS-nNhiJthVD3Lp8LJdrUdMN2liNenoaXV68J9fmg-2ujpmMAnGb3BRV_uqg)
* [LeanStore](https://db.in.tum.de/~leis/papers/leanstore.pdf)
<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

{% include syllabus_entry %}
## Introduction to Main-Memory Concurrency Control

* [Lecture Notes](https://docs.google.com/document/d/1VN4rG_QMAv0-nebNwU2YR8I7kUKDI8q4DSwQe-F4T_0/edit?usp=sharing)

{% include syllabus_entry %}
## Main Memory Concurrency Control
* [Slides for class discussion](https://docs.google.com/presentation/d/1skxxLdPE_eY1KHC_wpHCY-uuX58Za0rEhszRugCzmzk/edit#slide=id.p1) and [here](https://docs.google.com/presentation/d/1hJloJuen6oHcDXXPlJNMszTn2MSF2w2jGD3oMWC_eRQ/edit) (oops!)

<div class="reading">
<div class="required_reading" markdown="1">
* [High-Performance Concurrency Control Mechanisms for Main-Memory Databases](https://vldb.org/pvldb/vol5/p298_per-akelarson_vldb2012.pdf)
* [Fast Serializable Multi-Version Concurrency Control for Main-Memory DB Systems](https://dl.acm.org/doi/pdf/10.1145/2723372.2749436?casa_token=4FJLKRhWfVkAAAAA:G4HHOtduR28eAVfWTAJrOpoPpwrWM4000Ns9cgWO8RlGvkVffPcMVepcHSCfnlkr7KrX92bzGt7I8Q)
* [Opportunities for Optimism in Contended Main-Memory Multicore Transactions](http://www.vldb.org/pvldb/vol13/p629-huang.pdf)
<div class="optional_reading" markdown="1">
* [Meerkat: Multicore-Scalable Replicated Transactions Following the Zero-Coordination Principle](https://dada.cs.washington.edu/research/tr/2019/11/UW-CSE-19-11-02.pdf)   
</div>
</div>
</div>

{% include syllabus_entry %}
## Introduction to Programming Support for DB-Backed Applications
Guest lecturer: Alvin Cheung, UC Berkeley

* [Lecture Notes](https://drive.google.com/open?id=1UTEw6exOTxxDrJxfKj0MLiPaFjEgx3sA)
* [Lecture video](https://drive.google.com/open?id=16QRUW8CqY9ugZWwGtWKbnFYkwap4uQnT) (Berkeley only)

{% include syllabus_entry %}
## Programming Support for Database-Backed Applications
* [Slides for class discussion](https://docs.google.com/presentation/d/1tKz8lDHmmpReziajIhyIlASvhid58Lq0xta2xSla_lA/edit)

<div class="reading">
<div class="required_reading" markdown="1">
* [Orleans: Distributed Virtual Actors for Programmability and Scalability](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/Orleans-MSR-TR-2014-41.pdf)
* [Optimizing Database-Backed Applications with Query Synthesis](http://people.csail.mit.edu/akcheung/papers/pldi13.pdf)
* [Feral concurrency control: An empirical investigation of modern application integrity](https://amplab.cs.berkeley.edu/wp-content/uploads/2015/06/feral-sigmod2015.pdf)
<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

{% include syllabus_entry %}
## Introduction to Cloud Databases
Guest lecturer: Alex Lloyd (Google)

* [Lecture Notes]()
{% include syllabus_entry %}
## Cloud Databases
* [Slides for class discussion](https://docs.google.com/presentation/d/1Qs7s2a01HGiQIHbY5qwfjIpnqHl7i2ZM9i4UjnzVthQ/edit)

<div class="reading">
<div class="required_reading" markdown="1">
* [Spanner: Google's Globally Distributed Database](https://dl.acm.org/doi/pdf/10.1145/2491245)
* [Amazon Aurora: Design considerations for high throughput cloud-native relational databases](https://dl.acm.org/doi/pdf/10.1145/3035918.3056101)
* [Amazon Aurora: On Avoiding Distributed Consensus for I/Os, Commits, and Membership Changes](https://dl.acm.org/doi/pdf/10.1145/3183713.3196937)
<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

{% include syllabus_entry %}
## Data Wrangling and Cleaning
* [Lecture Notes]()
{% include syllabus_entry %}
## Paper Discussion TBA
* [Slides for class discussion]()

<div class="reading">
<div class="required_reading" markdown="1">
* [Wrangler: Interactive visual specification of data transformation scripts](http://vis.stanford.edu/files/wrangler.pdf)
* [Raha: A configuration-free error detection system](https://www.bigdama.tu-berlin.de/fileadmin/fg326/portraits/mohammad/raha_paper.pdf)
* [Deep Learning For Entity Matching: A Design Space Exploration](http://pages.cs.wisc.edu/~anhai/papers1/deepmatcher-tr.pdf)
<div class="optional_reading" markdown="1">
* [Holoclean: Holistic data repairs with probabilistic inference](https://arxiv.org/pdf/1702.00820)
* [Blinkfill: Semi-supervised programming by example for syntactic string transformations](https://dl.acm.org/doi/pdf/10.14778/2977797.2977807)
* [Activeclean: Interactive data cleaning for statistical modeling](https://dl.acm.org/doi/pdf/10.14778/2994509.2994514)
</div>
</div>

{% include syllabus_entry %}
## Stream Query Processing

* [Lecture Notes]()
{% include syllabus_entry %}
## Paper Discussion TBA
* [Slides for class discussion]()

<div class="reading">
<div class="required_reading" markdown="1">
* TBA
* TBA
* TBA
<!-- <div class="optional_reading" markdown="1"> -->
<!-- </div> -->
</div>
</div>

</div>
</td>
</tr>
</tbody>
</table>

More tentative syllabus [here](https://docs.google.com/spreadsheets/d/1P1FoyTejwmcYAAmiNP9TkgEGltQkD2lCUYEIf1qbcNs/edit?usp=sharing).

## Projects

Detailed candidate project descriptions will be posted shortly.  However, students are encourage to find projects that relate to their ongoing research.


## Grading

Grades will be largely based on class participation and projects.  In addition, we will require weekly paper summaries submitted before class.
* **Projects:** _60%_
* **Weekly Summaries:** _20%_
* **Class Participation:** _20%_









<script type="text/javascript">


var current_date = new Date();
var rows = document.getElementsByTagName("th");
var finished =  false;
for (var i = 1; i < rows.length && !finished; i++) {
   var r = rows[i];
   if (r.id.startsWith("counter_")) {
      var fields = r.id.split("_")
      var week_div_id = "week_" + fields[2]
      var lecture_date = new Date(fields[1] + " 23:59:00")
      if (current_date <= lecture_date) {
         finished = true;
         r.style.background = "orange"
         r.style.color = "black"
         var week_td = document.getElementById(week_div_id)
         week_td.style.background = "#043361"
         week_td.style.color = "white"
         var anchor = document.createElement("div")
         anchor.setAttribute("id", "today")
         week_td.prepend(anchor)
      }
   }
}

$(".reading").each(function(ind, elem) {
   var optional_reading = $(elem).find(".optional_reading");
   if(optional_reading.length == 1) {
      optional_reading = optional_reading[0];
      optional_reading.setAttribute("id", "optional_reading_" + ind);
      var button = document.createElement("button");
      button.setAttribute("class", "btn btn-primary btn-sm");
      button.setAttribute("type", "button");
      button.setAttribute("data-toggle", "collapse");
      button.setAttribute("data-target", "#optional_reading_" + ind);
      button.setAttribute("aria-expanded", "false");
      button.setAttribute("aria-controls", "#optional_reading_" + ind);
      optional_reading.setAttribute("class", "optional_reading_no_heading collapse")
      button.innerHTML = "Additional Optional Reading";
      optional_reading.before(button)
   }
   
})


$(".details").each(function(ind, elem) {
      elem.setAttribute("id", "details_" + ind);
      var button = document.createElement("button");
      button.setAttribute("class", "btn btn-primary btn-sm");
      button.setAttribute("type", "button");
      button.setAttribute("data-toggle", "collapse");
      button.setAttribute("data-target", "#details_" + ind);
      button.setAttribute("aria-expanded", "false");
      button.setAttribute("aria-controls", "#details_" + ind);
      elem.setAttribute("class", "details_no_heading collapse")
      button.innerHTML = "Detailed Description";
      elem.before(button)
   })

</script>


