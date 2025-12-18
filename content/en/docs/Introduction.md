---
title: "Introduction"
weight: 1
---

## **Introduction:** 

This is a decision guide for preserving a github repository. There are many approaches to doing this, with varying degrees of effort, difficulty, longevity, and dependability. The following guide outlines three main methods for preserving source code found on [github.com](http://github.com). 

**Why is it important to preserve source code?** 

Software has become an integral part of modern society, embodying significant portions of our cultural knowledge. However, as Di Cosmo and Zacchiroli (2017) eloquently state, unlike other forms of digital preservation, source code has not yet achieved the status of “first class citizen in the digital archive landscape.”

**Why software is at risk:**

**Inherent obsolescence** - Software depends on specific execution environments, languages, and dependencies that keep evolving and there is no unifying data model for version control systems.

**Project abandonment** - Without active maintenance, the knowledge of specific softwares can be lost permanently. 

**Censorship** - Despite software frequently migrating between platforms, there is always a chance that code hosting platforms would remove content due to policy violations and political pressure.

**Platform dependence** - Most code hosting platforms do not offer any long term preservation guarantees. The 2015-16 shutdown of Gitorious and Google Code demonstrated this as over 1.5 millions projects had to relocate in a short timeframe.

------

**Current state of software preservation**

Two major initiatives currently represent different approaches to software preservation. [**GitHub’s Arctic Code Vault**](https://archiveprogram.github.com/arctic-vault/) takes a focused approach to creating a long-term physical backup. The initiative stores snapshots of public repositories in a decommissioned coal mine in the Svalbard archipelago, a location chosen for its geological stability. However, the Vault primarily focuses on creating snapshots rather than capturing complete development histories with all their evolution, functioning essentially more as a disaster recovery backup than an active archive.

[**Software Heritage**](https://www.softwareheritage.org/) takes a fundamentally different approach to focus on broad accessibility and long-term viability. Rather than relying on a single backup location, Software Heritage maintains a geographic network of “mirrors” and operates on a principle of no a priori selection to archive comprehensively. As of June 2022, Software Heritage has archived over 180 million software origins with more than 12 billion unique source code files, making it the largest corpus of source code available on the planet.

------

**Components of GitHub Repository**

Understanding what comprises a complete GItHub repository reveals the challenges in considering which elements are essential versus secondary.

Core technical artifacts:

- Source code: The primary artifact
- Commit history: Record of changes that affect the file
- Branch: Separate workspace for new changes without affecting the main branch
- Tag: Marker referencing a specific commit within project history
- README: Overview documentation of the project
- License: Legal declaration governing use and distribution

Recording these elements provides what might be called a comprehensive snapshot of the repository at a given point in time. Like a disk image, these artifacts document a digital volume’s particular content and functionality at a particular moment. This represents the minimum viable preservation effort as it captures the project with sufficient detail that future users could understand and potentially build upon the work. For software that never had significant community engagement, this level of preservation may be adequate. 

However, contemporary software development is an increasingly collaborative process. Preserving these secondary content provides a richer understanding of the repository as a community artifact, such as revealing the decision-making processes through which communities debate technical approaches, though the dynamic nature of these elements presents challenges for preservation.

- [Issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/learning-about-issues/about-issues) and [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests): Bug reports and proposed code changes
- [Wiki page](https://docs.github.com/en/communities/documenting-your-project-with-wikis/about-wikis): Extended, long-form information
- [Project](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects): Tool for planning and tracking work on GitHub 
- [Release](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases): Software iteration for distribution including notes
- [Actions](https://docs.github.com/en/actions/get-started/understand-github-actions): Platform allowing automated processes for continuous integration / continuous delivery
- [Discussions](https://docs.github.com/en/discussions): Collaborative communication forum

**The question of metadata and related materials**

The question of metadata and related materials is a key one in archiving and software preservation. Different approaches to keeping and labeling the ancillary materials related to a piece of source code greatly shape the differences between preservation approaches. 