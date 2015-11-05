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
