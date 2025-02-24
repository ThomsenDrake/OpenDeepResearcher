# Git vs. Mercurial: A Detailed Comparison for Version Control

## Original Query
git vs mercurial for version control

## Research Findings
Final Report:
Git and Mercurial are both distributed version control systems (DVCS).

Mercurial is easier to learn and use, but its branching model often creates confusion. Git is more complex and requires more expertise.

Git has become an industry standard with over 80% of the market share. Mercurial has about 2% of the VCS market share.

Key Differences:

*   **Usability:** Mercurial is simpler with easier-to-understand syntax and documentation. Git is more complex, requiring more in-depth knowledge.
*   **Security:** Mercurial may be safer for less experienced users because it doesn't allow changing history by default. Git allows all involved developers to change the version history.
*   **Branching:** Git's branching model is more effective; branches are lightweight references to commits. Mercurial's branching model can be cumbersome, embedding branches in commits and making them difficult to remove. Git supports a staging area (index file) to choose which files to commit, while Mercurial commits changes as they are in the working directory (though extensions exist to add staging functionality).

Git is a clear choice for web and mobile application development. Mercurial's advantage is that it’s easy to learn and use, which is useful for less-technical content contributors.

- Both Git and Mercurial use the same abstractions: a series of snapshots (changesets) that make up the history. Each changeset knows where it came from (the parent changeset) and can have many child changesets.
- Git has a strong focus on mutating this history graph, whereas Mercurial does not encourage history rewriting.
- Mercurial has supported repositories with multiple branches. Git repositories with multiple branches are multiple diverged strands of development in a single repository. Git then adds names to these strands and allows you to query these names remotely. The Bookmarks extension for Mercurial adds local names.
- TortoiseHg is faster and better than the Git equivalent on Windows (due to better usage of the poor Windows filesystem).
- Mercurial feels clean and elegant -- Git involves shell/Perl/Ruby scripts.
- Git is a platform, Mercurial is an application. Git is a versioned filesystem platform that happens to ship with a DVCS app in the box, but as normal for platform apps, it is more complex and has rougher edges than focused apps do. Git's VCS is immensely flexible, and there is a huge depth of non-source-control things you can do with git.
- Mercurial is supported natively on Windows, Git isn't.
- With Mercurial, to start a new branch, you simply clone the repository to another directory and start developing. Then, you pull and merge. With git, you have to explicitly give a name to the new topic branch you want to use, then you start coding using the same directory.
- Git represents commits as snapshots, while Mercurial represents them as diffs. Operations are faster in git, such as switching to another commit, comparing commits, etc.

Mercurial vs Git

Both released in 2005 under the GNU Public License (GPL).

Mercurial is a distributed CVS supporting local copies of a repository and merging of changes into a central version. The command syntax for working with Mercurial is designed to be very simple and easy for users to quickly understand.

Basic commands include:
hg init to create a new repository
hg commit saves changes in the current repository
hg log to see all changes in the repository
hg pull brings all of the changes from another repository into the current repository
hg push sends all changes from the current repository into another repository
hg serve create a web server where collaborators can see the history and pull from it
hg merge to join different lines of history

Changes are tracked linearly over time in a data structure called a revision log (RevlogNG).

Once a change is recorded in the Mercurial history, it is immutable and cannot be removed – except via a rollback which is similarly recorded as a new change.

Git is a distributed CVS supporting local copies of a repository and merging of changes into a central version. Linus Torvalds created Git in 2005 to support the ongoing development of the Linux kernel by widely distributed developers.

The basic Git commands for working in a repository include:
git init / git clone are used to create a new repository or to create a copy of an existing repository
git add adds files and directories to be tracked by Git; new files or directories are not tracked by default
git commit records the current status of objects in the repository into a commit
git status prints information about the current status, including what has deviated from the last commit
git branch is used to manage branches both locally and remotely within the repository
git checkout switches from the current branch to another specified branch and may create a new branch if the one specified does not exist
git merge adds the history of one branch to another branch
git push upload all committed history to a remote copy of the repository
git pull download a remote copy of the current branch and merge any changes to the local version

In addition to these basic commands, Git offers several commands for more specialized operations, such as:
git config
git diff
git reset
git rm
git log
git show
git tag
git remote
git stash

Commits are the basic unit of Git operations and are tracked distinctly by a SHA-1 hash. Git focuses on making a commit a lightweight and cheap operation both computationally and philosophically. Because this approach can, by design, result in numerous commits – especially when merging large branches together – Git provides a capability called rebase that logically collapses all of the commits in a series together into a single commit.

Mercurial and Git are almost interchangeable in function and overall mechanics, but a few important differences stand out:

Implementation – with its more numerous (and more specific) command structure, Git adoption can be a daunting task; especially for teams getting started on a DevOps transition or without developer leaders already familiar with Git work. Mercurial has specifically focused on a command structure that is simpler and ideally more intuitive for developers resulting in not only potentially faster adoption but anecdotally fewer mistakes during development due to errant commands.

Branching – Mercurial creates a branch on change from the tip (Mercurial-speak for the newest branch in the central repository) which supports multiple concurrent changesets without children (heads) which can be merged into a branch or maintained in parallel to track changes side-by-side. In Git branches are intentional – i.e. not created just because something has changed – and very lightweight; working in branches is a part of many teams’ adoption of Git technology – so much so that there are popular terms for the practice referencing Git. Within a branch, Git uses a calculated SHA-1 checksum to distinguish that unique point in branch history.

History – Git offers a few different options for “modifying” the history of a repository; commands such as rollback, cherry-pick, and rebase. Mutable history is an intentional choice designed to work in tandem with the multi-branching nature of Git repositories; for example, using rebase to collapse changes over time into a single logical point in the repository history. Mercurial does not permit such changes to the historical record by design.

Revision Tracking – Mercurial tracks revisions sequentially by natural numbers (1, 2, 3, etc) making it more intuitive for developers to understand the order of operations of changes over time. Git computes a SHA-1 hash at the time of a commit that is a combination of the metadata and the hash of the root object; this method is out of the scope of this article but well worth a read for any teams adopting Git. The resulting SHA means that two (or more) developers viewing a commit in the stream of revisions can be guaranteed to be viewing the same status, which can be especially important for highly distributed teams.

Rollback – As a part of managing the lifecycle of a repository, Git includes a revert command which creates a new commit in a state without any of the changes included as part of the specified historical commit. This action does not modify the history as the original, reverted commit is kept in its place, simply that the effects of that commit are undone. Mercurial offers similar functionality via its backout and revert commands, used in conjunction with a merge.

Community – Git boasts a very active user community – 5418 users and 1940 contributors according to OpenHub – with numerous tools implementing its capabilities and being adopted by teams worldwide – resulting in 1730 open jobs for “Git” according to itjobswatch. Using the same sites, Mercurial reports 979 users and 728 contributors on OpenHub with 44 open jobs on itjobswatch.

|                    | Git                                                                                                                                         | Mercurial                                                                                                                                                                                             |
| :----------------- | :------------------------------------------------------------------------------------------------------------------------------------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Implementation     | Git can take longer for teams to ramp up given its higher level of complexity in commands and repository structure                         | Simpler and more intuitive commands can help teams to quickly ramp up adoption                                                                                                                         |
| Branching          | A branch is a pointer to a commit (SHA)                                                                                                     | A branch is embedded in a commit; branches cannot be renamed or deleted                                                                                                                                |
| History            | Mutable through rollback, cherry-pick, rebase                                                                                               | Immutable beyond rollback                                                                                                                                                                               |
| Revision Tracking  | Each revision unique by calculated SHA-1                                                                                                    | Incremental, numerical index of revision (0, 1, 2, etc)                                                                                                                                                 |
| Rollback           | Supported via revert command; arbitrary via rebase and cherry-pick                                                                           | Supported via backout, revert commands                                                                                                                                                                |
| Community          | Git reports 5418 users and 1940 contributors on OpenHub 1730 jobs are returned by itjobswatch for Git, not counting other derivations like GitOps, GitHub, GitLab, etc. | Mercurial reports 979 users and 728 contributors on OpenHub 44 jobs mention Mercurial on itjobswatch                                                                                     |

There are three major considerations when choosing between Mercurial vs Git:

Ease of adoption – from command syntax and complexity to an incrementing numerical index, many developers find Mercurial easier to learn than Git when first starting out. This is less commonplace today than ten years ago when these CVS solutions were first gaining popularity because many educational curricula for developers now include exposure to versioning as a part of the software development lifecycle (SDLC).

Change tracking – the lightweight branching structure of Git encourages many branches and, by extension, many small bodies of work. This, combined with git rebase, tends to result in more frequent commits without fear of polluting the repository history with unnecessary data points resulting in a lower probability of losing work or of getting stuck at a point in the repository history. Many teams find this approach to repository history more friendly.

