---
# See project.yml for variables.
---

# About
_Building community around and gathering knowledge about the world’s stoneflies_

## Overview
The {{app:focal_taxon}} Species File offers a community-curated collection of richly-cited and annotated data on the taxonomy of Earth’s {{app:focal_taxon_common_name}}. Plecoptera Species File is powered by [TaxonWorks](https://taxonworks.org) managed by the [Species File Group](https://speciesfilegroup.org). See [Contribute](#contribute) below for how you can participate. This site is built using TaxonPages, [learn more and get help]().

## Gaps as Opportunity
The Earth's biodiversity is vast, the data captured to describe it are minimal in comparison, but still immense. All projects of this nature contain gaps, i.e. opportunities for collaboration on future work, grants, and research. Known gaps in this project include {an incomplete catalog of type-material (important specimens that are linked to the names given to species}, {species names published after XXXX}, {biological associations}, {distributions from X} and more. [Contact us](#contact) if you would like to help us address these, in particular we'd like to prioritize {choose from list above}.

## History
_Our old website is now a read-only resource available at [https://{{app:focal_taxon}}.archive.speciesfile.org](https://{{app:focal_taxon}}.archive.speciesfile.org)._

{How did the Species File Group come to be (shared history)}. How did this specific SF group come to be? When did we start our efforts? What are the historically important catalogs behind these data.}

As of 2023-08-## all data in the former Species File Websites were frozen and shortly thereafter migrated to TaxonWorks. As with all migrations of this nature the process is both lossy (e.g. some data could not be mapped with certainty) and improved (e.g. semantics of the new models have more precision and clarity).  The old website remains an excellent resource for fact-checking this migration. If you spot something that needs attention, please see [contribute](about#contribute).

## Team
### Contribute
_Projects of this nature require expertise in many different areas, not only on the taxa being treated. If you can imagine a way to contribute we'd love to hear about it._

* Join the {{app:focal_taxon}} Species File regular support meetings at { details if these exist }./
* Enquire about joining the researchers building this Species File: [{ProjectManager}](mailto:dewalt@illinois.edu).
* Provide new data or to identify a problem with existing data: [{ProjectManager}](mailto:address@example.com). {Issue tracker option}.
* Report a technical bug (e.g. broken link or button) within TaxonPages: [TaxonPages' issue tracker](https://github.com/SpeciesFileGroup/taxonpages/issues/new?assignees=&labels=bug&projects=&template=bug.yml&title=%5BBug%5D%3A+)
* TaxonWorks and TaxonPages are open-source efforts that are [opportunities for you and others to join](https://docs.taxonworks.org/develop/contributing.html) to request new features, report bugs, or discuss use among other things.

### Contributors
|Name|Affilation|Role|Email|
|:----|:----|:----|:----|
| R. Edward DeWalt | University of Illinois, Illinois Natural History Survey | Author | dewalt@illinois.edu |
| Heidi Hopkins | Ithaca College | Author | cockroachdoc@gmail.com |
| U. Neu-Becker | Max-Planck Institute | Author |
| G. Stueber | Max-Planck Institute | Author |
| Lily Hart | University of Illinois, Illinois Natural History Survey | Editor | lvhart2@illinois.edu

Please send **comments** and **questions** about the database and its development to R. Edward DeWalt (send email).  
How to **cite** this website, please use the following format: **DeWalt, R. E., H. Hopkins, U. Neu-Becker and G. Stueber. 2023. Plecoptera Species File. [retrieval date]. <([https://sfg-taxonpages.github.io/plecoptera/#/](https://sfg-taxonpages.github.io/plecoptera/#/))>**

### Support and Cooperation
_Plecoptera Species File functionality and content are made possible through services by:_

* Species File Group
* University of Illinois, Illinois Natural History Survey
* National Science Foundation (NSF) under Grant DEB 09–18805 ARRA. Any opinions, findings, and conclusions or recommendations expressed in this material are those of the author(s) and do not necessarily reflect the views of the NSF.

### The Species File Group
The Species File Group (SFG) is an endowment-funded collective of specialists whose broader goal is the advancement of biodiversity informatics. We are located at the University of Illinois, Illinois Natural History Survey. Our group supports the following software/activities: 

* [TaxonWorks](taxonworks.org) - a workbench for taxonomists and natural history museums.
* [Global Names Architecture](globalnames.org) - finding, parsing, and resolving taxon names from literature. Lead Developer: Dmitry Mozzherin.
* [Catalogue of Life](catalogueoflife.org) - editorial group, and data assembly hub. Executive Editor Yury Roskov and Database Manager Geoff Ower.
* Taxonomic/Systematic Research supporting several insect groups.

#### The TaxonWorks Community
Everyone joining us at our weekly meetings, everyone who invests efforts to capture, study, and share knowledge using and developing our software, and building on or connecting to our services, enriches our goal to support evolving our broader community efforts to describe life, together. The work revealed on this website comes from many community meetings, many hours of research, a lot of software and data model development. This includes considerable effort to support impactful culture change and potentially enhanced standards of practice for data capture, sharing resources, knowledge, and workload. Please join us any Wednesday to add your voice to our community and learn more (see [Events](https://speciesfilegroup.org/events.html)).

## Extended access
_A goal of these pages is to ensure that the underlying data behind them are accessible in their digital format. By diversifying the ways the data are accessible (e.g. on the web page, in JSON, in Darwin Core standard), we increase the opportunities to both spot errors and provide new services and portals._

* Researchers working on this project use their rich, multi-faceted access to the data via TaxonWorks' interfaces (e.g. filters, reporting, downloads). Access requires a project account, see [Contacts][#contact].
* Data behind individual panels can be seen via the *SiteMap* functionality.
* Each page offers an option to download a *DarwinCore formatted table* containing all data for this taxon and its children.
* Panel data (each section on a page) and other data not available here are accessible via a [TaxonWorks API](https://api.taxonworks.org) at [https://sfg.taxonworks.org/api/v1](https://sfg.taxonworks.org/api/v1),
* Core taxonomic data are exported to and available at the [Catalogue of Life]({https://link_to_root_taxon_page}) and its [associated API](https://link_to_api_for_pertinent_dataset).

### Websites
* [PERLA Annual News Letter](http://plecoptera.speciesfile.org/HomePage/Plecoptera/PerlaList.aspx)
* [ILLIESIA International Journal of Stonefly Research](http://illiesia.speciesfile.org/)


## Terms of Use (Copyright Guidance)

<div class="flex items-center gap-2">
  <a
    class="min-w-fit"
    href="{{ app:copyright_image_link }}"
  >
    <img 
      src="{{ app:copyright_image }}" 
      alt="copyright" 
      class="m-0"
    >
  </a>
  <span>{{ app:copyright_text }}</span>
</div>
