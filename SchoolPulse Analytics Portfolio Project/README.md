# SchoolPulse Analytics

SchoolPulse Analytics is a business analytics portfolio project focused on helping a school identify students who may need support **before final exams**, rather than waiting until the end of the term to discover performance problems.

I built the project as an end-to-end analytics case study using **Visual Paradigm, MySQL, Python, DynamoDB, Neo4j, and Power BI**. The aim was not only to create a dashboard, but to show how different analytical tools can work together to answer practical school-management questions.

> **Important:** One academic term was used to demonstrate the project, but the logic is designed to work throughout the school year. The same process can be repeated for each term so that school management can continuously monitor student performance before final exams.

![School Overview](Screenshots/01%20-%20School%20Overview.png)

## Project Objective

Schools collect a large amount of information about students, including attendance, assessments, subjects, classes, and teacher activity. The challenge is turning those records into something useful enough for early intervention.

SchoolPulse Analytics was built around a simple business question:

**Which students are beginning to struggle before final exams, what areas are causing the problem, and where should the school focus its attention?**

The project therefore focuses on:

- identifying students who may need academic support;
- comparing student performance with class and subject benchmarks;
- showing classes with the highest support needs;
- identifying weaker subjects before final exams;
- combining score and attendance information to provide a clearer view of student performance;
- giving users the ability to drill from school-level information into class, subject, and student-level detail.

## Tools Used

### Visual Paradigm
I used Visual Paradigm to design the relational data model and define how the main school entities connect.

### MySQL
MySQL stores the core structured school data, including students, classes, subjects, assessments, scores, attendance, teachers, enrolment, and risk-related records.

### Python
Python was used for data validation, analysis, cumulative performance calculations, risk classification, and the preparation of reporting outputs.

### DynamoDB
DynamoDB was used as an event store for student-related activities such as risk events, interventions, notifications, and other analytical events that do not need to sit inside the main relational model.

### Neo4j
Neo4j was used to explore relationships between students, classes, subjects, teachers, guardians, risks, and interventions in a graph structure.

### Power BI
Power BI brings the analytical outputs together into an interactive report for school-level, class-level, subject-level, and student-level analysis.

## Business Logic

The dashboard is designed around the **pre-exam position**.

Performance information recorded before final exams is combined to show the student's current standing. Final exam records remain part of the wider school data, but they are not used when calculating the pre-exam support position.

### Student support classification

A student can be classified as needing support based on a combination of:

- academic performance;
- attendance;
- number of failed subjects.

The project uses three broad levels:

- **High risk:** the student needs more immediate attention;
- **Medium risk:** the student should be monitored and supported;
- **Low risk:** the student is currently performing within the expected range.

### Subject performance gap

For subject-level analysis, the project compares a student's performance with the average for the same subject in the student's class.

**Performance Gap = Student Subject Average - Class Average for the Same Subject**

A negative value means the student is performing below the class benchmark for that subject.

## Power BI Report

The final report contains four main pages:

1. **School Overview**  
   Gives management a quick view of total students, pre-exam average performance, attendance, students needing support, risk distribution, weaker classes, and classes requiring attention.

2. **Student Support**  
   Focuses on students who still require support before final exams and allows the user to identify priority cases.

3. **Class Performance**  
   Compares class performance, attendance, support needs, and students failing subjects.

4. **Subject Performance**  
   Highlights weaker subjects and subject-level risk before final exams.

The report also includes drill-through pages for deeper analysis:

- Class Detail
- Subject Detail
- Student Profile
- Student-Subject Detail
- Class Benchmark Analysis
- Subject Risk Map

## Dashboard Screenshots

### Student Support
![Student Support](Screenshots/02%20-%20Student%20Support.png)

### Class Performance
![Class Performance](Screenshots/03%20-%20Class%20Performance.png)

### Subject Performance
![Subject Performance](Screenshots/04%20-%20Subject%20Performance.png)

### Student Profile
![Student Profile](Screenshots/07%20-%20Student%20Profile.png)

## What the Project Demonstrates

This project gave me the opportunity to work through a complete business analytics process rather than focusing on one tool in isolation.

It demonstrates experience with:

- translating a business problem into analytical requirements;
- designing a relational data model;
- writing and working with SQL;
- validating and analysing data in Python;
- creating business rules for student risk and intervention;
- working with NoSQL and graph databases;
- building Power BI measures and interactive dashboards;
- using drill-through pages to move from high-level KPIs to detailed student information;
- presenting analytical findings in a way that can support decision-making.

## Project Files

```text
SchoolPulse-Analytics-Business-Analytics-Portfolio/
|
|-- README.md
|-- Screenshots/
|-- Visual Paradigm/
|-- SQL/
|-- Python/
|-- DynamoDB/
|-- Neo4j/
`-- Power BI/
```

Each folder contains the relevant work completed using that tool.

## Current Portfolio Dataset

For the demonstration dataset used in this project, the final dashboard includes:

- **216 students**
- **18 classes**
- **34 active subjects in the final analysis**
- **114 students identified as needing pre-exam support**
- **60 high-priority students**
- **54 medium-priority students**
- **48 students failing at least one subject**
- **66.86 pre-exam average score**
- **81.40 pre-exam average attendance**

These values are part of the sample term used to demonstrate how the SchoolPulse analytical process works. They are not intended to limit the project to one term. The same process can be repeated across the school year before each set of final exams.

## Final Note

SchoolPulse Analytics is a portfolio project built to demonstrate how I approach a real business problem using data.

The main goal was to create something that goes beyond reporting past results. The project is designed to help school management understand what is happening **before final exams**, identify where support may be needed, and move from a school-wide view down to the individual student and subject level.

As a Business Analytics student, this project represents the kind of work I am interested in developing further: using data, analytical tools, and clear visual reporting to help organisations make better decisions.