Community – Git boasts a large and active user community promoting not only more rapid iterations of capabilities and introduction of new features, but also a greater pool from which new users may draw experience and seek help.

*   Mercurial has a single implementation, while Git has multiple. Mercurial discourages additional implementations to maintain a single source of truth.
*   Mercurial has better hooks, allowing companies to change the behavior of actions without forking.
*   Mercurial had better Windows support than Git for a long time because it doesn't rely on MinGW or a Linux abstraction layer.
*   Mindshare matters; many companies have switched from Mercurial to Git because new employees are more likely to prefer Git or not know Mercurial.
*   Git is rapidly improving on Windows, with Microsoft contributing to its development and performance.
*   Mercurial has an excellent cross-platform GUI called TortoiseHg.
*   Git's command-line interface can be challenging, and a GUI is essential for some users.
*   Some users find Mercurial more forgiving and easier to use than Git, particularly in avoiding accidental data loss.
*   The migration from Mercurial to Git is trivial and retains the full history.
*   Git has better integration with third-party tools and services.
*   Git has become more popular than Mercurial.
*   Mercurial commands are considered to have a cleaner user experience and more sane defaults than Git.

Git is likened to MacGyver due to its flexibility and multitude of individual tools, allowing for extensive configuration and adaptation to various workflows. It's considered suitable for command-line users, large teams, and complex projects.

Mercurial is compared to James Bond, being monolithic and relatively inflexible. It is considered simpler and more Mac-like, emphasizing usability and smoothness. It is favored by those who experiment with new coding methods and prefer not to share code.

Git's dominance is largely attributed to GitHub's rise, which brought a social aspect to programming through forking and collaboration.

Git is considered a poor fit for the typical Microsoft Access developer, who may not be command-line wizards or members of large teams. Mercurial is considered a better option for Access developers due to its lower learning curve, GUI-first nature (especially with TortoiseHg), and safer user experience due to its "never-change-history" philosophy. However, Git has a dominant market share.

The user is moving from Mercurial to Git and is confused by Git's behavior, particularly:

*   History rewriting: Git allows deleting changesets from history, which is not possible in Mercurial.
*   Squashing commits: Squashing a commit resulted in duplication after pulling.
*   Branching: The concepts of "remote branch" and "tracking" are unclear and different from Mercurial's branches (bookmarks).
*   Pushing: Git only pushes the currently selected branch, unlike Mercurial, which pushes everything.
*   Pulling: Git can pull changes from a different branch than the remote, potentially causing problems. There's no "pull everything" or "push everything" functionality like in Mercurial.
*   Cloning: A second clone of a Git repository had fewer changesets and lost branch names.

Git vs. Mercurial: Feature Comparison

Git: Born Out of Necessity
Developed by Linus Torvalds in 2005.
Designed with speed, data integrity, and support for non-linear workflows.
Architecture is a content-addressable filesystem with a mutable index.
Flexibility and power, even if it means a steeper learning curve.
Offers a vast array of commands and options.
Lightweight branching.
Allows for extensive customization through configuration files and hooks.
Generally faster for most operations.
Widespread adoption and has become the de facto standard.

Mercurial: Simplicity and Performance
Created by Matt Mackall around the same time as Git.
Designed with an emphasis on simplicity, performance, and scalability.
Written primarily in Python.
Aims to provide a user-friendly command-line interface.
Simplicity and ease of use.
Straightforward command set and consistent behavior.
Offers multiple ways to handle branching: Named Branches, Bookmarks, and Clone Branching.
Designed to be extensible with a robust extension system.
Performance is comparable, and for certain operations, Mercurial can be faster, especially with large binary files.

Command Comparison:
Initializing a Repository:
Git: git init
Mercurial: hg init
Cloning a Repository:
Git: git clone https://github.com/user/repo.git
Mercurial: hg clone https://www.mercurial-scm.org/repo/hg/
Checking Repository Status:
Git: git status
Mercurial: hg status
Adding Changes:
Git: git add filename.py
Mercurial: hg add filename.py
Committing Changes:
Git: git commit -m "Commit message"
Mercurial: hg commit -m "Commit message"
Viewing Commit History:
Git: git log
Mercurial: hg log
Branching:
Git: git branch new-feature; git checkout new-feature
Mercurial: hg branch new-feature
Merging:
Git: git checkout main; git merge new-feature
Mercurial: hg update main; hg merge new-feature
Pushing Changes to Remote Repository:
Git: git push origin main
Mercurial: hg push

Git’s Dominance:
Widespread Adoption: Git has become the de facto standard in the industry.
GitHub: The largest code host, which has significantly boosted Git’s popularity.
Used By: Linux kernel, Android, Ruby on Rails, and many more.

Mercurial’s Niche:
Steady User Base: While not as popular as Git, Mercurial has a dedicated community.
Used By: Some large projects like Facebook (historically), though many have migrated to Git.
Bitbucket: Originally supported both Git and Mercurial but dropped Mercurial support in 2020.

Tooling and Ecosystem:
Git’s Ecosystem:
Hosting Services: GitHub, GitLab, Bitbucket, and others.
Integration: Extensive support in IDEs, CI/CD pipelines, and deployment tools.
Community: Large and active, with numerous tutorials, plugins, and third-party tools.
Mercurial’s Ecosystem:
Hosting Services: Previously Bitbucket, now more limited options.
Integration: Supported by several IDEs and tools, but not as extensively as Git.
Community: Smaller but passionate, with resources and extensions available.

Choose Git if:
You want the industry-standard tool with extensive community support.
You require advanced features and extensive customization.
You plan to use platforms like GitHub or GitLab.

Choose Mercurial if:
You prefer a simpler command set and a more straightforward workflow.
You value a consistent and user-friendly interface.
Your project benefits from Mercurial’s specific features or extensions.

Git vs Mercurial: Feature Comparison

**Mercurial**
*   **Developer:** Matt Mackall (April 19, 2005)
*   **Languages:** Python, C, Rust
*   **Supported Platforms:** Windows, UNIX-like systems (FreeBSD, macOS, Linux)
*   **Network Protocols:** HTTP, Custom over SSH, Email Bundles (with standard plugin)
*   **Version History:** Does not allow history changes by default
*   **Branching:** Provides branching but not as robust as Git
*   **Complexity:** Simple and straightforward commands
*   **Staging:** Does not support staging
*   **User Interface:** Command-line interface with optional GUIs
*   **Workflow Models:** Supports various models, typically simple workflows
*   **Popularity:** Less popular but favored for simplicity
*   **Documentation:** Good documentation, less extensive community contributions
*   **Large File Support:** Extensions available for large files
*   **Learning Curve:** Easier to learn due to simplicity
*   **Integration with CI/CD:** Supported but less integrated compared to Git

**Git**

*   **Developer:** Linus Torvalds (April 7, 2005)
*   **Languages:** C, Perl, Python
*   **Supported Platforms:** Windows, Linux, macOS, Solaris
*   **Network Protocols:** Custom over SSH, Rsync, HTTP
*   **Version History:** Allows developers to change version history
*   **Branching:** Strong branching and merging capabilities
*   **Complexity:** More complex due to a richer set of commands
*   **Staging:** Supports staging
*   **User Interface:** Command-line interface with numerous GUI options
*   **Workflow Models:** Supports a wide range of workflows, including Gitflow
*   **Popularity:** Highly popular, widely adopted in open-source and enterprise
*   **Documentation:** Extensive documentation with large community contributions
*   **Large File Support:** Git LFS (Large File Storage) supports large files
*   **Learning Curve:** Steeper learning curve due to more features and commands
*   **Integration with CI/CD:** Highly integrated with many CI/CD tools

**Key Differences Summarized:**

*   **Mercurial:** Known for simplicity and ease of use. Favored where ease of use is crucial.
*   **Git:** Offers more advanced features and flexibility. Preferred for large-scale and collaborative projects.
*   Git’s advanced branching and merging capabilities often make it more suitable for large-scale, collaborative projects.

Git vs. Mercurial: Feature Comparison

*   **Storage Format:** Git stores every commit/file in a simple hashed document repository, where the identity of each object is a hash of the contents, making everything immutable. Mercurial uses append-only logs, optimizing for disk seeks.
*   **History Manipulation:** Git allows rewriting history to craft commit logs, making it easier to review complex pull requests. Mercurial makes it difficult to retroactively tweak commits
*   **Branching:** Git's branching is considered a "killer feature." Mercurial recommends cloning a repository for each branch or uses the Bookmark extension. Git uses namespaces that make it clear which branch is local and which is remote.
*   **Staging:** Git uses an "index" or staging area where changes must pass through before being committed, allowing for selective addition of hunks/snippets from a file. Mercurial has a Record extension to imitate this behavior.
*   **Rename Tracking:** Git does not track renames but detects lines moved between files using the `-C` option in `git blame`. Mercurial does not have an equivalent extension.
*   **Safety:** Git keeps track of every change in the reflog, storing references to unique and immutable commits.

