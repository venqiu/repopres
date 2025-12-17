---
title: "Local Solution"
weight: 4
---

**Local Solution:**

If you decide to preserve source code yourself, there are different levels of preservation standards you can abide by – depending on the resources and capacity you have to maintain your software. The following instructions are based on the National Digital Stewardship Alliance’s (NDSA) 4 levels of digital preservation, which we have adapted to fit the needs of Github repository preservation. These methods for storing software are based on MackinationsAI’s guide (link). 

- [MackinationsAI ](https://github.com/MackinationsAi/preserve-open-source)

​	**Prerequisites:**

​	Before you start, make sure you have:

​		• Git installed

​		• On macOs with [Homebrew](https://brew.sh/): `brew install git`

​		• On Ubuntu/Debian: `sudo apt-get install git`

​	        • (Optional but recommended) Git LFS if the repo uses large files

​	        • `brew install git-lfs` or `sudo apt-get install git-lfs`

​        • then run git lfs install

​		• Enough disk space on the target drive

​		• On the repo’s GitHub page you can check the approximate size

​	**Simple “mirror” clone (good for long-term storage)**

​		If you mainly care about **preserving the history** and do not need to open the project in an editor right now, 		**amirror clone** is the safest and most compact option.

```bash
		# 1. Choose a directory where you keep archivescd /path/to/archive/folder

​		# 2. Mirror-clone the repository

​		git clone --mirror https://github.com/username/repository.git

​		\# 3. Enter the bare repo

​		cd repository.git

​		# 4. (Optional) Fetch all Git LFS objects, if used

​		git lfs fetch --all  # only works if Git LFS is installed

​		# 5. Fetch all tags explicitly (usually already included)

​		git fetch --all --tags`
```

​	**What this gives you**

​		• a bare Git repository in repository.git/

​		• all branches and full commit history

​		• all tags and refs

​		• (if you ran git lfs fetch --all) all LFS objects

​		You cannot open this bare repo directly in most IDEs, but you can **recreate a working copy in the future** f		rom this archive:

```bash
# later, on another machine:
git clone /path/to/archive/repository.git my-working-copy`
```

​		This is a good choice if your **Local Solution** is mainly about long-term storage.

​	**Verification**

​		Check how many branches you have:

​		`git branch | Measure-Object -Line`

​		View all branches:

​		`git branch -a`

​		Check disk usage:

​		`Get-ChildItem .git -Recurse | Measure-Object -Property Length -Sum`

​	**How this fits into the Local Solution section**

​		This bash guide is one concrete implementation of the Local Solution described in the main decision guide:

​		It stays on your own storage (external disk, NAS, etc.).

​		It does not depend on Software Heritage or any institution.
​		It can be combined with other strategies (for example, you can mirror to two disks and also submit the repo 		to Software Heritage).
​		For many individual developers or small groups, this is the fastest way to gain real control over their GitHub 		code: a copy that lives on their own hardware, with all branches, tags, and history preserved.



- NDSA Standards (link to [NDSA levels of digital preservation table)](https://ndsa.org/publications/levels-of-digital-preservation/)
  - Level 1: Know your content
  - Level 2: Protect your content
  - Level 3: Monitor your content
  - Level 4: Sustain your content



Levels of Github Repository Preservation

|           | Level 1 (Know your content)                                  | Level 2 (Protect your content)                               | Level 3 (Monitor your content)                               | Level 4 (Sustain your content)                               |
| --------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Storage   | Have 2 complete copies of this repository in separate locations Document all storage media where content is stored (a finding aid for your harddrives)  Put content in stable storage | Have 3 complete copies of this repository in separate locations Document storage and storage media indicating the resources and dependencies they require to function | Have at least one copy in a geographic location with a different disaster threat than the other copies Have at least one copy on a different storage media type Track the obsolescence of storage and media | Have at least three copies in geographic locations, each with a different disaster threat  Maximize storage diversification to avoid single points of failure Have a plan and execute actions to address obsolescence of storage hardware, software, and media |
| Integrity | Verify integrity information if it has been provided with the content  Generate integrity information if not provided with the content Bagit and generate a checksum ([more info](https://www.youtube.com/watch?v=nYG459M7FmY)) Virus check all content; isolate content for quarantine as needed | Verify integrity information when moving or copying content Use write-blockers when working with original media Back up integrity information and store copy in a separate location | Verify integrity information of content at fixed intervals Document integrity information verification processes and outcomes Perform audit of integrity information on demand | Verify integrity information in response to specific events or activities  Replace or repair corrupted content as necessary |
| Control   | Determine the human and software agents that should be authorized to read, write, move, and delete content | Document the human and software agents authorized to read, write, move, and delete content and apply these | Maintain logs and identify the human and software agents that performed actions on content | Perform periodic review of actions/access logs               |
| Metadata  | Create inventory of content, also documenting current storage locations | Store enough metadata to know what the content is (this might include some combination of administrative, technical, descriptive, preservation, and structural)  You could model your metadata document off of the [Guggenheim’s Identity Report for Sun Yuan and Peng Yu’s piece *I Can’t Help Myself*](https://www.guggenheim.org/wp-content/uploads/2019/12/guggenheim-identity-report-cant-help-myself-sun-yuan-peng-yu.pdf) *or* | Determine what metadata standards to apply Find and fill gaps in your metadata to meet those standards | Record preservation actions associated with content and when those actions occur  Implement metadata standards chosen |
| Content   | Document file formats and other essential content characteristics including how and when these were identified (This could be based on | Verify file formats and other essential content characteristics Build relationships with content creators to encourage sustainable file choices | Monitor for obsolescence, and changes in technologies on which content is dependent | Perform migrations, normalizations, emulation, and similar activities that ensure content can be accessed |