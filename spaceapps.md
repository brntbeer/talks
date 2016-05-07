# Space Apps outline
- Recorded: https://vimeo.com/163855840

## Intro
- how many people here have heard of Hub?
- What hub does is helps us use github better. If we like to stay on the command line, hub will let us do that.

## Agenda
So some things i'd like to show, and I'd like to describe these scenarios so we can work through them together (well, i'll show you may need to help me! collaboration at its finest)

- Double check we have hub installed
- Fork a project from the command line
- start adding some features (regular git stuff)
- open a pull request from the command line, and browse to it
  - we can do this with pbcopy or `hub browse` and then go look at it
- Take a peek at how hub helps us working together as maintainers of some project (ie: we're not using an organization team)

## Double check hub
- `git --version`
  - this should return hub version too if we've got that set!
- We can also take a look at some hub commands, to get a good idea of what's going on
  - `git help` always is great, but now at the bottom we have some hub things.

## Doing some open source work
- To work on open source, or really any else's project that isn't our own or we dont have write permissions on yet, we need to fork.
  - how many people here have forked a project before?
    - Have you ever struggled to keep your project up to date? Yeah? Exactly. me too. I don't love it!
- Lets find a project to clone. For my example im going to use a project called `example-ruby`. it's one i've used in training classes before. Without opening the web browser, I want a copy of this to my laptop.
  - `git clone githubschool/example-ruby`
- Now, i want to fork it!
  - `git fork`

## Add some feature
- Before i do any of this work, I want to add CI to my fork first.
  - https://travis-ci.org/profile/brntbeer and enable example-ruby
- add a travis-ci
  - couple commits with adding .travis.yml file
  -
```
language: ruby
rvm:
  - 2.0
script: script/cibuild
```
- We have a script/cibuild because that's kind of a culture thing at GitHub. I can talk more about this afterwards: http://githubengineering.com/scripts-to-rule-them-all
- Okay. I've made changes, I want to push. So let's push!
  - I always push before I do a PR, the branch needs to be on the server.
- Now i can run `git pull-request`
  - I can customize this a bit, this is super similar how like in Git, you can run `git commit` and it pops open a dialog box. for doing a PR, you need to supply a message and you can do so on the command line `git pull-request -m "initial adding of travis file"` and add secondary lines and such. but you can also control where you're sending your PR to. By default, forks send PRs to the upstream (where we forked from), but i want to send this into just my fork first. So, to finish this, it's just: `git pull-request -m "initial work for adding travis-ci" -h "brntbeer:add-travis-ci" -b "brntbeer:master"`
- Add a "pbcopy" on the end to get the URL on your clipboard, or `git browse` and it'll open your default browser!

- Because travis CI is running. i can run `git ci-status` or download the travis gem and run `travis status` as well!

## As a maintainer
- Maybe you want to grab a pull request, make a change to it, and then merge it in locally. Git allows this, github allows this, and hub makes it easy
  - `git checkout https://github.com/githubschool/github-games/pull/149`
    - this PR is coming from a repo that doesn't even exist anymore. even better
  - Maybe there's a conflict and you wanted to solve it!
  - then merge it into master and it'll close the PR automatically

## Conclusion
- I hope this at least encourages you to look at more things with hub. I think it makes you a faster developer and allows you to work more effectively with your teammates!
