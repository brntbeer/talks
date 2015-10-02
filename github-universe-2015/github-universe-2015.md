# Outline

## Pull Request
- What are they?
- How do you use them?
- What are ways to do them well

### Setup
- In my few years of training, I don't know if I ever had a class where everyone in the class knew just one language or if everyone was on an even level. So, I and the rest of the training team usually taught with markdown. It's the best way to relate to projects people may work on, so that's what I'm doing today.
- My project just has a few markdown files in it that I use as outlines for my talks. If you want to relate this to something else for yourself, think of this as your documentation repository for all of your projects on GitHub.
- SO! Let's take a look at what's missing from this repository and add it in a pull request. If you're new to pull requests, which I know some people are, it may seem odd based on my explanation previously that I send myself a pull request. Many people often say, "Wait, I'm working by myself. No one is going to work on this with me, why do I 'Open it for discussion'?". Pull requests help me think about the work. It gives me a sandbox environment to work on my own changes. Besides that, even if you're working by yourself, are you going to be working by yourself forever? What if you open source this work? If you're working on it inside of GitHub Enterprise and your team starts to grow? Let's give context to WHY we're doing this change.
  - Some will say the commits will tell why. And that's true, they could but in my opinion, [that's not a proper unit of change](http://zachholman.com/posts/git-commit-history/) in today's day in age. Zach Holman's blog post about this is pretty great in describing pull requests and their usefulness for conversations.
- _Create Pull request_

### Testing, all the time.
- White paper research
- "Use Travis CI, or some other testing service"
- Link to a RubyHoedown 2012 talk maybe where someone (big in ruby) was saying that even a few minutes a day of spending time testing would roll up into minutes lost, then hours, then days over the course of a project

#### Setup with Travis
- I use Travis CI because it's free, I love the documentation, and it Just Works for me.
- Let's add some testing into this, because I want to make sure to some degree that my work is going to work for all time.
- One thing that's easy to forget is that, even though **we** have now said "a url is forever", that doesn't mean other websites adhere to that. What if one of the URLs in my notes section changes? I don't think my tests should pass.
- _Set up travis CI real quick like, maybe even live. Use html-proofer to check URLS still existing. Find a URL that is broke and fix it._

### Summary
- Use Pull Request
- Talk to your team
- Speak like a human

## Code Review
- Now, one could say that if your tests are failing, that you shouldn't be able to merge that code into production.
- What is it?
- Many levels of code review
  - Some people view code review as a thing that happens on a thursday or friday at the end of their sprint cycle. Why would you be synchronous with your code review? You don't want your developers schedule to have calendars, you want it to look empty. If you're worried about them getting work done, we have graphs you can look at to ensure they're getting work done. Allow code review to happen at all time.
  - We are often asked by customers and new users of GitHub about code review and we tell them we have code review. Which I agree with, we do. Through pull request and good social interactions, you can adhere to a culture of "no one ships alone". What I mean by this is that if you're new, and you're working on a teacher, you should not merge until someone on another team or a mentor, or someone senior, or just another person on YOUR team looks at the work and shares the responsibility.
  - This has worked for us for many years, but it's not the only way to do it. As we've grown – both as a company and the number of users – we've heard from our customers and found out about reasons why you would want more rigorous (or gated) code review. The first thing we've done about this is build out protected branches.

### Protected Branches
- Protected branches is the first step to not just listening some of the feedback we received, but really hearing it and doing something about it. **This has been something we've been working on for a long time, and wanted to get correct**.
- Let's take a look at setting up protected branches for our project.

#### Protected Branches Setup
- The thing I want to protect for my repository is master. If you're even knew to Git, master isn't really a special branch or place. It's just a default within the community that people generally associate with "This is the code that is running on our production servers". In fact, some people who use a philosophy of Continuous Delivery through something like CodeShip, or even on TravisCI / CircleCI to send their code off to Heroku, their Amazon EC2 server, or their own server in your own data center have automatic deployments once their pull request gets merged into master. Sounds like good candidacy for protected branches.
- **_Set up protected branches for Master with required status checks for CI_**
- Now as I mentioned, there are many levels of code review. Cultural is one, checking all tests pass is another. We often hear from customers that they want to force review before it gets merged as well. I personally don't love this, because it can slows down the developer to get their changes into production. But, some people need it, and so we can do that too.
- See how we have a required status check for CI? Well, what if we had CI to check for comments?
- (Are there any Bill Nye fans in the audience? One of the things I loved about his show was when he dropped knowledge, "DID YOU KNOW THAT....:" and then he'd explain something, and then the big ominous voice would come back, "NOW YOU KNOWWWWWWW".)
- If we create a webhook for our repository, we could have it send data every time someone comments. If someone comments with `:+1:`, then we may want to count that as them saying they've reviewed the work. This will also have to take into effect a cultural change of people still needing to comment.
- That webhook could go to a server we consider CI, and if there still hasn't been any `:+1:`s on the thread, the tests fail.
- You could also build this to check for a given person to comment, so not everyone could.
- Weellll... If you don't want to spend time building it yourself, and you want some more structure around the review (mark comments as needing to be resolved, external tool for :+1: because your managers only want view that site, etc) you can use [ReviewNinja](https://review.ninja). This is open source, so you can work on it yourself and help add to it if there's something missing, but this is just another example of GitHub's integration power. ReviewNinja can be deployed to Heroku, or you can set it up on AWS if you're so inclined. Or just GitHub.com
- **Show ReviewNinja required status**

### Summary
- Code review comes in many flavors
- Decide how you want to do code review within your team and within your company
  - Decide if you want to force it or just lead by examples.

## The GitHub Flow
- What is the GitHub flow?
  - At it's core, _GitHub Flow is a lightweight, branch-based workflow that supports teams and projects where deployments are made regularly._
  - https://guides.github.com/introduction/flow/
- Why does the GitHub Flow matter?
  - What about Git Flow!
  - Git Flow is harder to learn, and puts more constraints around your developers. We already have code review (maybe even with protected branches), do we need some hard (e.g. it has many steps) workflow on top of it?
- GitHub Flow isn't set in stone either. In fact, at GitHub we have our own special take on it. When we have a pull request, we deploy that branch to production. This is pretty automated and done through our chat service with Hubot.
- Show: http://githubengineering.com/deploying-branches-to-github-com/
- If we wanted to, we could make it so some branches can't be deployed if there are certain tests failing too, we could check that in our deployment sections

### Summary
- All of these pieces are what make software development more human and more safe.
- Some people may even see Pull Request as something that slows down development, "I just commit to master".
  - But now, a pull request is critical to open source and inner-sourced application development around the world from some of the best and brightest developers.
- Some people see code review as another step towards making it harder to ship code. The steps you'd have to take to un-do errors is not worth ignoring this. Just because something takes a little while to do at first, doesn't mean it won't end up being faster to do later, and pay off in the end.
- Using Pull Requests, talking to your teammates or collaborators, and making sure that the code is well tested and reviewed before your merge it are crucial parts of the GitHub Flow and the GitHub Flow is how software should be developed.

## Notes
- [Breaking through with continuous integration]( https://www.atlassian.com/agile/continuous-integration)
- [Why code reviews matter
(and actually save time!)](https://www.atlassian.com/agile/code-reviews)
- [When to do code reviews when doing CI](http://programmers.stackexchange.com/questions/121664/when-to-do-code-reviews-when-doing-continuous-integration)
- [Fog Creek and Jeff Atwood quote on when to do code review](http://blog.fogcreek.com/effective-code-reviews-9-tips-from-a-converted-skeptic/)
- [Wait For It: Determinants of Pull Request Latency on GitHub](https://bvasiles.github.io/papers/msr15.pdf)
- [Why You Should Use Continuous Integration and Continuous Deployment](http://blog.teamtreehouse.com/use-continuous-integration-continuous-deployment)
  - _It’s too easy for us as developers to say that a specific change won’t break something and later realise it did break the app. Often we are simply too lazy to really run all of our tests. This is where an automated system that runs or tests whenever we do any changes continuously can help us from falling into the trap._

## Post Talk feedback
- Slow down the video, not everyone knew what was going on
  - Or use the `k` key in keynote to pause at certain sections. I would have run over on time if I did too much of this
- Make videos bigger so everyone can see
- Use a Madonna mic
  - Some sentences just kind of trailed off because of head movement
- Should have included twitter handle in first slide of talk
- Use more inflection when I want to emphasize something
  - Jokes were lost!
- :+1: to no filler words
- Show examples of pull requests for other to see
  - https://github.com/atom/atom would have been great