Git is a widely used distributed version control system (DVCS) used for source code management. It tracks changes in code and documents, allowing users to revert to previous versions. Git uses a branching system to manage multiple versions of the code. Some basic git commands are: git config, git init, git clone, git add, git commit, git diff, git reset, git status, git rm. Commits are the fundamental unit of Git operations and are distinguished by an SHA-1 hash.

Advantages of Git:
*   Versatility: Suitable for projects ranging from small personal projects to large enterprise projects.
*   Easy Branching and Merging: Simplifies the management of multiple code versions.
*   Comprehensive Tracking: Provides tools for tracking changes, including versioning, tagging, and history logs.
*   Distributed Architecture: Each user has a complete copy of the repository, enabling offline work, faster performance, and better security.

Mercurial is a free distributed version control system used to organize and track changes across projects. The command syntax is designed to be straightforward. Some fundamental commands are: hg init, hg log, hg clone, hg pull, hg push, hg commit. It uses a revision log data structure (RevlogNG) to monitor changes. Once a change is recorded in Mercurial, it is immutable unless a rollback is performed.

Advantages of Mercurial:

*   Easy to Use: Straightforward interface, suitable for users new to version control.
*   Speed: Fast performance, suitable for large repositories.
*   Scalability: Designed to scale well for large projects.
*   Flexibility: Can be tailored to specific needs.

Key Differences:

| Feature           | Git                                                                                                           | Mercurial                                                                 |
| ----------------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| Implementation    | Commands and repository structure can be complex.                                                             | Simpler and more intuitive commands.                                        |
| Branching         | Allows creating, removing, and modifying branches without impacting previous commits.                          | Requires changes in a complete set of a file in a repository.              |
| History           | Rollback, cherry-pick, and rebase are methods for modifying data.                                           | Immutable beyond rollback.                                                |
| Revision Tracking | Uses a computed SHA-1 hash for each revision.                                                                | Uses an incremental, numerical revision index (0, 1, 2, etc.).            |
| Rollback          | Supports Revert command, rebase, and cherry-pick commands are optional.                                      | Backout and revert commands are available.                                |
| Speed             | Slower than Mercurial.                                                                                        | Somewhat faster than Git.                                                  |
| Support           | Linux heritage.                                                                                               | Based on Python and cares about Windows users more.                        |
| Complexity        | More complex.                                                                                                 | Less complex than Git.                                                     |
| Community Support | Larger and more active community.                                                                              | Smaller community, potentially less support and fewer resources for users. |

*   **Repository Structure:**
    *   Git: Object database with blobs (file content), trees (directory structure), commits (authorship, snapshot pointer), and tags (references to other objects). Uses loose and packed formats for storage. Requires periodic maintenance with `git gc`.
    *   Mercurial: Stores file history in filelogs, uses a flat manifest for directory structure, and a changelog for revisions. Uses a transaction journal for atomicity.
*   **Merges:**
    *   Mercurial: Doesn't allow octopus merges (more than two parents).
    *   Git: Allows octopus merges.
*   **Tags:**
    *   Mercurial: Uses a versioned `.hgtags` file for repository-wide tags and `.hg/localtags` for local tags. Requires committing changes to the `.hgtags` file.
    *   Git: Tags are references in the `refs/tags/` namespace. Automatically fetched/pushed by default. Supports lightweight and annotated tags.
*   **Branches:**
    *   Mercurial: Uses anonymous heads as the basic workflow. Supports bookmarks (local, transferable since version 1.6) and named branches (embedded in commits).
    *   Git: Uses lightweight named branches and remote-tracking branches. Current branch is referenced by the `HEAD` ref.
*   **Revision Naming and Ranges:**
    *   Mercurial: Uses local revision numbers and relative revisions.
    *   Git: Refers to revisions relative to the branch tip; revision ranges are topological.
*   **Renaming:**
    *   Mercurial: Uses rename tracking.
    *   Git: Uses rename detection.
*   **Network Protocols:**
    *   Mercurial: Supports SSH and HTTP "smart" protocols, and static HTTP protocol.
    *   Git: Supports SSH, HTTP and GIT "smart" protocols, and HTTP(S) "dumb" protocol.
*   **Extensibility:**
    *   Mercurial: Uses extensions (plugins) with an established API.
    *   Git: Has scriptability and established formats.
*   **Branches (Pushing):**
    *   Mercurial: Pushes all heads by default unless a specific branch tip is specified.
    *   Git: Pushes matching branches by default or uses options like `--all` or specifying a single branch.
*   **Branches (Fetching):**
    *   Mercurial: Fetches all heads by default, but a specific branch can be specified. Stores fetched tips as unnamed heads.
    *   Git: Fetches all branches from the remote repository (refs/heads/) and stores them in the refs/remotes/ namespace. Can fetch a single branch.

Git vs Mercurial: What are the differences? Git and Mercurial are both distributed version control systems (DVCS) that offer functionalities for managing source code. Here are the key differences between Git and Mercurial:

Architecture: Git uses a content-addressable filesystem, where each file is identified by its content hash, and commits are represented as directed acyclic graphs. On the other hand, Mercurial uses a simpler model with changesets that directly track changes to files. This architectural difference impacts how they handle branching, merging, and storage efficiency.

Performance: Git is known for its exceptional performance, especially when it comes to handling large repositories and performing operations like branching and merging. Mercurial, while still performant, may be slightly slower in certain operations due to its different architecture and algorithms.

Learning Curve: Git has a steeper learning curve compared to Mercurial. Git's command-line interface and terminology can be initially challenging for new users. Mercurial, on the other hand, aims for a simpler and more intuitive command set, making it more approachable for beginners or those transitioning from other version control systems.

Ecosystem and Adoption: Git has gained widespread adoption and has a larger ecosystem compared to Mercurial. It is the de facto standard for version control in many open-source projects and industry workflows. Git has an extensive collection of third-party tools, integrations, and hosting platforms like GitHub, GitLab, and Bitbucket. While Mercurial also has its ecosystem and hosting platforms like Bitbucket, it has a smaller community and user base overall.

Windows Compatibility: Git has native support for Windows, making it a popular choice for developers working in Windows environments. Mercurial also supports Windows, but historically, Git has provided better compatibility and performance on this platform.

In summary, Git's widespread adoption and robust tooling make it a popular choice for many developers, while Mercurial's simpler command set and intuitive design may appeal to beginners or those looking for an alternative version control system.

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

Mercurial is dedicated to speed and efficiency with a sane user interface. It is written in Python. Mercurial's implementation and data structures are designed to be fast. You can generate diffs between revisions, or jump back in time within seconds.

Pros of Git: Distributed version control system, Efficient branching and merging, Fast, Open source, Better than svn, Great command-line application, Simple, Free, Easy to use, Does not require server, Small & Fast, Feature based workflow, Staging Area, Most wide-spread VSC, Disposable Experimentation, Role-based codelines, Frictionless Context Switching, Data Assurance, Efficient, Easy branching and merging, Github integration, Compatible, Flexible, Team Integration, Easy, Light, Fast, scalable, distributed revision control system, Rebase supported natively; reflog; access to plumbing, Flexible, easy, Safe, and fast, CLI is great, but the GUI tools are awesome

Pros of Mercurial: A lot easier to extend than git, Easy-to-grasp system with nice tools, Works on windows natively without cygwin nonsense, Written in python, Free, Fast, Better than Git, Best GUI, Better than svn, Hg inc, Good user experience, TortoiseHg - Unified free gui for all platforms, Consistent UI, Easy-to-use, Native support to all platforms

Cons of Git: Hard to learn, Inconsistent command line interface, Easy to lose uncommitted work, Worst documentation ever possibly made, Awful merge handling, Unexistent preventive security flows, Rebase hell, Ironically even die-hard supporters screw up badly, When --force is disabled, cannot rebase, Doesn't scale for big data

Cons of Mercurial: Track single upstream only, Does not distinguish between local and remote head

What companies use Git? Shopify Netflix Udemy Robinhood reddit CRED Delivery Hero SE

What companies use Mercurial? Bitbucket Deveo Yomali Eyereturn Marketing Jitbit IVS CrossKnowleddge

Mercurial vs. Git: why Mercurial?

There are two major distributed version control systems in widespread use today: Mercurial (Hg) and Git.

Mercurial’s CLI is full-featured, stable, and elegant. It follows the UNIX philosophy: “each command should do one thing and do it well.” Git’s CLI is designed to be extremely flexible. Each command has many options that can change its behavior.

Mercurial tries to be helpful by anticipating some of the more common aliases for commands and just making them work. Git simply gives you a git mv command.

Mercurial’s CLI is also quite similar to Subversion’s, which can help ease the transition between the two tools.

