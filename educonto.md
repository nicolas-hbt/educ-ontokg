---
layout: default
title: EducOnto
---

[Motivations](#motivations) | [Overview](#overview) | [Description](#description) | [Download](#download) 

<article class="mb-5" id="educonto">

<content>
  <h1 id="educontopage">EducOnto: An <span style="color: #6a9fb5">Onto</span>logy for <span style="color: #6a9fb5">Educ</span>ation</h1>
  
  <p class="message">EducOnto is made available as an open-source resource under the <a href="https://www.apache.org/licenses/LICENSE-2.0">Apache 2.0 license</a></p>
  
<h2 id="motivations">Motivations</h2>
  
    <p>Owing to the intricacies of the educational domain, several ontologies have been proposed to model the richness of the field. Apart from its inner complexity, education is also a high stakes domain. In particular, educational guidance can be stressfull for high school seniors struggling to make a choice. The transition from the last year of high school and the first year of university is a pivotal moment for every student. Unfortunately, we did not find any available ontology modelling this specific concern. We then choose to develop our own ontology - EducOnto - and make it publicly available to foster research.</p>
  
<h2 id="overview">Overview</h2>
  
    <p>Below, a conceptual overview of EducOnto is depicted. It provides a first glimpse of the ontology as a whole. For clarity, we only includes the main classes and shorten the relationships' labels. The separation between students' profiles, their high school educational paths and the domain of higher education is made visible. </p>
  
<img src ="../images/educonto.png" style="width:90%; height:90%" class="center">  
  
<h2 id="description">Description</h2>
  
In this subsection, we give a deeper insight into EducOnto. In particular, we give the reader a better understanding of how the different classes and properties have been designed, what they stand for and what their interactions are. Below are the main classes of EducOnto and what they stand for:
<!-- Bad rendering of < and > signs on the website; this is a backup version
      <table>
<thead>
  <tr>
    <th>Class</th>
    <th>Description</th>
    <th>Example of Instance</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>educonto:AcademicSkill</td>
    <td>Skill that a student possesses</td>
    <td><i>http://purl.org/edukg/good_memory</i></td>
  </tr>
  <tr>
    <td>educonto:Curriculum</td>
    <td>University curriculum</td>
    <td><i>http://purl.org/edukg/curriculum/lg_psycho</i></td>
  </tr>
  <tr>
    <td>educonto:FieldOfStudy</td>
    <td>Field of Study</td>
    <td><i>http://purl.org/edukg/engineering</i></td>
  </tr>
  <tr>
    <td>educonto:HighSchoolMajor</td>
    <td>Chosen major in high school</td>
    <td><i>http://purl.org/edukg/major/ts</i></td>
  </tr>
    <tr>
    <td>educonto:HighSchoolSpecialty</td>
    <td>Chosen specialty in high school</td>
    <td><i>http://purl.org/edukg/spe/arts</i></td>
  </tr>
      <tr>
    <td>educonto:Keyword</td>
    <td>Can be linked to student and seen as a center of interest. Can be linked to university curricula and high school majors and be seen as a descriptive feature</td>
    <td><i>http://purl.org/edukg/healthcare</i></td>
  </tr>
      <tr>
    <td>educonto:Person</td>
    <td>High school senior or Undergraduate student</td>
    <td><i>http://purl.org/edukg/stud/user999</i></td>
  </tr>
        <tr>
    <td>educonto:PersonalityTrait</td>
    <td>Personality trait a student possesses</td>
    <td><i>http://purl.org/edukg/investigative</i></td>
  </tr>
        <tr>
    <td>educonto:SchoolSubject</td>
    <td>School subject taught at school</td>
    <td><i>http://purl.org/edukg/chemistry</i></td>
  </tr>
  
</tbody>
</table>
-->  


  <table>
<thead>
  <tr>
    <th>Class</th>
    <th>Description</th>
    <th>Example of Instance</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>educonto:AcademicSkill</td>
    <td>Skill that a student possesses</td>
    <td><i>&lthttp://purl.org/edukg/good_memory&gt</i></td>
  </tr>
  <tr>
    <td>educonto:Curriculum</td>
    <td>University curriculum</td>
    <td><i>&lthttp://purl.org/edukg/curriculum/lg_psycho&gt</i></td>
  </tr>
  <tr>
    <td>educonto:FieldOfStudy</td>
    <td>Field of Study</td>
    <td><i>&lthttp://purl.org/edukg/engineering&gt</i></td>
  </tr>
  <tr>
    <td>educonto:HighSchoolMajor</td>
    <td>Chosen major in high school</td>
    <td><i>&lthttp://purl.org/edukg/major/ts&gt</i></td>
  </tr>
    <tr>
    <td>educonto:HighSchoolSpecialty</td>
    <td>Chosen specialty in high school</td>
    <td><i>&lthttp://purl.org/edukg/spe/arts&gt</i></td>
  </tr>
      <tr>
    <td>educonto:Keyword</td>
    <td>Can be linked to student and seen as a center of interest. Can be linked to university curricula and high school majors and be seen as a descriptive feature</td>
    <td><i>&lthttp://purl.org/edukg/healthcare&gt</i></td>
  </tr>
      <tr>
    <td>educonto:Person</td>
    <td>High school senior or Undergraduate student</td>
    <td><i>&lthttp://purl.org/edukg/stud/user999&gt</i></td>
  </tr>
        <tr>
    <td>educonto:PersonalityTrait</td>
    <td>Personality trait a student possesses</td>
    <td><i>&lthttp://purl.org/edukg/investigative&gt</i></td>
  </tr>
        <tr>
    <td>educonto:SchoolSubject</td>
    <td>School subject taught at school</td>
    <td><i>&lthttp://purl.org/edukg/chemistry&gt</i></td>
  </tr>
  
</tbody>
</table>
-->
 

Below are some of the 30 object properties of EducOnto. For clarity, we do not include the object properties whose meaning and domain-range pair are obvious.

<table>
<thead>
  <tr>
    <th>Object Property</th>
    <th>Domain</th>
    <th>Range</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>educonto:belongsToFieldOfStudy</td>
    <td>educonto:Curriculum</td>
    <td>educonto:FieldOfStudy</td>
  </tr>
   <tr>
    <td>educonto:hasFavoriteSchoolSubject</td>
    <td>educonto:Person</td>
    <td>educonto:SchoolSubject</td>
  </tr>
    <tr>
    <td>educonto:hasMainTopic</td>
    <td>educonto:HighSchoolMajor</td>
    <td>educonto:SchoolSubject</td>
  </tr>
  <tr>
    <td>educonto:hasSkill</td>
    <td>educonto:Person</td>
    <td>educonto:AcademicSkill</td>
  </tr>
  <tr>
    <td>educonto:isInterestedInKeyword</td>
    <td>educonto:Person</td>
    <td>educonto:Keyword</td>
  </tr>
    <tr>
    <td>...</td>
    <td>...</td>
    <td>...</td>
  </tr>
   <tr>
    <td>educonto:mentionedCurriculum</td>
    <td>educonto:Person</td>
    <td>educonto:Curriculum</td>
  </tr>
    <tr>
    <td>educonto:pickedGeneralMajor</td>
    <td>educonto:Person</td>
    <td>educonto:GeneralMajor</td>
  </tr>
      <tr>
    <td>educonto:recommendsHighSchoolMajor</td>
    <td>educonto:Curriculum</td>
    <td>educonto:HighSchoolMajor</td>
  </tr>
      <tr>
    <td>educonto:recommendsHighSchoolSpecialty</td>
    <td>educonto:Curriculum</td>
    <td>educonto:HighSchoolSpecialty</td>
  </tr>
      <tr>
    <td>educonto:requiresHighSchoolMajor</td>
    <td>educonto:Curriculum</td>
    <td>educonto:HighSchoolMajor</td>
  </tr>
      <tr>
    <td>educonto:requiresHighSchoolSpecialty</td>
    <td>educonto:Curriculum</td>
    <td>educonto:HighSchoolSpecialty</td>
  </tr>
</tbody>
</table>

 In order to comply with the <a href="https://www.nature.com/articles/sdata201618">FAIR principles for scientific data management</a>, standard Semantic Web vocabularies are integrated into EducOnto metadata. This is essential for properly describing the ontology, thus avoiding any possible misinterpretation. Below are the vocabularies we used to describe EducOnto metadata with their respective namespaces:
  
<h4> Ontology Namespaces </h4>
  <table style="width:100%">
    <tr>
    <th>Prefix</th>
    <th>Hyperlink</th> 
  </tr>
  <tr>
    <td>dc</td>
    <td> <a href="http://purl.org/dc/terms/">Dublin Core Term</a> </td> 
  </tr>
  <tr>
    <td>ed</td>
    <td> <a href="">EducOnto</a> </td> 
  </tr>
  <tr>
    <td>owl</td>
    <td><a href="http://www.w3.org/2002/07/owl#">Web Ontology Language </a> </td> 
  </tr>
  <tr>
    <td>rdf</td>
    <td><a href="http://www.w3.org/1999/02/22-rdf-syntax-ns">Resource Description Framework</a></td> 
  </tr>
  <tr>
    <td>rdfs</td>
    <td><a href="http://www.w3.org/2000/01/rdf-schema">RDF Schema</a></td> 
  </tr>
  <tr>
    <td>xml</td>
    <td><a href="http://www.w3.org/XML/1998/namespace#">Extensible Markup Language</a></td> 
  </tr>
   <tr>
    <td>xsd</td>
    <td><a href="http://www.w3.org/2001/XMLSchema#">XML Schema Definition</a></td> 
  </tr>
</table>
  
    
<h2 id="download">Download</h2>
    
<p><strong>EducOnto</strong> can be downloaded in .owl format at the following link: <a href="../educonto/educonto.owl" download>educonto.owl</a></p>
  
<!-- 
```graphql

owl:Thing 
  ├─ AcademicSkill
  ├─ Curriculum
  ├─ FieldOfStudy
  ├─ HighSchoolMajor
  ├─ HighSchoolSpecialty
  ├─ Keyword
  ├─ Person
  ├─ PersonalityTrait
  ├─ SchoolSubject
```

Below, we present the hierarchy for the Curriculum class. We limit ourselves to a depth of five for better readability:

```graphql

Curriculum 
  ├─ LongStudies
  │  ├─ Bachelor
  │  │  ├─ DualBachelor
  │  │  ├─ GeneralBachelor
  │  │  │ ├─ ArtAudiovisualDesign
  │  │  │ ├─ BusinessEconomyManagement
  │  │  │ ├─ Humanities
  │  │  │ ├─ LawPolitics
  │  │  │ ├─ Sciences
  │  │  ├─ TechnologicalBachelor
  │  │  │ ├─ Industry
  │  │  │ ├─ Tertiary
  │  ├─ PreparatoryClass
  │  │  ├─ Cpge
  │  │  │ ├─ BusinessEconomyManagement
  │  │  │ ├─ Engineering
  │  │  │ ├─ Humanities
  │  │  │ ├─ Technology
  │  │  ├─ IntegratedPreparatoryClass
  │  ├─ School
  │  │  ├─ ArtAudiovisualDesign
  │  │  ├─ BusinessEconomyManagement
  │  │  ├─ EngineeringScience
  │  │  ├─ InformationCommunication
  │  │  ├─ Paramedical
  ├─ ShortStudies
  │  ├─ AdvancedTechnicianCertificate
  │  │  ├─ AgricultureAgronomyEnvironment
  │  │  ├─ ArtAudiovisualDesign
  │  │  ├─ AutomationConstructionMechanic
  │  │  ├─ BiologyChemistry
  │  │  ├─ BusinessEconomyManagement
  │  │  ├─ CateringHospitalityTourism
  │  │  ├─ ComputerScience
  │  │  ├─ Engineering
  │  │  ├─ Paramedical
  │  ├─ VocationalBachelor
  │  │  ├─ AgricultureAgronomyEnvironment
  │  │  ├─ ArtAudiovisualDesign
  │  │  ├─ AutomationConstructionMechanic
  │  │  ├─ BiologyChemistry
  │  │  ├─ BusinessEconomyManagement
  │  │  ├─ CateringHospitalityTourism
  │  │  ├─ ComputerScience
  │  │  ├─ Engineering
  │  │  ├─ Humanities
  │  │  ├─ LawPolitics
  └───  ├─ Paramedical
```
-->
 </content>
