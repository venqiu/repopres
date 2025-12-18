---
title: "Software Heritage"
weight: 5
---

## **Software Heritage:**

**About Software Heritage**

Software Heritage was founded in 2016, launched by Inria in partnership with UNESCO. Their mission is to “collect, preserve, and make readily accessible all the software source code ever written” ([Source](https://hal.science/hal-03375572)).Check if your repository is already by visiting their online archive at https://archive.softwareheritage.org/. If not, then issue an origin save request [here](https://archive.softwareheritage.org/save/).

**The Software Heritage Acquisition Process**

 In their 2021 research paper, they outlined what they call the “Software Heritage Acquisition Process” (SWHAP). This process was developed to preserve source code from various sources, including but not limited to software development platforms like Github and Gitlab, legacy platforms like Google Code and Gitorious, package manager repositories like CPAn and npm, and FOSS (free and open source software) distributions such as Fedora and FreeBSD. The following contains a general overview of SWHAP so you can evaluate if Software Heritage is the right place for the code you’d like to preserve. You can find more information from their published research articles 

**Phases**

- Collect: Find the source code and related materials (e.g. research articles, pictures, drawings, user manuals) and gather it ‘as is’ 
- Curate: Analyze and clean up the structure of raw materials (source code). This includes clarifying the production dates, contributors, and general history and evolution of the software. This information is logged as metadata, using [vocabulary from CodeMeta](https://codemeta.github.io/terms/) (e.g. software runtime platform, programming languages, authors, license)
- Archive: Upload or contribute the each category of materials to the appropriate infrastructures: Software Heritage for source code, Wikimedia for images and videos, open access repositories for research articles, Wikidata for software descriptions and properties, and so on
- Present: Create presentations, exhibitions, events, or websites from the results

------

**Software artifacts: How SWHAP divides their components**

The following categories are how Software Heritage distinguishes the different components that make up the “raw materials” of software:

- file contents (AKA ‘blobs’): the raw content of the source code in the form of bytes
- directories: a list of named directories, each pointing to other artifacts
- revisions (AKA ‘commits’): each recorded copy of the root directory is known as a revision
- releases (AKA tags): milestone revisions
- origins (software provenance): fine grained references to where source code artifacts have been retrieved from.
- projects: abstract entities that relate together several development resources, including websites, issue trackers, mailing lists, as well as software origins
- snapshots: records all entry points found there and where they pointed to. This would include branches for VCS, and suites for package distributions
- visits: link together software origins with snapshots. This is essentially a time stamp of when Software Heritage recorded a snapshot

**Metadata: version_history.csv** 
For each piece of software, the SWHAP recommends that preservationists collect relevant metadata files for each version of the software, in the form of a spreadsheet titled version_history.csv. SWH recommends using [vocabulary provided by CodeMeta](https://codemeta.github.io/terms/) as an extension of schema.org. Here is an example of one. These typically contain:

- director name: name of directory containing the source code of this version
- author name: name of the main author
- date original: original date when this version was made
- curator name: name of the curator person or team
- curator email: reference email of the acquisition process
- release tag: tag name if the directory contains a release, empty otherwise
- commit message: text containing a brief note from the curator team


------

**Explain Merkle Direct Acyclic Graph (DAG) as their way of preventing unnecessary redundancies** 

Software Heritages’ collection is in essence a big Merkle Direct Acyclic Graph (DAG), a multi-node structure in which each of the aforementioned software artifacts (file contents, directories, revisions) constitute one node. With each node having its own intrinsic cryptographic hash, Software Heritage is able to to avoid unnecessary duplication of code, contextualize source with the entire development of all source code in the collection, and establish provenance and code reuse. 

**How often Software Heritage scans for new code**

Software Heritage uses an adaptive scheduling discipline, specifically an “exponential backoff strategy.” This means that they run periodic checks of the source code they collect to scan for changes and edits. If the scan shows changes for any given software origin, they increase the frequency that that site is visited in the future. If the check does not show changes for the software, they decrease the scanning frequency. 

**Where they keep their data**

In order to ensure longevity and security of their collection, Software Heritage is building an international network of mirrors, each hosting a read-only copy of their entire collection. At the moment, they have partnered with ENEA in Italy and GRNET in Greece. 