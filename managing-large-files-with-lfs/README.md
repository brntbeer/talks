# Managing Your Large Files with Git LFS

Git has continued to prove itself year over year as the preferred version control system for software developers, but game developers have always been left with complex solutions, workarounds, or needing to use a different version control system all together because of how Git handles large assets and binary files. The decision whether or not to use Git is now over thanks to Git LFS.

In this talk I'll introduce you to Git LFS, an open source project developed by GitHub, Atlassian, and the open source community to help Git handle these large files. This unprecedented collaboration is bringing sane management of large file assets to Git and our favourite collaboration platforms, like GitHub. By the end of this session you will have seen how LFS works, learned how to integrate it into your existing Git workflow, what graphical interfaces support it, and finally have a clear path forward to work and collaborate effectively with anyone.

## Outline
- Introduction
  - Poll room about experience and current workflows
    - Who uses a terminal, who uses a GUI, etc
- Background
  - State of large files in software development
  - What solutions did people have previously
    - Not necessarily new work. But LFS is sticking in the community.
    - Other version control tools
- What is LFS?
    - This will hopefully solidfy what it is and how it's used because people will see something concrete
    - What about seeing projects marketed on the website and use those as references to make people imagine that those could be developed with LFS (though I may not be able to actually confirm)
  - "Throughout this talk we're going to convince you that most if not all of your pains with large asset development will go away". "Or any pains you had with git before and this kind of work."
    - I would love it if you walk away and say "Well, that's not hard"
      - I want this to seem simple once you get it installed. I want you all using Git
  - Some content from https://www.eclipsecon.org/na2016/sites/default/files/slides/Practical%20workflows%20with%20Git%20LFS%20%28EclipseCon%29.pdf would do well here
  - Don't really need to go into too many details about HOW it work, I don't think that part is SUPER important. I just want to show that it's possible and how to get people started as fast as possible
  - Find examples of GitHub projects that are using LFS
- How to get started with LFS
  - Getting started on new projects
  - Migrating existing Git projects that should have LFS installed but dont and you've been in trouble for some time.
    - git BFG repo cleaner with LFS support: https://rtyley.github.io/bfg-repo-cleaner/
    - git-lfs wiki says to do this now: https://github.com/bozaro/git-lfs-migrate? Doesn't explain how it works, I dont like it.
- How to move over to Git with LFS from other version control tools
  - Most likely the case for people in the audience.
  - Maybe demo / video this from svn or mention the steps and patterns
  Then you can carry on with Git and GitHub development practices that everyone loves. Good tool integration, collaboration / communication, and a pleasant workflow
- Setting up an LFS server
  - You may be an admin or your admin at your company may want to know how to get this going for you!
    - This is some material that you can hopefully take back to someone to show them how to set it up
  - May just be a quick overview that says GHE supports this but where to go for more information
    - The attendees may not care about this.
- Common Git LFS workflows
  - "Now that everything is set up..."
  - Skipped this section and showed it in an interface with desktop
- Graphical Interfaces
  - Eclipse (with eGit)
  - Sourcetree looks real good
  - VSfGH doesn't really do anything specific either
  - GHfD
    - Ending with GHfD to stay sharp in people's mind as we move forward and talk about tips and things.
  - UE4GitPlugin
- Tips with using LFS on teams which not everyone needs LFS
  - Is it possible to keep just the most current version of a asset download
  - Grabbing specific assets
  - ignoring all assets
  - Other less-well-documented commands
    - https://github.com/github/git-lfs/blob/master/docs/man/git-lfs-checkout.1.ronn
    - https://github.com/github/git-lfs/blob/master/docs/man/git-lfs-fetch.1.ronn#L37-L68
    - lfs.fetchrecentcommitsdays
      - `git lfs fetch --recent` will fetch objects in recent commits and other active branches. Good if you're going on a plane trip or something.
    - lfs.fetchrecentalways
    - Some people will want `git config lfs.fetchinclude Path/to/assets`
      - What about `lfs.fetchexclude`!
  - File Locking support coming soon to a project near you? Community definitely could use this but I think with the gaming community continuing to get behind LFS and putting some support on this we can continue to see this project accelerate and become the tool it needs to be.
- Conclusion
  - recap things
  - What can you do to get started today?
    - Install LFS locally
    - Make sure it's installed on your favorite graphical client
  - Get involved with the community to help make it better! https://github.com/github/git-lfs
- Thanks!

## Feedback
- Maybe talk about current state of git-lfs once I mention how to get it installed
  - Include link early for file locking as a problem set
  - Include resources for what happens when i don't have LFS installed and someone sends me a contribution for LFS support on my repo?
  - Information for how non-technical people work better with lfs?
    - Of course they don’t always work on the same pieces and are doing different things.
- Audience was surprisingly technical. Was told they may not be!

## Additional Resources
- http://bit.ly/git-lfs-gdc-eu
