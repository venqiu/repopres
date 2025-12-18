---
title: "First steps: Evaluating"
weight: 2
---

## **First steps: Evaluating**

Before beginning the archival process, ask yourself fundamental questions about your goals and the repository’s significance.

**Why are you archiving this repository?**

Understanding your motivation helps determine the appropriate preservation approach:

- Software history preservation: Contributing to the history of software development
- Personal backup: Ensuring your own work is safely stored
- Community preservation: Protecting software important to a specific community
- Emergency rescue: Saving at-risk code before it disappears
- Research purposes: Preserving software for academic story or reproducibility

**Is It Already Preserved?**

Before investing effort in archiving, check if the repository is already preserved:

Check Software Heritage

1. Visit [Software Heritage](https://archive.softwareheritage.org/)
2. Search using the repository URL (e.g., https://github.com/venqiu/repopres) 
3. If found, verify the archive includes:
   - Recent commits and branches
   - Complete commit history
   - All releases and tags

Even if already archived, you may still want to preserve additional context (issues, discussions, wiki) that Software Heritage doesn’t capture.

**GitHub Repository Evaluation Checklist**

Use this checklist to assess the completeness and archival readiness of your repository:

Completeness Assessment

Core components:

- Source code is present and readable
- Commit history exists and is complete
- README provides basic documentation
- License is clearly specified
- Dependencies are documented

Functionality status:

- Software builds successfully (if applicable)
- Installation or setup instructions exist
- Critical bugs are documented, if not fixed
- Known limitations are noted

Dependencies and External Requirements

Identify external dependencies:

- Programming language version
- External libraries and packages
- System dependencies (OS-specific)
- Hardware requirements
- Network services or APIs

Document what won’t be captured:

- Proprietary components not included in the repo
- Unpackaged files too large for upload
- Community knowledge not documented in code

Version Control Systems

Be prepared to work with various version control systems:

Common Systems:

- Git: Most prevalent
- Mercurial: Similar to Git; Check [Git vs. Mercurial](https://medium.com/@Nelsonalfonso/git-vs-mercurial-the-battle-of-distributed-version-control-titans-79ffbf3d67d7)
- Apache Subversion (SVN): Centralized, client-server architecture
- CVS, Darcs, Bazaar: Less common alternatives