Mercurial Git
hg add git add
hg blame git blame
hg cat git show
hg clone git clone
hg commit ; hg push git commit -a ; git push
hg remove git rm
hg diff git diff, git diff –cached
hg help git help
hg log git log
hg revert git checkout -f
hg status git status
hg pull –update git pull
hg move/rename git mv

Mercurial’s philosophy is that “history is permanent and sacred.” Core Mercurial includes only one single command that can alter history: hg rollback. Git, on the other hand, lets you play fast and loose with your project’s history. Commands like git rebase –interactive let you rewrite history, possibly discarding data along the way.

For the times when you do need to rewrite history in Mercurial, you can turn to extensions like collapse, histedit and MQ.

Several third-party GUIs have been created to make working with Mercurial easier. One of the tools out there is Sourcetree, a free Git and Mercurial Mac client offered by Atlassian. TortoiseHg is another available tool — a shell extension for Windows, Linux and OS X that provides a mature, stable GUI to work with Mercurial. If you use the popular Eclipse IDE for your development, there is a plugin called MercurialEclipse that integrates Mercurial into Eclipse.

With Mercurial, Windows support is a first-class feature. Git, on the other hand, does not provide support for Windows in its core code. There is a project called msysgit that adds compatibility for Windows. However, it is commonly reported to be slower than Git on Linux, and the fact that it is a completely separate project says something about Git’s attitude toward Windows use.

The maintainer (and original author) of Mercurial, Matt Mackall, is a strong proponent of backwards compatibility, which is important when you’re choosing a version control system that you plan to rely on for a long time.

Mercurial knows that everyone is going to have different needs, so it provides several ways to extend its functionality without changing the core code.

Git and Mercurial are both free software tools for distributed revision control and software source code management. Both were started at approximately the same time with similar aims, spurred by Bitmover withdrawing the free version of BitKeeper in April 2005.

Git was created by Linus Torvalds for Linux kernel development, emphasizing speed, beginning April 3, 2005. Mercurial was created by Matt Mackall as a BitKeeper replacement, announced April 19, 2005. The Linux kernel project chose Git, but Mercurial is used by many other projects.

Here's a comparison chart of Git and Mercurial:

| Feature                     | Git               | Mercurial          |
|------------------------------|-------------------|----------------------|
| Built-in web server           | No                | Yes                  |
| Pre/post-event hooks         | Yes               | Yes                  |
| End of line conversions      | Yes               | Yes                  |
| Tags                        | Yes               | Yes                  |
| International support        | Partial           | Yes                  |
| File renames                 | Yes (implicit)    | Yes                  |
| Merge file renames           | Yes               | Yes                  |
| Symbolic links               | Yes               | Yes                  |
| Open source                  | Yes               | Yes                  |
| Signed Revisions             | Yes               | Yes                  |
| Revision IDs                | SHA-1 hashes      | Numbers, SHA-1 hashes|
| Atomic commits               | Yes               | Yes                  |
| History model                | Snapshot          | Changeset            |
| Repository size              | O(patch)          | O(patch)             |
| Concurrency model            | Merge             | Merge                |
| Operating Systems            | Unix-like, Windows, Mac OS X | Unix-like, Windows, Mac OS X |
| Staging area                 | Yes               | No                   |
| Externals branch             | Yes               | No                   |
| Shallow checkout / clone     | Yes               | No                   |
| File/dir name tracking       | Rename detection  | Rename tracking      |
| Subdirectory checkout/clone  | No                | No                   |
| Repository model             | Distributed       | Distributed          |
| Permission keeping           | Execution bit only| Execution bit only   |
| Network protocols            | custom, custom over ssh, rsync, HTTP, email bundles | HTTP, custom over ssh, email bundles (with standard plugin) |
| Developed by                 | Junio Hamano, Linus Torvalds | Matt Mackall         |
| Maintained by                | Junio Hamano      | Matt Mackall         |
| Written in                   | C, Bourne Shell, Perl | Python and C         |
| Merge tracking               | Yes               | Yes                  |
| Bug Tracker integration      | No                | Trac (via plugin)    |
| License                      | GPL v2            | GPL v2               |
| Website                      | git-scm.com       | www.selenic.com/mercurial |

Git is a free distributed revision control system emphasizing speed, initially created by Linus Torvalds for Linux kernel development. Mercurial is a cross-platform, distributed revision control tool mainly implemented in Python, with a C binary diff implementation.

Mercurial's design goals include high performance, scalability, serverless fully distributed collaborative development, robust handling of text and binary files, and advanced branching/merging, while remaining simple. It includes an integrated web interface. Linus Torvalds' key design goals for Git were speed and efficiency, with strong safeguards against corruption.

Several high-profile projects use Git, including the Linux kernel, Perl, Samba, X.org Server, Qt, OLPC, Ruby on Rails, VLC, YUI, Merb, Wine, SWI Prolog, GNOME, GStreamer, DragonFly BSD, and Android. Projects using Mercurial include Adblock Plus, Aldrin, Audacious, Dovecot IMAP server, GNU Octave, NxOS, Nuxeo, Growl, MoinMoin, Mozilla, Mutt, Netbeans, OpenJDK, Python, SAGE, Sun Microsystem's OpenSolaris, and Oracle's Btrfs.

Mercurial was initially written for Linux but has been ported to Windows, Mac OS X, and other Unix-like systems and is primarily a command line program. Git is primarily developed on Linux but runs on other Unix-like OSes, including BSD and Solaris, and also runs on Windows (msysgit).

Mercurial operations are invoked via the `hg` driver program. GUI interfaces for Mercurial include Hgk (Tcl/Tk), hgview (Python), (h)gct (Qt), and Meld. The convert extension allows importing from CVS, Darcs, git, GNU Arch, Monotone, and Subversion repositories. Netbeans IDE, TortoiseHg, VisualHG, and Mercurial Eclipse support Mercurial.

Alternatives for Git GUIs include git-cvsserver, Eclipse IDE-based Git client (egit), NetBeans IDE support (under development), TortoiseGit, and Git Extensions.

Git vs Mercurial

Mercurial and Git both are two quite similar and most popular distributed version control systems. Their strengths and weaknesses make them ideal for different use cases. Both tools use a directed acyclic graph to store history.

Mercurial is a distributed source control management tool. It is free and open-source. It can handle projects of any size and offers an easy and intuitive interface.

Today, Git has more than 31 million users and is owned by Microsoft. Since the last decade, the Git has become the standard for most development projects.

Mercurial still has a handful tool of large development organizations. Some software development giants like Facebook, Mozilla, and World Wide Web Consortium are using it. But it only has approx 2 % of the VCS market share. Comparatively, Git has covered more than 80% market share.

Both version control systems, i.e., Mercurial and Git are distributed version control systems (DVCS).

GitMercurial
Git is a little bit of complex than Mercurial.Mercurial is simpler than Git.
No VCS are entirely secured, but Git offers many functions to enhance safety.Mercurial may be safer for fresher. It has more security features.
Git has a powerful and effective branching model. Branching in Git is better than Branching in Mercurial.Branching in Mercurial doesn't refer the same meaning as in Git.
Git supports the staging area, which is known as the index file.There is no index or staging area before the commit in Mercurial.
The most significant benefit with Git is that it has become an industry-standard, which means more developers are familiar with it.Mercurial's significant benefit is that it's easy to learn and use, which is useful for less-technical content contributors.
Git needs periodic maintenance for repositories.It does not require any maintenance.
It holds Linux heritage.It is python based.
Git is slightly slower than Mercurial.It is faster than Git.
Git supports the unlimited number of parents.Mercurial allows only two parents.

Git is largely implemented in C, whilst Hg is implemented entirely (or almost entirely) in Python.

Git allows direct mutable access to the contents of the repository and the history, whereas the latter allows access to the history but only on a read-only basis.

Git stores all of its metadata inside a .git folder at the top level of the repository. None of the subfolders have metadata inside them.
Mercurial has a .hg folder at the top level of a Mercurial repository. Unlike Git, instead of a fixed layout, Hg mirrors the repository's layout under the store/data directory.

In Mercurial, branches and tags are an intrinsic property of the repository, whereas in Git they are an extrinsic property of the repository tree.

Mercurial stores its deltas in revlog formats, which are essentially a sequence of diffs for a particular file. Git stores its deltas in a pack file, which stores diffs over a set of files.

Git's bisect, which allows a tree to be iteratively bisected to determine where a bad change was introduced, has subsequently been added to Mercurial. Similarly, Git's general rebasing has been ported to Mercurial in the form of the patch queue. From the other direction, Mercurial's bundle has been ported to Git.

Git's rebase allows a sequence of changes to be replayed onto a different branch, or (in the case of an interactive rebase) to be re-ordered.

Git also has a cherry-pick concept, which permits an out-of-order commit to be copied from one branch to another. (Mercurial has a plugin transplant which is a recent addition.)

