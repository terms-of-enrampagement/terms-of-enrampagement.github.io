---
title: The story behind Schematise and a use-case demonstration 
feature_text: |
   A HITL ("Human-in-the-loop") annotation task for a demonstration of legal ontology usage and I'm only halfway done.
excerpt: |
  "... For instance, in a text-classification model trained on Indian laws, one could be assisted by Schematise to categorise which statements represent obligations..."
date: 2024-04-16
categories: 
  - Legal Tech
  - AI
  - Currently working
---
Table of Contents:
<ol>
<li> <a href = "#Section1"> An overview of Schematise, as it currently stands (16th April, 2024). </a> </li>
<li> <a href = "#Section2"> Why have laws in XML? </a> </li>
<li> <a href = "#UseCase"> A demonstration of compliance mapping using LegalRuleML </a> </li>
</ol>


<section id = "Section1">
<h3> An overview of Schematise, as it currently stands (16th April, 2024). </h3>
</section>

I started the project "Schematise" at The Fifth Elephant's Open Source AI Hackathon as a way to get a programmatic way of generating 
laws in the XML format (for reasons explained hereunder). 

My intention was to expedite the annotation of laws in a way that a single user can decrease the amount of time required for the same. 
The reason I say "single user" here is because I think the way to utilise machine-readability in the current era of Legal-Tech development
will require a single organisation or individual to adapt the code to their requirements.

Hence, for example, training a model on the dataset generated (using the Local Inference method without OpenAI) would first 
necessitate the expression in a way that suits the training of the model. 

<h4> Usage for dataset generation </h4>

For instance, in a text-classification model trained on Indian laws,
one could be assisted by Schematise to categorise which statements represent obligations, and which ones represent prohibition or any of the other categories available in the LegalRuleML documentation.

<section id = "Section2">
<h3> Why have laws in XML? </h3>
</section>
Machine-readability (to put it simply).

There are a great many problems that get solved using machine-readable laws. As the name suggests, this allows you to
express legal information in a way that enables:

- Semantic annotation
- Interoperability (say, across jurisdictions, or even across contexts)
- Temporal management (a great language for [point-in-time classifications, as IndianKanoon's blogpost explains](https://blog.indiankanoon.org/2024/01/comprehensive-up-to-date-laws-from.html))

<h5> How does AkomaNtoso help? </h5>

- A standard of "legal ontology" that is uniform across contexts. 
- It is an [OASIS Open Standard](https://www.oasis-open.org/2018/08/30/akoma-ntoso-version-1-0-becomes-an-oasis-standard/) which further helps in utilisation, due to its expansive documentation.
- It has been historically deliberated. One of the benefits are the several examples that exist on the GitHub repositories - [[1]](https://github.com/oasis-open/legaldocml-akomantoso)[[2]](https://github.com/oasis-open/legalruleml-repo) that can be utilised with attribution as per their terms of the CC license.

<section id = "UseCase">
<h3> Complianalyse (proof of concept) </h3>
</section>

<a href = "https://complianalyse-webapp-poc.onrender.com/"><img src = "/assets/images/Complianalyse-POC.png" alt = "Screenshot of the Complianalyse POC app"></a>

> 'Before there came "Schematise", there was "Complianalyse"'

I started off the Fifth Elephant + Hasgeek's Open Source AI Hackathon conceiving of an app that could generate compliance checklists from an XML format.

But due to the lack of an automated method to generate laws in XML as of yet, and in the interests of adhering with the UNIX philosophy of
"Doing one thing and doing it well", I decided to first build Schematise.

Nevertheless, events took an interesting turn with the news regarding an advisory issued by the Ministry of Electronics and Information Technology under the Government of India.
Hence, a use-case presented itself for the purpose of testing whether Schematise was generating XML content that could reasonably serve the purpose for building a simple compliance-checklist app.

Hence, I took time to program a simple [python Flask app](https://complianalyse-webapp-poc.onrender.com/) to test this.

<h4> Here is a brief overview of what the development process was: </h4>

- I first generated and edited the XML content from Schematise using the Local Workflow. 

Hence, a paragraph such as,

> All intermediaries or platforms to ensure that their computer resource do not permit any bias or discrimination or threaten the integrity of the electoral process including via the use of Artificial Intelligence model(s)/LLM/Generative AI, software(s) or algorithm(s).

would get represented in XML as,

```
<lrml:Statements key="textblock2">
    <lrml:PrescriptiveStatement key="paragraph3">
        <ruleml:Rule>
            <ruleml:if>
                <ruleml:And>
                    <ruleml:Atom keyref=":intermediaryORplatform">
                        <ruleml:Var>Intermediary</ruleml:Var>
                        <ruleml:Var>Platform</ruleml:Var>
                    </ruleml:Atom>
                    <ruleml:Atom keyref=":useAIModelLLMGenerativeAISoftwareAlgorithm"/>
                    <ruleml:Atom keyref=":CResource"/>
                </ruleml:And>
            </ruleml:if>
            <ruleml:then>
                <lrml:SuborderList>
                    <lrml:Prohibition>
                        <ruleml:Atom>
                            <ruleml:Rel iri=":permit"/>
                            <ruleml:Ind>bias</ruleml:Ind>
                        </ruleml:Atom>
                    </lrml:Prohibition>
                    <lrml:Prohibition>
                        <ruleml:Atom>
                            <ruleml:Rel iri=":permit"/>
                            <ruleml:Ind>discrimination</ruleml:Ind>
                        </ruleml:Atom>
                    </lrml:Prohibition>
                    <lrml:Prohibition>
                        <ruleml:Atom>
                            <ruleml:Rel iri=":threaten"/>
                            <ruleml:Ind>integrity of electoral process</ruleml:Ind>
                        </ruleml:Atom>
                    </lrml:Prohibition>
                </lrml:SuborderList>
            </ruleml:then>
        </ruleml:Rule>
    </lrml:PrescriptiveStatement>
</lrml:Statements>

```

- Thereafter, I added code to allow users to select which of the paragraphs they would like to check their compliance obligations for.
I also added an option to view the paragraph of the advisory while hovering over the selection using Javascript. Like all other coding in this project, 
this was done with the help of LLMs.

- Lastly, I added backend modules in Python to parse through the XML generated programmatically and generated compliances based on conditions. You can view this code with comments explaining the process of parsing the XML in the format I annotated the law at [this GitHub link (click here)](https://github.com/sankalpsrv/Schematise/tree/Complianalyse-webapp-POC)

