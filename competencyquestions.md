---
layout: default
title: Competency Questions
---

<article class="mb-5" id="competencyquestions">
<content>

<h1>Competency Questions</h1>

	<p class="message">Several designed competency questions are presented below, alongside their related SPARQL queries and outputs. These competency questions aim at demonstrating the usefulness of EducOnto for a wide range of operational tasks.</p>

        <h3>CQ1: How to retrieve recommended/required academic backgrounds for a specific curriculum?</h3>

<p>CQ1 aims at checking what academic backgrounds are recommended or even required for a specific curriculum. This is because there exist many structural restrictions in the educational system. For instance, a high school senior who is majoring in Literature will be denied access to most scientific curricula.</p>

<strong>SPARQL Query</strong> <br/>
<pre>
PREFIX ed: <http://erpi.fr/educonto/>
PREFIX major: <http://erpi.fr/edukg/major/>
PREFIX curriculum: <http://erpi.fr/edukg/curriculum/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

SELECT ?major 
WHERE {
    ?major rdf:type/rdfs:subClassOf* ed:HighSchoolMajor.
    curriculum:lg_cs ed:recommendsHighSchoolMajor ?major .
}
</pre>

<strong>Result</strong> <br/>

<table>
<thead>
  <tr>
    <th></th>
    <th>Major</th>
  </tr>
</thead>
<tbody>
  <tr>
  <td>1</td>
  <td>edukg:major/ts</td></tr>
  
  <tr>
  <td>2</td>
  <td>edukg:major/sti2d</td></tr>
</tbody>
</table>

        <h3>CQ2: What is the most popular higher education curriculum for students coming from a given high school major?</h3>

<p>CQ2 seeks to retrieve the most picked-up curricula by students sharing the same high school major as the active user. This consideration is of major importance as some high school majors allow access to a large number of higher education curricula. In such circumstances, retrieving all the accessible curricula given a high school major may result in a vast amount of choices and the student would still feel overwhelmed.</p>

<strong>SPARQL Query</strong> <br/>
<pre>
PREFIX ed: <http://erpi.fr/educonto/>
PREFIX major: <http://erpi.fr/edukg/major/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

SELECT ?curriculum (COUNT(?curriculum) AS ?count)
WHERE
{ ?student rdf:type ed:UndergraduateStudent .
  ?student ed:likedCurriculum ?curriculum .
  ?student ed:pickedGeneralMajor major:ts .
}
GROUP BY ?curriculum
ORDER BY DESC(?count)
LIMIT 5
</pre>

<strong>Result</strong> <br/>
<table>
<thead>
  <tr>
    <th></th>
    <th>Curriculum</th>
    <th>Count</th>
  </tr>
</thead>
<tbody>
<tr>
<td>1</td>
    <td>edukg:curriculum/lg_paces</td>
    <td>79</td>
</tr>
<tr>
<td>2</td>
    <td>edukg:curriculum/lg_staps</td>
    <td>73</td>
</tr>
<tr>
<td>3</td>
    <td>edukg:curriculum/lg_sv</td>
    <td>64</td>
</tr>
<tr>
<td>4</td>
    <td>edukg:curriculum/cpge_pcsi</td>
    <td>45</td>
</tr>
<tr>
<td>5</td>
    <td>edukg:curriculum/cpge_bcpst</td>
    <td>38</td>
</tr>

</tbody>
</table>

        <h3>CQ3: How to personalize curricula recommendations based on a student's profile?</h3>

<p>CQ3 evaluates the ability of our ontology to return curricula that match student’s personality and preferences. In the query presented below, keywords that the active student mentioned are considered as insightful preferences to focus on.</p>

<strong>SPARQL Query</strong> <br/>
<pre>
PREFIX ed: <http://erpi.fr/educonto/>
PREFIX student: <http://erpi.fr/edukg/stud/>

SELECT ?curriculum (COUNT(?keyword) AS ?commonKeywords)
WHERE {
    student:user3037 ed:isInterestedInKeyword ?keyword .
    ?curriculum ed:curriculumRelatesToKeyword ?keyword .
}
GROUP BY ?curriculum
ORDER BY DESC(?commonKeywords)
</pre>

<strong>Result</strong> <br/>
<table>
<thead>
  <tr>
  <th></th>
    <th>Curriculum</th>
    <th>Common Keywords</th>
  </tr>
</thead>
<tbody>
<tr>
<td>1</td>
    <td>edukg:curriculum/lg_miashs</td>
    <td>3</td>
</tr>
<tr>
<td>2</td>
    <td>edukg:curriculum/lg_tech</td>
    <td>3</td>
</tr>
<tr>
<td>3</td>
    <td>edukg:curriculum/but_sid</td>
    <td>2</td>
</tr>
<tr>
    <td>...</td>
    <td>...</td>
</tr>
<tr>
<td>84</td>
    <td>edukg:curriculum/speech-language</td>
    <td>1</td>
</tr>

</tbody>
</table>
        <h3>CQ4: Based on some initial curriculum a high school senior is interested in, what are the alternative curricula he might also consider?</h3>

<p>CQ4 aims at leveraging relationships between the total set of curricula and the ones the active student is explicitly interested in. CQ4 is a broad question that can be answered in many ways. Consequently, it is further subdivided below for improved clarity.</p>

            <h4>CQ4.1: What are the alternative curricula regarding the curriculum's class?</h4>

<p>CQ4.1 regards the curriculum's type as the main criterion for retrieving similar curricula.</p>

<strong>SPARQL Query</strong> <br/>
<pre>
PREFIX ed: <http://erpi.fr/educonto/>
PREFIX student: <http://erpi.fr/edukg/stud/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