Git index A significant difference between Mercurial and Git is Git's index. This permits a work-in-progress to be built up over multiple (add) operations, prior to committing the operation.

Git Reflog Since Git effectively stores where you are as a commit hash, and that commit hash moves as you update a branch, it can also record where you have been. The git reflog stores a list of places for which HEAD has been used over the past iterations of the (local) repository.

Git vs. Mercurial for Version Control:

- Git is a version control software developed to manage source codebases.
- Mercurial is another version control system used by developers at Facebook, Mozilla, the W3C, and the PyPy project.
- Conceptually, Mercurial and Git work the same way, both using a graph of changes made to a codebase.
- Mercurial's core command set for common use cases is smaller and easier to master than Git's.
- Branching in Mercurial can be done in a few ways: cloning the repository, bookmarking changesets, using named branches, or creating anonymous branches.
- Mercurial offers an extension mechanism for integrating third-party code directly, while Git typically uses standalone programs.
- Mercurial has the ability to sync with a Git repository, useful for transitioning codebases.

Git vs. Mercurial: Which DVCS to choose?

Git and Mercurial are two distributed version control systems (DVCSs). Both will give you the tools to track changes to your code, and collaborate remotely with others on development.

Git offers more granular control at the cost of requiring a little more user input, while Mercurial makes its default behavior what most users want ~80% of the time, at the cost of some granularity of control.
Git provides the tools to rewrite history, if necessary, and assumes that if you’re using them, you know what you’re doing. Mercurial enforces the sanctity of history by default.
Git favors using branches for any separate work or idea. Mercurial tends to consider branches more permanent.

Git generally tends to favor grouping similar actions into one subcommand, with its behavior modified by additional arguments or flags. Mercurial tends to follow the idea that each command does one thing.
Mercurial has a system in place for adding extensions, and which extensions are enabled can vary by repo. While Git can be extended with new subcommands, there’s not a system in place to manage them.

Which one is used by the group you are or will be working with?
Which one is most commonly used in your field?
Available remotes: Git has GitHub and Bitbucket, Mercurial, since July 2020, has no ready-to-go solution (though you can host your own.)
Will you want to assign DOIs to your code? This is possible via GitHub + Zenodo, but there’s no ready-to-go solution for Mercurial.

Granularity of control
Commands in Mercurial often have a default behavior that does what you want most of the time, but makes it more difficult to exercise fine control over exactly what you want to do when the default isn’t ideal. Git tends to favor the reverse.

Making commits: In Mercurial, when you commit changes, hg commit by default assumes you want to commit all changes to any tracked file. In Git, you either have to add an extra flag to get that behavior (git commit -a) or add changes to commit first with git add then make the commit.

Pushing to remotes: When you do hg push, Mercurial assumes you want to push all heads to the remote named “default” in the repo’s config file. There’s no way to change this default. Git requires you to specify the remote (and branch) the first time you push, unless the repo was cloned from a remote.

Rewriting history
Git assumes that if you need to do so, you have a good reason, and provides commands like reset, rebase, and filter-branch to do so. You use these commands at your own risk. Mercurial, on the other hand, doesn’t provide any equivalent to these commands (without enabling some extensions). Essentially, it enforces best practice (which is to not rewrite history).

Branching philosophy
In Git, branches can be created and deleted as needed. The branch a particular commit is made on is not recorded, and once deleted, the reference for a branch is fully gone. In Mercurial, the branch a commit is made on is recorded and branches cannot be deleted, only closed.

Which one is used by your immediate colleagues?
Which one is most commonly used in your field?

Available remotes
Once it comes time to share your code repository, either just between different computers you own, among others you work with, or as part of a publication, you’ll need to start working with a remote repository. The easiest way to do so is to use a website like GitHub or BitBucket. Since July 2020, both of these only support Git. If you want to have a Mercurial remote, you’ll likely have to set one up yourself.

Assigning a DOI to your code
This can be considered a feature of the available remotes, but as of July 2019, if you want to assign a DOI to a release of your code, you’ll need to work with GitHub, as BitBucket doesn’t yet support this.

Conclusions
Given that the major hosting websites (GitHub and BitBucket) now only support Git, unless you’re working in a group that already has lots of Mercurial repos, it’s probably better to learn Git rather than Mercurial.

Git and Mercurial are both distributed and open-source version control systems (VCS).

**Similarities:**

*   Both are distributed VCS, meaning each developer has a local copy of the entire codebase, including history and branches, without relying on a central server.
*   Both are open-source, free to use and modify, and have large communities.

**Differences:**

*   **Data Model:** Git uses a snapshot-based model (captures the entire codebase at a point in time), while Mercurial uses a changeset-based model (reflects modifications from the preceding commit).
*   **Staging Area:** Git has a staging area to select and review changes before committing; Mercurial does not.
*   **Branching:** Git has a more complex and powerful branching system with lightweight references, while Mercurial has a simpler branching system with permanent labels.
*   **Commands:** Git has more commands and options, making it more flexible but harder to learn. Mercurial has fewer commands, making it more consistent but less customizable.

**Installation:**

Both Git and Mercurial are available for various operating systems (Windows, Linux, Mac OS) and can be installed from their official websites or using package managers. GUIs and IDEs like SourceTree, TortoiseHg, Visual Studio Code, and Eclipse also support them.

**Basic Commands:**

*   **Initialize a repository:** `git init` vs. `hg init`
*   **Clone a repository:** `git clone URL` vs. `hg clone URL`
*   **Commit changes:** `git add FILE` and `git commit -m "MESSAGE"` vs. `hg commit -m "MESSAGE"`
*   **Push changes:** `git push REMOTE BRANCH` vs. `hg push REMOTE`
*   **Pull changes:** `git pull REMOTE BRANCH` vs. `hg pull REMOTE`
*   **View history:** `git log` vs `hg log`
*   **Switch to a specific commit:** `git checkout COMMIT` vs `hg update COMMIT`
*   **List, create, or delete branches:** `git branch` vs `hg branch`
*   **Merge a branch:** `git merge BRANCH` vs `hg merge BRANCH`
*   **Reapply a branch:** `git rebase BRANCH` vs `hg rebase -d BRANCH`

- In January 2011, a performance comparison between Mercurial and Git server performance concluded that Mercurial gives a steadier performance, but Git is faster on average.
- Performance shouldn't be the deciding factor between Git and Mercurial, as both are good.
- Git excels in space efficiency if the same content exists in many different paths over time due to its model.
- Key performance aspects of a DVCS are merge speed, publication workflow speed, integration speed with IDEs and other tools, and setup speed for a centralized repository.
- Raw performance of basic operations is less relevant, but understand the limits of a DVCS: avoid putting everything into a single repo. Organize into modules.
- Microsoft uses Git for its entire Windows codebase (3.5M files, 300GB) with GVFS (Git Virtual File System) for dynamically downloading portions needed.
- Network clones/pushes/pulls take longer than commits.
- A 2011 benchmark showed SVN slower than Git, Mercurial, and Bazaar. Git was the fastest, but the difference between Git and Mercurial was small (around 1.4 seconds).

Google's analysis compared Git with Mercurial to choose what to use in Google Code.

Learning Curve: Git has a steeper learning curve than Mercurial because Git has more commands and options. Mercurial's documentation is more complete and easier for novices. Mercurial's terminology and commands are closer to Subversion and CVS.

Windows Support: The official way to run Git under Windows used to be with cygwin. A MinGw based port of Git was gaining popularity but was a little sluggish. Mercurial is Python-based and runs cleanly under Windows, Linux, and Mac OS X. Nowadays msysGit works perfectly fine.

Maintenance: Git requires periodic maintenance of repositories (i.e. git-gc), but Mercurial does not.

History is Sacred: `git-push –force` can result in revisions becoming lost in the remote repository. Mercurial's repository is structured more as an ever-growing collection of immutable objects.

Repository structure: Mercurial doesn’t allow octopus merges (with more than two parents), nor tagging non-commit objects.

Tags: Mercurial uses versioned .hgtags file with special rules for per-repository tags, and has also support for local tags in .hg/localtags; in Git tags are refs residing in refs/tags/ namespace, and by default are autofollowed on fetching and require explicit pushing.

Branches: In Mercurial basic workflow is based on anonymous heads; Git uses lightweight named branches, and has special kind of branches (remote-tracking branches) that follow branches in remote repository.

Revision naming and ranges: Mercurial provides revision numbers, local to repository, and bases relative revisions (counting from tip, i.e. current branch) and revision ranges on this local numbering; Git provides a way to refer to revision relative to branch tip, and revision ranges are topological (based on graph of revisions)

Mercurial uses rename tracking, while Git uses rename detection to deal with file renames

Network: Mercurial supports SSH and HTTP “smart” protocols; modern Git supports SSH, HTTP and GIT “smart” protocols, and HTTP(S) “dumb” protocol. Both have support for bundles files for off-line transport.

