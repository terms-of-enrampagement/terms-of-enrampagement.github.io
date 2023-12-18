---
title: Ideas for creating and utilising legal datasets
feature_text: |
  Computational thinking, Artificial Intelligence, and a modicum of knowledge about the law all go together to create an opportunity for lawyers. 
excerpt: |
  "Some platforms are increasingly adopting Digital Restrictions Management, but that does not in any way guarantee that content you prepared to be shared and accessed widely will generate monetisation. You need to set your terms for the utilisation of your work, whether for "derivative works", trademark usage, or even straight up commercial use."
date: 2023-12-18
---

 <a href = "#UseCases"> To go directly to a list of use-cases I'm in the process of developing, click here </a> 

<section id="Licensing">
<h2>The benefits of copyleft licensing, and where to find sources for legal datasets</h2>
</section>

What are the benefits of publishing a legal dataset with a Creative Commons license? It allows people to utilise your content as per your terms, and also increases the visibility of your content. 

My law professors, and indeed many of those in the academic space have deliberated on the internet's tendency to make memes or other forms of "derivative" content regardless of the license it utilises. Some platforms are increasingly adopting Digital Restrictions Management, but that does not in any way guarantee that content you prepared to be shared and accessed widely will generate monetisation. You need to set your terms for the utilisation of your work, whether for "derivative works", trademark usage, or even straight up commercial use. 

Now that that is apparent, we can also utilise datasets (or even data in its raw form) when it occurs in the wild in a permissive license. So, here's a list of some sources I found helpful:

- Indian laws from their original sources - This content is free from copyright restrictions by virtue of Section 52 of the Copyright Act, the relevant clauses from which are reproduced below:

```
Section 52. *Certain acts to not be infringement of copyright*
(1) The following acts shall not constitute an infringement of copyright, namely,--
...
..
.
(q) the reproduction or publication of--
(i) any matter which has been published in any Official Gazette except an Act of a Legislature;
(ii) any Act of a Legislature subject to the condition that such Act is reproduced or published together with any commentary thereon or any other original matter;
(iii) the report of any committee, commission, council, board or other like body appointed by the Government if such report has been laid on the Table of the Legislature, unless the reproduction or publication of such report is prohibited by the Government;
(iv) any judgment or order of a court, tribunal or other judicial authority, unless the reproduction or publication of such judgment or order is prohibited by the court, the tribunal or other judicial authority, as the case may be;
```
What this means is that texts of laws when obtained from the [eGazette](egazette.gov.in) - which has [replaced the publication of the Gazette in the printed form](https://pib.gov.in/newsite/PrintRelease.aspx?relid=128570), are free from copyright restrictions.

Another rich data source is the eCourts platform which provides all the judgments or orders in PDF forms. Although you will require some knowledge of processing case details for navigating this specific portal, I think that's a task for a separate post altogether.

- YouTube's Creative Commons works - While multimedia might be a lesser known platform for extracting legal data, there is an increasing corpus of such work licensed as Creative Commons. The best part is, you can search through all of them using YouTube's in-built filters. [And their help page offers a link to what content can be marked as such, if you are looking to upload your own.](https://support.google.com/youtube/answer/2797468)

- [Internet Archive](archive.org/) - A great many texts, reports of law commissions, and even books which are presumably listed under the Creative Commons license or Public Domain are available here. A word of caution, though, if you want to seriously extract and republish data from this source - do ascertain whether the term of copyright in the country where you plan to publish your work lies. In the case of an internet platform, those in India, would be bound by the Copyright Act regardless of its global reach. Reason I mention this is, there are many works here that are intended for US users/audiences.

- Open Access legal journals are a great source of information - I had linked to where you can find these in a [previous blog post](https://sankalpsrv.in/2023/06/25/ReasearchingIndianLaw/) - I am reproducing the relevant section below


	- Open Access Journals/Journals with free texts
	These valuable sources of multidisciplinary and even legal scholarly content in peer-reviewed journals, sometimes available in the public domain or a "copyleft" license are useful for legal and non-legal research both. Some popular indexes are:-
		- [Law Review Commons](https://lawreviewcommons.com) - This is the largest index of open access journals in the field of law, with a majority of English language and American journals.	
		- [Database of Open Access Journals](https://doaj.org) - As of the date of my writing, there are 537 Law journals in English indexed here. This supports keyword search and can be used for sharpening your legal awareness with new trends. 
		- [The Electronic Journals Library](http://ezb.ur.de/ezeit/fl.phtml?bibid=AAAAA&colors=1&lang=en&notation=P) - This index provides a resource of "freely available texts" when filtered through with the option named as such. You can also similarly filter on Google Scholar and Semantic Scholar.
		- While not "popular" per se, some governmental institutes also post a compendium of links to Open Access Databases in the law category. For example, [Delhi Judicial Academy](https://judicialacademy.nic.in/knowledge-gateway/open-access-resources) provides international resources, and [NALSAR, Hyderabad](https://library.nalsar.ac.in/open-access-resources/) provides a list of resources from a variety of jurisdictions.


<section id="UseCases">
<h2>Use-cases which I am working on currently, or plan to incorporate further</h2>
</section>

1. I've created a unique tool for extracting specific clauses from judgment documents in PDF format. My next step is to make this data publicly available, following the completion of my detailed clause annotation process.

2. I'm currently employing a blend of OpenNyAI and similar ML models to work on a set of judgments.

3. An interesting project I believe has academic potential involves harvesting data from ecourts and various other APIs. This data serves as the foundation for performing topic modeling and other sophisticated analyses in the realm of NLP and data science.

4. As I think having a resource for easy access to government notifications is necessary, I've developed and shared a preliminary version of a website that serves as a directory for some of these. You can explore this initial version here: https://env-law-notification-browser.onrender.com/browse. This one will require me to go through to the original sources for each of them, as the government websites that host these often have restrictions on hyperlinking. 

5. With respect to government notifications that undergo constant change, the Indigo project offers a software to implement point-in-time classification. While not a legal dataset in strict terms, it depends on the Akoma Nsoto (or LegalXML) format for exchanging data, that I think largely conforms to the philosophy of sharing data on legislations. 

<iframe src="https://www.linkedin.com/embed/feed/update/urn:li:share:7142173806361583616" height="1644" width="504" frameborder="0" allowfullscreen="" title="Embedded post"></iframe>
