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


* [Lecture notes]()

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

* [Lecture notes]()

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
I will be out at Microsoft on a RISE faculty expedition; speaker TBD.

{% include syllabus_entry %}
## Weak Isolation
Three papers. One is co-authored by Atul Adya and occasional database research contributor and Turing winner [Barbara Liskov](https://en.wikipedia.org/wiki/Barbara_Liskov), one is co-authored by incoming Berkeley faculty [Natacha Crooks](https://nacrooks.github.io/), and yet another appearance from Pat and Betty O'Neil.

Optional reading from then-Berkeley PhD student [Peter Bailis](http://www.bailis.org/), which identifies and pushes the boundary of what's possible with coordination-free isolation levels.

* [Lecture notes]()

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