Mercurial uses extensions (plugins) and established API; Git has scriptability and established formats.

Git vs Mercurial: Empirical Evidence of Popularity

- Stack Overflow: Git has significantly more hits than Mercurial.
- Google Trends: Git has a higher ratio compared to Mercurial.
- Ohloh: Git has a significantly higher number of repositories compared to Mercurial.
- Eclipse Community Survey: Git usage is significantly higher than Mercurial.

Reasons companies might prefer Mercurial:
- Mercurial is more polished and easier to approach.
- Mercurial experience is better than Git on Windows.

Git is the hands-down winner in terms of open-source software.

Popularity is an excellent reason to choose a version control system because of the distributed nature of the tool. The network externality effects give the more popular tool vastly more value if you plan to contribute to projects with other participants.

Choose Git when a project or community you want to contribute to uses Git, and use Mercurial when they use Mercurial.

Performance comparison of Git, Mercurial, Bazaar, Darcs, Monotone, and SVK

Git stores snapshots of the repository with each commit, while Mercurial balances snapshots and delta storage. Git's architecture prioritizes speed, but as projects grow very large, with many commits and authors, it can become slow. Facebook, with 62 million lines of code, found Git slow and improved Mercurial's performance. Mercurial uses a revlog storage format with index and data files, storing either binary deltas or complete snapshots of files. Mercurial's analysis operations are faster, and its scaling is better due to its storage system. Mercurial has become a viable alternative to Git, especially in recent years, due to advancements made by Facebook devs.

- Question about using hg or git for a repository of about 5gb
- A repository with 5 GB is large, but not outrageously large.
- OpenOffice repository has a history of 2.0 GB (about 270,000 changesets) and a working copy of 2.3 GB and Mercurial runs okay on that size
- `hg status` on the OpenOffice repo takes 0.63s user 0.26s system 99% cpu 0.886 total with a warm cache
- With a cold cache is takes 2.4 sec
- There are 69,000 files in the working copy.
- In general, you can expect both Git and Mercurial to slow down as the repository grows.
- `hg status` is obviously O(number of files in the working copy)
- `hg commit` has the complexity of `hg status` plus O(number of changed files)
- `hg cat` has O(1) complexity in the number of files and number of changesets — Mercurial can reconstruct any version of a file in constant time.
- facebook recently sent a post about their git repo slowing down because all their "apps" are in one repo

- Git has a terrible UI, but Mercurial's UI is also considered terrible by some.
- Git's data model is considered more sane by some, while others find it unnecessarily complex. Mercurial's data model is considered more complicated with more pointers.
- Git's speed was a significant factor in its adoption.
- Git's popularity was also boosted by the Linux kernel development using it, Linus Torvalds creating it, and the existence of GitHub.
- Git doesn't handle file copies and renames well, using heuristics that sometimes fail. Mercurial handles renames as a first-class concept.
- Git has scaling problems with large repos, particularly those with many files.
- Git's scaling issues relate to centralization and file count rather than raw size. Pushing changes to a central repo requires including upstream commits, leading to contention.
- Some Git algorithms scale linearly with the number of server branches or files, causing performance issues.
- Binary files don't compress or deduplicate well in Git, slowing down pull and clone operations.
- Git is difficult for beginners, but day-to-day development only requires understanding a few commands.
- Git's data model brings speed advantages.
- Git's performance was a key factor in its adoption.
- Git won over Mercurial partly due to Github's popularity.
- Git was already gaining traction before GitHub existed.

Subversion vs. GIT vs. Mercurial. vs. Bazaar
I write python scripts. Looking for a solution to sync them between my windows desktop (use Komodo IDE) and Linux Laptop (use VIM). I want to be able to have them backed up on a server that will allow me to share the scripts with others. I know of the four solutions I mentioned in the title. I've used subversion in the past and was happy with it. Wondering if any of the other three would be better for what I need to do. Thanks!

*   Mercurial used to have performance issues with many commits and slow merging.
*   Git is more efficient with large repositories than Mercurial.
*   Mercurial has historically performed better than Git on Windows due to Git's slow lstat calls on Windows. Mercurial used an additional cache file, which was slower on Linux with big repos but faster on Windows.
*   Git's main target is Linux.
*   Git has a feature called "octopus merge" (merging multiple branches at the same time) which is used by kernel maintainers. This feature is impossible to add in Mercurial as it does not allow more than two commit parents.

OSX v10.4.11
Python 2.5
mercurial v1.2.1
git v1.6.3.1

clone
git clone git://code.python.org/python/trunk 1:29
hg clone http://code.python.org/hg/trunk 3:02

space (du -hs)
git 137M
hg 175M

log specific file
git log README 1.68
hg log README 0.65

log latest 10 commits
git log -10 0.02
hg log -l 10 0.52

status
git status 0.11
hg status 0.27

list branches
git branch 0.02
hg branches 0.43

get changes from remote
git fetch 0.08
hg pull 0.52

diff
git diff 0.04
hg diff 0.26

going back 500 commits
git checkout HEAD~500 1.5
hg checkout -r -501 4.5

- Facebook's main source repository is enormous, many times larger than the Linux kernel.
- Two years ago, Facebook saw their repository continue to grow at a staggering rate.
- They looked at available options for source control and found none that were both fast and easy to use at scale.
- Facebook decided to take an existing system and make it scale, choosing to improve Mercurial over Git.
- After much deliberation, they concluded that Git’s internals would be difficult to work with for an ambitious scaling project. Instead, they chose to improve Mercurial.
- Mercurial is a distributed source control system similar to Git, with many equivalent features, written mostly in clean, modular Python (with some native code for hot paths), making it deeply extensible.
- When Facebook first started working on Mercurial, they found that it was slower than Git in several notable areas.
- To narrow this performance gap, they've contributed over 500 patches to Mercurial over the last year and a half.
- For a repository as large as Facebook's, a major bottleneck is simply finding out what files have changed.
- Git examines every file and naturally becomes slower and slower as the number of files increases.
- Facebook solved the file change bottleneck by monitoring the file system for changes using Watchman.
- For Facebook's repository, enabling Watchman integration has made Mercurial’s status command more than 5x faster than Git’s status command.
- The rate of commits and the sheer size of Facebook's history also pose challenges.
- They created the remotefilelog extension for Mercurial to solve the problem of slow pulls. This extension changes the clone and pull commands to download only the commit metadata, while omitting all file changes that account for the bulk of the download.
- Enabling the remotefilelog extension for employees at Facebook has made Mercurial clones and pulls 10x faster, bringing them down from minutes to seconds.
- The remotefilelog extension allowed Facebook to shift most of the request traffic to memcache, which reduced the Mercurial server’s network load by more than 10x.

Mercurial vs Git: Scaling and Architecture

TL; DR — A long, somewhat technical post on why mercurial is better at scaling that git. Some history, too.

Everywhere I look, I see people using git.

Now, let me make it clear that despite all appearances to the contrary, I am in no way criticising git or GitHub. In fact, I love git.

Linus Torvalds created git.

Both were adamant on creating a perfect — at least their vision of perfect — DVCS. Both had a vision of perfection. And, almost ten years later, we have both of them to thank for two absolutely fantastic version control systems — systems so good that they blew away all the competition, commercial or otherwise.

Linus decided to go with C, for reasons of speed, I should think. Matt, however, saw another language, one that was maybe not quite so fast as C, but with tremendous potential.

He decided to develop in Python.

First things first — mercurial is easy for beginners. This, quite mistakenly, makes people believe that it is a dumbed down version of git with lesser functionality, lesser… depth. Not so. Mercurial is every bit as powerful as git and anything that you can do with git, you can almost always do with mercurial.

GitFirst, let’s talk about git. If you’ve ever tried to look under-the-covers of a git repository, you’ll know of git objects. Git and mercurial both use a directed acyclic graph (DAG) to represent history with commits — or changesets, as they are called in mercurial — as nodes of the graph. Also, if you’ve read the first chapter of the Pro Git book, you will know that git stores a snapshot of your repository whenever you make a commit instead of the usual delta (or diff) that the other systems do.

Git’s architecture is designed to provide speed and the way git stores things, it makes both storage and retrieval blazingly fast. However, as your project grows large — specially if there are a lot of commits and a lot of authors — more and more git objects are created and stored as files. Often, several objects are created for a single commit. That’s when the problems begin — your project gets too large and git becomes slowww.

Facebook is 62 million lines of code and git has became slow for the engineers at Facebook. So, they decided to make mercurial faster than git. And they succeeded, as the facebook blog post shows.

MercurialAnyway, now let’s come to mercurial’s architecture. Mercurial is somewhat odd in it’s choice of storing data — in that it does not use either the delta or the snapshot approach exclusively. It tries to strike a balance between the two. I’ll explain this in a bit.

