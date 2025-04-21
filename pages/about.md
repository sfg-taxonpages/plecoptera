---
# See project.yml for variables.
---

# About

_Building community around and gathering knowledge about the world’s stoneflies_

## Overview

The Plecoptera Species File (Plecoptera SF) offers a community-curated collection of richly-cited and annotated data on the taxonomy of Earth’s {{app:focal_taxon_common_name}}. Information includes valid names, their synonyms, bibliographic data, specimen data, images, sounds, and distributions for stoneflies of the world.  The project currently includes the following- <ProjectStats :data="['Taxon names', 'Collection objects', 'Project sources', 'Documents', 'Citations', 'Images', 'Asserted distributions']"/>, along with many annotations and related data.

Our site seeks to include and serve an expanding group of stakeholders such as taxonomists, ecologists, policy makers, and educators.

Plecoptera SF is curated in an instance of [TaxonWorks](https://taxonworks.org) managed by the [Species File Group](https://speciesfilegroup.org). See [Contribute or get help](#contribute-or-get-help) below for how you can participate. This site is built using TaxonPages, [learn more and get help](https://github.com/SpeciesFileGroup/taxonpages).

## Gaps as Opportunity

The Earth's biodiversity is vast, the data captured to describe it are minimal in comparison, but still immense. All projects of this nature contain gaps, i.e. opportunities for collaboration on future work, grants, and research. [Contact us](#contribute-or-get-help) if you would like to help us address these.

## History

_Our old website is now a read-only resource available at [http://plecoptera.archive.speciesfile.org](http://plecoptera.archive.speciesfile.org)._

Species File Software, used to curate the Plecoptera SF during its origin and for over a decade thereafter, was developed by David Eades as a taxonomic workbench. For more information about Species File Software at the [Species File Group Homepage](https://speciesfilegroup.org/) .

Plecoptera SF started with the acquisition of a database of stonefly nomenclature, taxonomy, and distribution from Peter Zwick (His contributors were U. Neu-Becker and G. Stueber, hence their authorship. Zwick declined authorship of this version) in 2007. The data were imported by Marilyn Beckman, Rich Flood, and James Tucker into the original Species File Software. Elizabeth Frank's difference tool allowed Ed DeWalt and Mike Maehr to check import quality and completeness. In 2009 Plecoptera SF was accepted by [Catalogue of Life](https://www.catalogueoflife.org/) as the global source of stonefly names and the [Global Biodiversity Information Facility](http://GBIF.org). Maehr and DeWalt continued data entry until Heidi Hopkins took over most duties in 2017. August 14, 2023 saw data entry into the old Species File Software suspended. The data were ported to our replacement TaxonWorks platform and the setup of a new public user interface in Taxon Pages began. The new website went live on Friday, 29 September 2023. Be aware that that most but not all functionality from the old site is present in the new. Some information about a taxon is now available as a standard data set in Darwin Core. If you think there is a bug or some critical data are missing, then add your request to the Issue Tracker (see Contribute or get help below, or click on the links at the bottom of this page). If you still need more information, one option is to become a collaborator with us. Send a note to DeWalt if you wish to contribute to Plecoptera SF or to use TaxonWorks as your research workbench.

As of August 2023 all data in the former Species File Websites were frozen and shortly thereafter migrated to TaxonWorks. As with all migrations of this nature the process is both lossy (e.g. some data could not be mapped with certainty) and improved (e.g. semantics of the new models have more precision and clarity). The old website remains an excellent resource for fact-checking this migration. If you spot something that needs attention, please see [contribute or get help](about#contribute-or-get-help).

## Do More with TaxonPages

### Create a checklist of species

Watch our YouTube tutorial for help with creating checklists of species using the data in Plecoptera SpeciesFile [Checklists from DarwinCore in a few clicks](https://www.youtube.com/watch?v=OrlmlqZOkwk)

### Contribute or get help

_We welcome you to join us in our efforts! Projects of this nature require expertise in many different areas, not only on the taxa being treated. Collaboration is key. Please see below how to best reach our team with your questions, concerns, suggestions, and ideas:_

- Enquire about joining the researchers building this Species File: [Contact R.E. DeWalt directly](mailto:dewalt@illinois.edu).
- <TrackerReport label="Report a problem or offer data" tag="a" button-class="cursor-pointer"/> (bugs or data issues) on our issue tracker.
- [TaxonWorks](https://taxonworks.org) and TaxonPages are open-source efforts that are [opportunities for you and others to join](https://docs.taxonworks.org/develop/contributing.html) to request new features, report bugs, or discuss use among other things.

## Team

### Contributors

| Name             | Affiliation                                             | Role        | Email                  |
| :--------------- | :------------------------------------------------------ | :---------- | :--------------------- |
| R. Edward DeWalt | University of Illinois, Illinois Natural History Survey | Author      | dewalt@illinois.edu    |
| Heidi Hopkins    | University of Illinois, Illinois Natural HIstory Survey | Author      | cockroachdoc@gmail.com |
| Mike Maehr*      | University of Illinois, Illinois Natural History Survey | Author      |                        |
| U. Neu-Becker    | Max-Planck Institute                                    | Author      |                        |
| G. Stueber       | Max-Planck Institute                                    | Author      |                        |
| Lily Hart        | University of Illinois, Illinois Natural History Survey | Editor      | lvhart2@illinois.edu   |
| Matt Yoder       | University of Illinois, Illinois Natural History Survey | Facilitator |                        |
| Rich Flood       | University of Illinois, Illinois Natural History Survey | Facilitator |                        |
| Elizabeth Frank* | University of Illinois, Illinois Natural History Survey | Facilitator |                        |
| Jim Tucker*      | University of Illinois, Illinois Natural History Survey | Facilitator |                        |
| Marilyn Beckman* | University of Illinois, Illinois Natural History Survey | Facilitator |                        |

_* Past contributor, now inactive._

### Cite this website

_please use the following format:_  

DeWalt RE, Hopkins H, Neu-Becker U, and Stueber G. {{ (new Date()).getFullYear() }}. Plecoptera Species File. [retrieval date]. <https://plecoptera.speciesfile.org>

### Support and Cooperation

_Plecoptera Species File functionality and content are made possible through services from:_

- Species File Group
- University of Illinois, Illinois Natural History Survey
- National Science Foundation (NSF) under Grant DEB 09–18805 ARRA. Any opinions, findings, and conclusions or recommendations expressed in this material are those of the author(s) and do not necessarily reflect the views of the NSF.

### The Species File Group

The [Species File Group (SFG)](https://speciesfilegroup.org/index.html) is an endowment-funded collective of specialists whose broader goal is the advancement of biodiversity informatics. We are located at the University of Illinois, Illinois Natural History Survey. Our group supports the following software/activities:

- [TaxonWorks](https://taxonworks.org) - a workbench for taxonomists and natural history museums.
- [Global Names Architecture](https://globalnames.org/) - finding, parsing, and resolving taxon names from literature. Lead Developer: Dmitry Mozzherin.
- [Catalogue of Life](https://catalogueoflife.org/) - editorial group, and data assembly hub. Executive Editor Yury Roskov and Database Manager Geoff Ower.
- Taxonomic/Systematic Research supporting several insect groups.

#### The TaxonWorks Community

Everyone joining us at our weekly meetings, everyone who invests efforts to capture, study, and share knowledge using and developing our software, and building on or connecting to our services, enriches our goal to support evolving our broader community efforts to describe life, together. The work revealed on this website comes from many community meetings, many hours of research, a lot of software and data model development. This includes considerable effort to support impactful culture change and potentially enhanced standards of practice for data capture, sharing resources, knowledge, and workload. Please join us any Wednesday to add your voice to our community and learn more (see [Events](https://speciesfilegroup.org/events.html)).

## Extended access

_A goal of these pages is to ensure that the underlying data behind them are accessible in their digital format. By diversifying the ways the data are accessible (e.g. on the web page, in JSON, in Darwin Core standard), we increase the opportunities to both spot errors and provide new services and portals._

- Researchers working on this project use their rich, multi-faceted access to the data via TaxonWorks' interfaces (e.g. filters, reporting, downloads). Access requires a project account, see [Contacts][#contact].
- Data behind individual panels can be seen via the _SiteMap_ functionality.
- Each page offers an option to download a _DarwinCore formatted table_ containing all data for this taxon and its children.
- Panel data (each section on a page) and other data not available here are accessible via a [TaxonWorks API](https://api.taxonworks.org) at [https://sfg.taxonworks.org/api/v1](https://sfg.taxonworks.org/api/v1),
- Core taxonomic data are exported to and available at the [Catalogue of Life](https://www.catalogueoflife.org/data/dataset/1065).

### Websites

- [PERLA Annual News Letter](http://plecoptera.archive.speciesfile.org/HomePage/Plecoptera/PerlaList.aspx)
- [ILLIESIA International Journal of Stonefly Research](http://illiesia.speciesfile.org/)

### Past meetings

#### 2022 XVIth INTERNATIONAL CONFERENCE ON EPHEMEROPTERA AND XXth INTERNATIONAL SYMPOSIUM ON PLECOPTERA
<a href="http://plecoptera.archive.speciesfile.org/HomePage/Plecoptera/MF_SF 2022 Program and Schedule.pdf" target="naps">Download PDF of 2022 Program</a>.

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
