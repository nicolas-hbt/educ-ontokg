---
layout: default
title: EducOnto and EduKG
description: An Ontology and a Knowledge Graph for Higher Education
---

[Abstract](#abstract) | [FAIR Principles](#fair-principles) | [Directions](#directions)

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fnicolas-hbt.github.io%2Feduc-ontokg%2Findex&count_bg=%233DA7C8&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=visits&edge_flat=false)](https://hits.seeyoufarm.com)

<h1 class="page-title" id="header">EducOnto and EduKG: An Ontology and a Knowledge Graph for Higher Education</h1>

<h3 style="color:dimgrey;">Nicolas Hubert<sup>12</sup>, Armelle Brun<sup>2</sup>, Davy Monticolo<sup>1</sup></h3>
<h3><a href="https://erpi.univ-lorraine.fr/"><sup>1</sup>Université de Lorraine, ERPI, France</a> | <a href="https://www.loria.fr/en/"><sup>2</sup>Université de Lorraine, CNRS, Loria, France</a></h3>

<p class="message">EducOnto and EduKG are respectively an ontology and a knowledge graph rooted in the field of higher education. EducOnto aims at modelling students' profiles, curricula and other relevant concepts. EduKG is an instantiation of EducOnto with students' and curricula's information.</p>

<!-- <table>
  <tbody>
    <tr>
      <td><a href="#abstract">Abstract</a></td>
    </tr>
  </tbody>
</table> -->

<hr>
<article class="mb-5" id="abstract">
<content>
<h2>Abstract</h2>
  <p>Education is a complex domain where students must make their curricula choices carefully. To model the intricacies of the educational domain,
ontologies have successfully been leveraged in the past. However, no available ontology or dataset directly addresses the critical transition from high school to university from a decision-making perspective. Therefore, the contribution of our on-going work is twofold. Firstly, we introduce EducOnto -- an ontology that aims at modeling university curricula and students’ profiles. Secondly, we introduce EduKG -- a knowledge graph inheriting the semantics of EducOnto and instantiated with data about French students and curricula.</p>
</content>
 
<hr/>

<article class="mb-5" id="citation">
<content>
<h2>Citing</h2>
  <p>When citing, please use the following reference:

Nicolas Hubert, Armelle Brun, Davy Monticolo. New Ontology and Knowledge Graph for University Curriculum Recommendation. ISWC 2022 - The 21st International Semantic Web Conference, Oct 2022, Hangzhou / Virtual, China.</p>

```
@inproceedings{hubertISWC2022,
  TITLE = {{New Ontology and Knowledge Graph for University Curriculum Recommendation}},
  AUTHOR = {Hubert, Nicolas and Brun, Armelle and Monticolo, Davy},
  URL = {https://hal.archives-ouvertes.fr/hal-03768154},
  BOOKTITLE = {{ISWC 2022 - The 21st International Semantic Web Conference}},
  ADDRESS = {Hangzhou / Virtual, China},
  YEAR = {2022},
  MONTH = Oct,
  KEYWORDS = {Knowledge Graph ; Education ; Ontology ; Recommender System},
  PDF = {https://hal.archives-ouvertes.fr/hal-03768154/file/ISWC_Hubert.pdf},
  HAL_ID = {hal-03768154},
  HAL_VERSION = {v1},
}
```
</content>
 
<hr/>

<article class="mb-5" id="fair-principles">
<content>
<h2>FAIR Principles</h2>
  <p>Ontology development goes hand in hand with Knowledge Graph building. The former represents the content of the latter with a rich semantics and undoubtedly help data linking and integration across several Knowledge Graphs. Nonetheless, ontologies can be difficult to reuse, understand or even simply access. To address this issue, some best practices and principles have been proposed. The <a href="https://www.nature.com/articles/sdata201618">Findable, Accessible, Interoperable and Reusable (FAIR) principles</a> are an integral part of this endeavor to make data, ontologies and vocabularies more transparent and documented. Our work fully support this initiative. As such, we make sure to comply with the FAIR principles as follows:</p>
  <ul>
    <li><strong><span style="color: #6a9fb5">Findability</span></strong>: Both EducOnto and EduKG are made publicly available at persistent URIs - respectively <a href="https://purl.org/educonto">https://purl.org/educonto</a> and <a href="https://purl.org/edukg">https://purl.org/edukg</a> - to ensure their long-term persistence on the Web. EducOnto is more specifically described with rich metadata;</li>
    <li><strong><span style="color: #6a9fb5">Accessibility</span></strong>: multiple representations of EducOnto and EduKG are provided. They are both human-readable (HTML) and machine-readable (RDF and XML);</li>
    <li><strong><span style="color: #6a9fb5">Interoperability</span></strong>: EducOnto's metadata is described in a formal and shared language (OWL) for knowledge representation. EducOnto's metadata also rely on existing and common vocabularies for describing ontologies, thus allowing references to other metadata;</li>
    <li><strong><span style="color: #6a9fb5">Reusability</span></strong>: Both EducOnto and EduKG are highly reusable. EducOnto can be seen as the foundations upon which EduKG is subsequently instanciated. This is why EducOnto comes with a rich documentation, an important part of which is  provided within the ontology itself through ontology metadata and human-readable annotations. The conceptualization diagram is available on the <a href="https://nicolas-hbt.github.io/educ-ontokg/educonto/#overview">project's website</a>, alongside natural language descriptions of the main classes and object properties. An external and even more thorough description of EducOnto is made available (<a href="https://nicolas-hbt.github.io/educ-ontokg/widoco/index-en.html">Widoco Documentation</a>).</li>
  </ul>
</content>
 
 <hr/>

<article class="mb-5" id="directions">
<content>
<h2>Directions</h2>
  <p>This section aims at giving an overview of this resource website. It is divided in several sections made visible in the right sidebar:</p>
  <ul>
    <li><strong>EducOnto</strong>: this section gives the reader a conceptual overview of the proposed ontology. A deeper dive into EducOnto structure is subsequently provided, through a thorough description of the main classes and properties of the ontology. A download link is also provided;</li>
    <li><strong>Competency Questions</strong>: this section is concerned with the evaluation of EducOnto. Several competency questions are defined and SPARQL queries are run against an instantiated version of the ontology to clearly demonstrate EducOnto's potential;</li>
    <li><strong>EduKG</strong>: this section elaborates on the proposed Educational Knowledge Graph. Motivations for building EduKG are briefly introduced. Then, the main statistics about the dataset are revealed. A download link is also provided;</li>
    <li><strong>Download</strong>: this section brings together EducOnto's and EduKG's download links. Moreover, we provide the reader with details about the tools we used during the development process;</li>
    <li><strong>GitHub project</strong>: access to the GitHub repository of the project.</li>
  </ul>
</content>