As I’ve said before, git uses git objects — blobs, trees, commits — as backend storage. Also, git creates a new snapshot for every changed file. Mercurial, however, uses a sigularly curious storage system — theRevlog.

With the revlog format, mercurial has truly became a viable alternative to git, specially in the recent years.

Neither mercurial nor git were built to scale to the level of the Facebook repository. However, in the recent years, mercurial has become capable to adapt better to the scalability problem while git has not. I think that this difference stems from the differences in architecture.

Facebook Engineering team chose Mercurial over Git to meet their scalability challenges.

"git vs mercurial for version control"
"git mercurial scalability"

"Been a mercurial user for a while, mercurial was IMO more mature when we started using it about 1.5 years ago. Git was new, and not quite as easy to deal with. What a difference 1.5 years make. I find starting/importing new projects with Mercurial harder than I like. Its not bad, it just takes a bit more thinking than I want during import. So I tried git tonight. Imported the deltaV tools in. Like butta (like butter, e.g. smooth, easy, and tasty). Creating the repository was easy. Moving data to it was easy. Almost trivial. Its a little more complicated in Mercurial, but not much."
"Found Mercurial while looking for alternatives. Mercurial is good, but it is dependent upon some python bits/configuration that is at least mildly annoying. This isn’t a Mercurial issue apart from Mercurial being a python code."
"Tonight I started with git. I created a repository, set up ssh keys, and imported the deltaV tools from the engineering unit inside of about 2 minutes, inclusive of the time to copy and paste the ssh keys, add and commit the stack, and finally move it to permanent storage. Um … we have a winner. Tomorrow I will install the web tools. I’ll also make a set of public git repositories. I’ll leave our existing public hg repository up, but will push new bits to git."

- Facebook chose Mercurial (Hg) over Git because they concluded that Git's internals would be difficult to work with for an ambitious scaling project.
- Facebook is trying to scale a single large repository, which is a different problem than scaling an army of slightly smaller ones.
- Git wasn't scaling for Facebook when they'd have an operating system release
- Mercurial is easier to extend than Git.
- Mercurial has seriously improved over the past couple of years. If you tried mercurial a few years ago and were scared away due to speed or functionality issues, you might want to give it another shot.
- Google uses Perforce, not Git, for its monolithic repository
- Google uses Perforce with caching servers and custom stuff in front of it and some special client wrappers
- One of Google's client wrappers uses git to manage a local thin client of the relevant section of the repo and sends the changes to Perforce
- People at Google who use git suffer from far worse performance than the people who just use perforce as such

Git vs mercurial for version control:

*   The author prefers Mercurial but wants to improve Git.
*   The author has mastered both Git and Mercurial, understands their internals and command line interfaces.
*   Changes are underway to enable Git to scale to very large repositories and that these changes could threaten Mercurial's scalability advantages over Git.
*   Microsoft is pushing Git to adopt architectural changes to enable it to scale.

Mercurial scales to the demands of real, challenging environments where many other revision control tools buckle.

Mercurial's high performance and peer-to-peer nature let you scale painlessly to handle large projects.

Centralised revision control systems tend to have relatively low scalability.

Since the load on a central serverâif you have one at allâis many times lower with a distributed tool (because all of the data is replicated everywhere), a single cheap server can handle the needs of a much larger team, and replication to balance load becomes a simple matter of scripting.

Mercurial scales excellently. See "Scaling Mercurial" for details if you do bump into scaling issues.

In terms of performance, Git is extremely fast. In several cases, it is faster than Mercurial.

Mercurial's major design goals include high performance and scalability, decentralization, fully distributed collaborative development, robust handling of both plain text and binary files, and advanced branching and merging capabilities, while remaining conceptually simple.
Mercurial uses SHA-1 hashes to identify revisions.
Facebook is using the Rust programming language to write Mononoke, a Mercurial server specifically designed to support large multi-project repositories.
In 2013, Facebook adopted Mercurial and began work on scaling it to handle their large, unified code repository.
Google also uses Mercurial client as a front-end on their cloud-based 'Piper' monorepo back-end.
Bitbucket announced that its web-based version control services would end support for Mercurial in June 2020 (then extended to July 2020), explaining that "less than 1% of new projects use it, and developer surveys indicated that 90% of developers use Git".
Mozilla used Mercurial for many years, but started moving to end support for Mercurial in 2023.