SELECT ?alternative
WHERE {
    student:user351 ed:mentionedCurriculum ?curriculum .
    ?curriculum rdf:type ?type .
    ?alternative rdf:type ?type .
    FILTER(?curriculum != ?alternative) .
}
</pre>

<strong>Result</strong> <br/>
<table>
<thead>
  <tr>
  <th></th>
    <th>Alternative</th>
  </tr>
</thead>
<tbody>

  <tr>
  <td>1</td>
  <td>edukg:curriculum/but_rt</td></tr>
  <tr>
  <td>2</td>
  <td>edukg:curriculum/but_mmi</td></tr>
</tbody>
</table>

            <h4>CQ4.2: What are the curricula sharing the same keywords?</h4>

<p>CQ4.2 regards the shared keywords as the main criterion for retrieving similar curricula.</p>

<strong>SPARQL Query</strong> <br/>
<pre>
PREFIX ed: <http://erpi.fr/educonto/>
PREFIX student: <http://erpi.fr/edukg/stud/>

SELECT ?alternative (COUNT(?keyword) AS ?commonKeywords)
WHERE {
    student:user351 ed:mentionedCurriculum ?curriculum .
    ?curriculum ed:curriculumRelatesToKeyword ?keyword .
    ?alternative ed:curriculumRelatesToKeyword ?keyword .
    FILTER(?curriculum != ?alternative) .
}
GROUP BY ?alternative
ORDER BY DESC(?commonKeywords)
</pre>

<strong>Result</strong> <br/>
<table>
<thead>
  <tr>
  <th></th>
    <th>Alternative</th>
    <th>Common Keywords</th>
  </tr>
</thead>
<tbody>
<tr>
<td>1</td>
    <td>edukg:curriculum/school_engineering_cs</td>
    <td>7</td>
</tr>
<tr>
<td>2</td>
    <td>edukg:curriculum/lg_cs</td>
    <td>6</td>
</tr>
<tr>
<td>3</td>
    <td>edukg:curriculum/but_rt</td>
    <td>5</td>
</tr>
<tr>
    <td>...</td>
    <td>...</td>
</tr>
<tr>
<td>35</td>
    <td>edukg:curriculum/lg_si</td>
    <td>1</td>
</tr>

</tbody>
</table>

            <h4>CQ4.3: What are the curricula related to the same field of study?</h4>

<p>CQ4.3 regards the field of study as the main criterion for retrieving similar curricula.</p>

<strong>SPARQL Query</strong> <br/>
<pre>
PREFIX ed: <http://erpi.fr/educonto/>
PREFIX student: <http://erpi.fr/edukg/stud/>

SELECT ?alternative
WHERE {
    student:user351 ed:mentionedCurriculum ?curriculum .
    ?curriculum ed:belongsToFieldOfStudy ?field .
    ?alternative ed:belongsToFieldOfStudy ?field .
    FILTER(?curriculum != ?alternative) .
}
GROUP BY ?alternative
</pre>

<strong>Result</strong> <br/>
<table>
<thead>
  <tr>
    <th></th>
    <th>Alternative</th>
  </tr>
</thead>
<tbody>
<tr>
    <td>1</td>
    <td>edukg:curriculum/lp_stats</td>
</tr>
<tr>
    <td>2</td>
    <td>edukg:curriculum/school_engineering_telecom</td>
</tr>
<tr>
    <td>3</td>
    <td>edukg:curriculum/lg_cs</td>
</tr>
<tr>
    <td>...</td>
    <td>...</td>
</tr>
<tr>
    <td>21</td>
    <td>edukg:curriculum/school_engineering_mathematics</td>
</tr>

</tbody>
</table>

        <h3>CQ5: How to mine the most influential factors leading to a particular curricula?</h3>

<p>CQ5 is motivated by a higher-level viewpoint. It asks what are the recurrent features of students following a given curriculum.</p>

<strong>SPARQL Query</strong> <br/>
<pre>
PREFIX ed: <http://erpi.fr/educonto/>
PREFIX curriculum: <http://erpi.fr/edukg/curriculum/>

SELECT ?keywordOrSubject ?preferredKeywordOrSubject
WHERE
{ 
	{
        SELECT (?subject AS ?keywordOrSubject) (COUNT(?subject) AS ?preferredKeywordOrSubject) WHERE 
        {
   			?student ed:likedCurriculum curriculum:cpge_mpsi .
    		?student ed:hasFavoriteSchoolSubject ?subject .
        }
        GROUP BY ?subject
    }
UNION
	{
        SELECT (?keyword AS ?keywordOrSubject) (COUNT(?keyword) AS ?preferredKeywordOrSubject) WHERE 
        {
    		?student ed:likedCurriculum curriculum:cpge_mpsi .
    		?student ed:isInterestedInKeyword ?keyword .
		}
        GROUP BY ?keyword
	}
}
GROUP BY ?keywordOrSubject ?preferredKeywordOrSubject
ORDER BY DESC(?preferredKeywordOrSubject)
LIMIT 15
</pre>

<strong>Result</strong> <br/>
<table>
<thead>
  <tr>
  <th></th>
    <th>Keyword or Subject</th>
    <th>Preferred Keyword or Subject</th>
  </tr>
</thead>
<tbody>
<tr>
<td>1</td>
    <td>edukg:mathematics</td>
    <td>43</td>
</tr>
<tr>
<td>2</td>
    <td>edukg:physics</td>
    <td>34</td>
</tr>
<tr>
<td>3</td>
    <td>edukg:history</td>
    <td>10</td>
</tr>
<tr>
    <td>...</td>
    <td>...</td>
</tr>
<tr>
<td>15</td>
    <td>edukg:chemistry</td>
    <td>2</td>
</tr>

</tbody>
</table>

  </content>
