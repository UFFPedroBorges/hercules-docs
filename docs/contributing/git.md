## Preface

This article will cover the **Git** details related to Hercules. **Git** is a version control system that allows
multiple users to contribute to the development of Hercules, if permitted. It is also the most efficient method to
downloading the source code of Hercules.

## About Git

As mentioned above **Git** is a version control system that allows users to download the latest source code.

### Checkout

When you **clone** a git repository, it is downloaded, along with all history, properties and files, onto your machine
so you can make local changes or use it in a production environment.

### Commit

When you **commit** a piece of code, you are saving a set of changes in a form that can be uploaded back to the server.
Each commit includes the author's name, what they changed and when they changed it, which can be viewed and referenced
later.

### Push

When you **push** your commits, you are sending your commits to the central git server, to make them available to other
people.

Only members of the [Hercules development team](Staff "wikilink") can commit code straight to the Hercules Git.

### Pull

When you **pull** commits, you are downloading the latest commits that were pushed to the git repository, and merging
them to your working copy. In this operation, many files are changed, but some are added, deleted or moved. When you
pull changes, a lot of conflicts can happen, so keep an eye out of those.

### Obtain/Install Git

Please see the [:Category:Installation](:Category:Installation "wikilink") appropriate category for installation of Git
on your operating system of choice and how to utilize it.

## Hercules Git Details

You can find the root or index of the Hercules source code at the following link:
[1](https://github.com/HerculesWS/Hercules/)(https://github.com/HerculesWS/Hercules/). This link can be used if you need
to view a single file and don't want to dig up your "copy" of the source code.

### Hercules Developer Branches

Each developer that contributes to the Hercules Project is welcome to their own branches on the git repository. A lot of
times, these separate branches branch are a testing bed for a new feature. You should never assume that any branch that
is not trunk or not stable is usable. Often times, it is not.

## Using .diff/.patch files

Often times, developers and contributors will release their work with a .diff or .patch file. these files are designed
specifically to be applied to Hercules and 'patched' in.

If the revision numbers are different, or the code is different in anyway, the patch will likely fail with the error
message that the revision numbers do not match. The diff file will include some important symbols and numbers to help
you apply them manually.

`/path/to/file [Revision 233]`  
`@@ +241,4 -241,4 @@`  
`+ This line will be added at the line number or position indicated above.`  
`- This line will be removed at the line number or position indicated above.`

So in the file, we're to remove line 241 and replace it with the line that has the '+' next to it.

[Category:incomplete](Category:incomplete "wikilink") [Category:Basics](Category:Basics "wikilink")