- Facebook modified Mercurial to scale with their repository, which stores all of its code in a single repository.
- Neither git nor mercurial were designed to support a single huge repository of all projects.
- Although the Facebook team investigated modifying Git to support their needs, their conclusion was that Mercurial had more appropriate programming APIs that could be hooked into in order to support their requirements.
- Two specific changes have enabled Facebook to use Mercurial for their repository size; modifying the status updates for files to check for specific file changes as opposed to content changes (by hooking into operating system's list of file changes) and modifying the checkout to give a lightweight or shallow clone without needing the full history state.
- These improvements, along with a memcached layer, have sped up Facebook's use of Mercurial to outperform Git for both pull/clone and working directory status calculation by a factor of 5x.

git and Mercurial are very similar in nature. They are both DVCS and have subtle differences only.
Mercurial is easy to fit in the head. The basic operations suffice. The sheer number of command variations in git usually puts me off. It feels a bit more indulgent.
Xcode integration can be a differentiating factor for you.
Xcode's version control UI is so shallow that you'll invariably need to revert to the command line as soon as you start wanting/needing to take advantage of additional features in your DVCS.
For those wishing to use DVCS without learning any command line syntax, there's the brilliant-and-free MacHg. If you simply must use git, you should install a secondary git client to supplement your learning; SourceTree is free on the Mac App Store as of this writing. These are the best $0 clients I've encountered so far.
You can use Mercurial directly within Xcode 4 after installing this patch: xcode4-with-mercurial. Xcode is then able to handle both git & Mercurial repositories.
plugin for Xcode that makes it even easier to handle Mercurial repositories: bitbucket.org/creaceed/mercurial-xcode-plugin

Git:
*   Very fast, scales well, transparent concepts.
*   Steep learning curve.
*   Win32 port not a first-class citizen.
*   Exposes hashes as version numbers.
*   Tracks file contents, even moves between files.
*   Does not track directories.
*   Easy to modify history.
*   Clean underlying design and rich set of features.
*   Best support for multi-branch repositories and managing branch-heavy workflows.
*   Small repository size.
*   Visible intermediate staging area (index) between working area and repository database.
*   Detecting renames and copies using similarity heuristic.
*   MS Windows support lags behind and is not full.
*   Not as well documented as Mercurial, and is less user friendly than competition, but it changes.
*   Written in C, shell scripts and Perl, and is scriptable.
*   Git's log and commit manipulation tools are unmatched.
*   Most complicated and the most dangerous to use.
*   Very easy to lose a commit or ruin a repository, especially if you do not understand the inner workings of git.

Mercurial:
*   Good performance and small repository size.
*   Good MS Windows support.
*   Local branches are second-class citizen.
*   Strange and complicated way it implements tags.
*   File renames suboptimal.
*   Doesn't support octopus merges (with more than two parents).
*   Content-hash addressing for revisions.
*   Does not treat directories as first-class objects (and cannot store an empty directory).
*   Faster than any other DSCM except for Git.
*   Far better IDE integration (especially for Eclipse) than any of its competitors.
*   May be compelling for teams with significant number of win32-centric or IDE-bound members.
*   Written in C (core, for performance) and Python, and provides API for extensions.
*   Resembles Bazaar on the surface.
*   Provides basic distributed version control, as in offline commit and merging multiple branches.
*   Slower than git.
*   Good performance, not big difference compared to Git.
*   Intuitive names for commands.

Bazaar:
*   Reasonably fast (very fast for trees with shallow history, but presently scales poorly with history length), and is easy-to-learn to those familiar with the command-line interfaces of traditional SCMs (CVS, SVN, etc).
*   Win32 is considered a first-class target.
*   Pluggable architecture for different components, and replaces its storage format frequently.
*   Directory tracking and rename support first-class functionality.
*   Tree-local revnos are used in place of content hashes for identifying revisions.
*   Support for "lightweight checkouts", in which history is kept on a remote server.
*   Easy support for centralized workflow.
*   Tracking renames of both files and directories.
*   Performance and repository size for large repositories with long nonlinear history.
*   Default paradigm is one ranch per repository
*   Written in Python, and provides API for extensions.
*   Resembles Mercurial on the surface.
*   Provides basic distributed version control, as in offline commit and merging multiple branches
*   Slower than git.
*   Easy to learn.
*   Very x-platform.
*   Intuitive to folks coming from SVN.
*   bzr-svn is considerably more capable than git-svn

General comparisons:

*   Git, Mercurial, Bazaar are distributed version control systems (DVCS).
*   SVN, Perforce, or ClearCase are centralized version control systems.
*   DVCS allow for much wider range of workflows.
*   They allow to use "publish when ready".
*   They have better support for branching and merging, and for branch-heavy workflows.
*   You don't need to trust people with commit access to be able to get contributions from them in an easy way.
*   SVN's GUI frontends and IDE integration are more mature than those of any of the distributed SCMs.
*   All are still evolving.

Python developers chose Mercurial based on:

1.  Python developers are more interested in using Mercurial.
2.  Mercurial is written in Python.
3.  Mercurial is significantly faster than bzr (it's slower than git, though by a much smaller difference).
4.  Mercurial is easier to learn for SVN users than Bazaar.

Steve Streeting of the Ogre 3D project did a great and even handed comparison of Git, Mercurial and Bazaar. In the end he finds strengths and weaknesses with all three and no clear winner.

- Git is a little harder to use but noticeably faster and arguably more powerful.
- Mercurial is friendlier and easier to use on Windows (TortoiseHg).
- Both have excellent hosting options (GitHub, Bitbucket).
- Mercurial is written in Python.
- Backwards Compatibility (Mercurial): Different versions of Mercurial must always be able to talk to each other over HTTP(S) and SSH.
- Output Stability (Mercurial): Ensure that the output of Mercurial is stable.
- Robustness (Mercurial/Git): Changesets are identified by a cryptographic hash value.
- Security (Mercurial): When repositories are hosted using SSH, all the normal rules for access control applies
- Backup (Mercurial): The proper way to do backups is to use hg clone.
- Git's major plus is Github
- Git is a series of tools just like unix and contains a few layers such as it's plumbing and porcelin where as mercurial is more of a single tool ala svn.

Git:
Open source version control system
Provides strong support for non-linear development.
Distributed repository model.
Compatible with existing systems and protocols like HTTP, FTP, ssh.
Capable of efficiently handling small to large sized projects.
Cryptographic authentication of history.
Toolkit-based design.
Periodic explicit object packing.
Garbage accumulates until collected.
Pros: Super-fast and efficient performance. Cross-platform, Code changes can be very easily and clearly tracked. Easily maintainable and robust. Offers an amazing command line utility known as git bash. Also offers GIT GUI where you can very quickly re-scan, state change, sign off, commit & push the code quickly with just a few clicks.
Cons: Complex and bigger history log become difficult to understand. Does not support keyword expansion and timestamp preservation.

Mercurial:
Mercurial is a distributed revision-control tool which is written majorly in Python and some small sections in C Language.
Features: High performance and scalability. Advanced branching and merging capabilities. Fully distributed collaborative development. Decentralized Handles both plain text and binary files robustly. Possesses an integrated web interface.
Pros: Fast and powerful Easy to learn Lightweight and portable. Conceptually simple
Cons: Partial checkouts are not allowed. Quite problematic when used with additional extensions.

*   A user is a longtime Mercurial (hg) user who never used Git much because they didn't need to collaborate on a project where Git was the choice.
*   The user tried Git several years ago, but their knowledge of Hg seemed to get in the way.
*   The user concluded that Hg was just easier to use for their situation.
*   The user's main complaint with Git was that the commands for Git were significantly longer than what you had to type for Hg.
*   The Rosetta Stone confirmed that the commands were longer for git.
*   The user checked the Rosetta stone again recently, and it seems that git has found a way to close the gap on the command length, so they're going to give it a try again.
*   The user had to fight hard to get their team to switch from Subversion to Hg. 90% of the developers didn't want any part of it. They went behind the user's back to management and tried to poison the well. Management didn't understand it and said "no".
*   The user explained to management that unlike Subversion, Hg would allow the developers to work on parallel paths and you could merge them seamlessly.
*   The developers said they could do that in Subversion.
*   The user created a project of a few dozen files, each file containing several paragraphs of text which started with a developer's name. The user created a repo in Subversion and a repo in Hg and over lunch half of the devs used Subversion to edit and commit the paragraphs with their name and the other half did the same thing in Hg and then they would do the merging after they finished.
*   One of the devs most opposed to Hg cheated and edited other people's text in addition to his own and switched his email account back and forth with his commit statements.
*   The cheating dev thought Hg would have as difficult a time as Subversion did when it came to resolving conflicts.
*   Management called the user in to discuss a migration plan to Hg.
*   The devs still complained, so as a compromise they agreed to make commits to both repositories for about a month.
*   One of the devs who was skeptical at first told the user about the cheating.
*   The user kept an eye on the cheating dev's work and on the first day he consistently "forgot" to post several of his commits to Hg. The user kept an eye on his commits to SVN and Hg and whenever he skipped one, the user created it in Hg.
*   The cheating dev ended up getting fired and escorted off the premises halfway into the experiment for sending out a "workplace humor" comic with racist and sexist humor.

Git vs Mercurial pros and cons:

*   **Easier learning curve:** Mercurial has an easier learning curve.
*   **Windows support:** Mercurial has good Windows support.
*   **Maintenance:** Mercurial is easier to maintain.
*   **Speed over HTTP:** Mercurial runs faster over HTTP.
*   **Branching and cloning:** Git is more intuitive in terms of branching and repository cloning.
*   **Portability:** Mercurial has better portability (e.g., Windows).
*   **Github:** GitHub is awesome for Git.
*   **Hg-Git:** Hg-Git plugin for Mercurial adds the ability to push to and pull from a Git server repository from Hg.
*   **VCS Choice:** Using the same VCS as colleagues and upstream projects makes collaboration easier.
*   **Mercurial users:** Python, Mozilla, OpenJDK are Mercurial users.
*   **Git users:** Many smaller projects use Git, especially in the web space. Linux Kernel, Ruby on Rails and Perl also use Git.

Git vs Mercurial for version control: pros and cons.

- DVCS benefits: can commit offline (faster times, not dependent on internet, everyone has a backup, can commit without messing with others' code).
- Team dynamics develop more naturally with any DVCS.
- Contributors can team up and handle their own merging, meaning less work for integrators in the end.
- Contributors can have their own branches without affecting others' (but being able to share them if necessary).
- Merging hell doesn't exist in DVCSland.
- In DVCSs, everyone represents a "branch", meaning there are merges everytime changes are pulled. Named branches are another thing.
- Mercurial is faster in some things, git is faster in other things.
- Distributed: you can commit/update locally, sharing/taking-from outside your computer is called pushing/pulling.
- DVCSs are easier and more natural.
- With a DVCS you have a different workflow.
- Lose the fear to commit, allowing you to commit at any time you see fit and work a more natural way.
- Everytime you commit you generate an unnamed branch, and everytime your changes meet other persons' changes, a natural merge occurs.
- DVCSs gather more metadata for each commit, less conflicts occur during merging.
- The changesets let you visualize exactly what you meant by doing what you were doing to a specific group of files, not the whole codebase.
- Developers being able to focus on their own work while commiting, without the fear of breaking others' code, they worry about breaking others' code after pushing/pulling but since merging is smarter here, they often never do.
- Mercurial+bitbucket instead of git+github if you work with windows folks.
- Mercurial is also a tad more simple, but git is more powerfull for more complex repository management (e.g. git rebase).
- Backups are easier to do.
- Easier to commit small steps when working without access to the central repository.
- Faster Hudson builds.
- Much, much faster to use git pull than updating.
- The real reason having a local repository is killer is that you have total control over your commit history before it gets pushed to the master repository.
- You can re-write history by continuously rolling the "fix it" and "oops" commits into the "bug fix" commit.
- A developer can do work that is entirely isolated within a branch and then when it's time to bring that branch into the trunk you have all sorts of interesting options: Do a plain vanilla merge. Brings everything in warts and all. Do a rebase. Allows you to sort through the branch history, re-arrange the order of commits, throw commits out, join commits together, re-write commit messages---even edit commits or add new ones!

Git vs Mercurial

Pros of Git:
*   Distributed version control system
*   Efficient branching and merging
*   Fast
*   Open source
*   Better than svn
*   Great command-line application
*   Simple
*   Free
*   Easy to use
*   Does not require server

Cons of Git:
*   Hard to learn
*   Inconsistent command line interface
*   Addons have limitations
*   Overlay complicated
*   Git is slower on windows when compared to mercurial

Git vs Mercurial: Pros and Cons

Mercurial Pros:
- Feels "nicer" to use.
- Philosophy is easier to work with; commands are more modular and less monolithic.
- Doesn't force the use of an index (staging area).
- Written in Python and is easily extendable.
- Works well out of the box on Windows.
- Better native documentation.
- Supported at more open source repositories.

Git Pros:
- The index enables lightweight branches.
- Sane tagging (a tag is not a commit).
- SHA1 hash means the same commit in any repository.
- Faster.
- More built-in tools.
- Higher availability of help, questions, and discussion.
- Git works the way one wants it to out of the box.
- Useful standards like fast-import.

Cons:
- Git can encourage committing untested code due to the index.
- Mercurial makes it difficult to keep private development branches.
