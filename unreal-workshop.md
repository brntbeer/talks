# Working with large files on GitHub

## How we'll be working today
- How many of you use Command Line for some of your development?
  - This is the most granular way to work with Large Files with Git by using Git LFS. However, we'll be using the GitHub Desktop client today to do our work with large files.

## What is Git and GitHub
- Only having 30 minutes to explain working with large files, I'm going to make some assumptions about everyone's knowledge about Git and GitHub. I assume you all have GitHub.com accounts (if you don't, it's free to signup and takes only seconds!) and I assume you may know about Git.
  - If you don't know about Git, I can definitely help! The boring definition is that Git is a distributed version version control system. What this means is, that you can work on your laptop without a network connection and record revisions (commits) of a project as you continue to develop it. These revisions are usually pretty granular and help you have checkpoints (we all love checkpoints right?) to fall back to if something gets seriously screwed up. What's more, is there's a full copy of the project on your laptop at all times, you can get updates with two important commands, a `push` and `pull`.
  - I won't go too deep into this for the sake of time, if you want more info or are interested in more details about this, you can check out our training classes at https://training.github.com/classes/developers/ for either setting up in-person, online, or self-paced classes.

## Workplace scenario: collaborating on a project with a large binary asset
- So you're using Git and GitHub and you realize this project needs to track a large asset. This asset could be an image, an mp4, an mov, whatever. It could also be defined as any file that isn't text based.
- Now traditionally, Git doesn't do well with binary assets. This is because how it compares differences and looks at changes from one revision (commit) to another in the text. It can't render an image. But that's where GitHub comes in, we can.

### Examples of GitHub diff'ing images
- There's only a few things so far that GitHub will show the difference of. The first was images.

SHOW IMAGES

- The next I think came 3d images

SHOW 3D RENDERING

- Etc. Well large binaries are still an issue, and people would like to edit them, AND record the differences in version control (Git in this case)

### Actual demo and no more slides
- I know that on the UE4Git plugin it recommends GitFlow as a workflow, but to me, that's overly complicated, and prone to easily making errors in the workflow. I'm going to be showing GitHub flow, which means any time I'm working on a feature or a fix or anything, that's done in a feature branch, made into a pull request on GitHub.com and then later merged into master for all to use in future feature branches. This is a lot simpler and honestly I think I'd make errors otherwise.
- Let's first start out with this repository that has some assets in it that we want to edit. The only asset I'm going to be working with for ease of demonstrating is an image that I'll edit.
- I'm going to open this repository up in GitHub Desktop so that as I make changes to the assets I can see them reflected in the user interface there.

OPEN DESKTOP
OPEN GIMP (I'm sorry!)

- So after I've made changes to my file, let's look at GitHub Desktop.
- GitHub Desktop should have this ready for me and we can commit it and immediately open a pull request for this change.
- Now, because I have LFS configured for this project, and it's looking to track .png files, we can see how that's reflected in this changes view.
- I'm going to write a description for this change, and commit it. Then start the pull request which also syncs the file.
- There's not much else to it. This seems straight forward because thats what we want it to be like for you when working with these files.
- When we view this file on the web, it's not going to show it to us because it's stored in another data store (in this case, S3 storage for amazon), but what is stored is a reference to the file itself on our servers.

## So what's the big difference?
- So the workflow seems nearly the same, so a lot of people often wonder what the differences are.

1. As we continue to use these large assets without LFS, any edits to the files doubles the size the file takes up on disk. This is because of the way Git stores files (commit 1 has the file at 100mb, after an edit the file is at 120mb, so thats 100+120mb on disk). We'd like the size of the repository on GitHub to not include this large size, but maybe when you work locally you can have that large file
2. As someone whos not working on the assets, maybe you dont need this large file since you're working on the source code for the asset or the documentation. Let's keep the size of the repository locally for these users as small as possible.
