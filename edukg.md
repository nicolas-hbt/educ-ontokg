---
layout: default
title: EduKG
---

[Introduction](#introduction) | [Use Cases](#usecases) | [Statistics](#statistics) | [Download](#download) 

<article class="mb-5" id="edukg">
<content>
  <h1 id="edukgpage">EduKG: An <span style="color: #6a9fb5">Edu</span>cational <span style="color: #6a9fb5">K</span>nowledge <span style="color: #6a9fb5">G</span>raph</h1>
    
<h2 id="introduction">Introduction</h2>
<p>Recently, the use of Knowledge Graphs (KGs) has met with great success for a wide range of use cases. In particular, KGs are increasingly used to improve the explainability of machine learning models. Unfortunately, there is a lack of suitable educational KGs. Therefore, we intend to contribute to the development and provision of a new educational KG, subsequently referred to as EduKG. EduKG is a knowledge graph instantiated with students' data and a broad spectrum of curricula. EduKG is built on the basis of <a href="{{site.baseurl}}educonto">EducOnto</a>, from which it inherits the rich semantics and structural constraints.</p>

  <!--
<h2 id="description">Description</h2>

  
<h4 id="modelling">Modelling choices</h4>

<p>Education is a highly complex domain. To model its own intricacies, we designed <a href="{{site.baseurl}}educonto">EducOnto</a> that gives a conceptual overview of the field of application. EduKG can be seen as an instantiation of EducOnto. Consequently, to fully understand the data some clarifications must be made:
    
<ul>
  <li>High School Major vs. High School Specialty: one may wonder why some students are linked to high school specialties and others do not. Recall that data were collected on in the French educational system. It turns out that the French system underwent a reform in 2018: before this date, <strong>general</strong> high school students had to choose one of the three proposed high school majors. After the 2018 reform, high school seniors now have to pick <strong>two</strong> specialties instead. In order to enable comparisons between these two different students' cohorts, the two chosen high school specialties constitues a pair, which is ultimately mapped to a newly defined high school major. Consequently, it is assumed that every student picked a <strong>general</strong> high school major. Please note that the 2018 reform had no effect on the technological high school diploma. The aforementioned remark does not hold for high school <strong>technological</strong> majors.</li>
  <li>...</li>
  <li>...</li>
</ul>
 !-->
    
<h2 id="usecases">Use Cases</h2>
<p>EduKG was built with a very clear use case in mind: making (explainable) university curriculum recommendations. Considering that EducOnto underpins EduKG by providing it with a rich semantics, EduKG is particularly well suited for conducting research at the crossroads of Explainable Artificial Intelligence (XAI) and recommender systems (RSs). However, EduKG contains a wide spectrum of information and remains generic enough to be used in a wide range of downstream tasks.</p>
    
<h2 id="statistics">Dataset Statistics</h2>

<article class="mb-5" id="statistics">
<p>The first table just below gives a sense of EduKG dimensions:</p>

    
<table>
    <tr>
        <td>#Fields Of Study</td>
        <td>#Keywords</td>
        <td>#School Subjects</td>
        <td>#Majors</td>
        <td>#Specialties</td>
    </tr>
    <tr>
        <td>12</td>
        <td>321</td>
        <td>15</td>
        <td>92</td>
        <td>13</td>
    </tr>
    </table>
<p>For those who are more specifically interested in using EduKG for the purpose of making curriculum recommendations, the following table should be looked at more closely:</p>

    
  <table>
    <tr>
        <td>#Users (Students)</td>
        <td>#Items (Curricula)</td>
        <td>#Interactions</td>
        <td>Sparsity</td>
    </tr>
    <tr>
        <td>3,583</td>
        <td>286</td>
        <td>7,021</td>
        <td>99.31 %</td>
    </tr>
    </table> 
    <table>
 <p>Traditionally, a KG is defined by the following statistics: the number of unique entities and relations in the graph, as well as the total number of KG triplets. The following table provides these details:</p>

  <table>
    <tr>
        <td>#Entities</td>
        <td>#Relations</td>
        <td>#KG Triplets</td>
    </tr>
    <tr>
        <td>5,452</td>
        <td>27</td>
        <td>36,301</td>
    </tr>
</table>

<h2 id="download">Download</h2>
    <p><strong>EduKG</strong> can be downloaded in .ttl format at the following link: <a href="../edukg/edukg.ttl" download>edukg.ttl</a></p>
    
</content>
