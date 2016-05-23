## Conference [GitHub Satellite: Amsterdam](https://githubuniverse.com/satellite)

**Where** : Amsterdam :flag_nl:

**When** : May 11, 2016

**Approved** : Approved

**Title**: Collaborating with Hubot for a More Efficient DevOps Workflow

**Type of talk**: 40min presentation

**Audience level**: All

**Type of presentation**: Slides and maybe demo?

### Notes
- Should be more Hubot-y
- Wired article about hubot being the most valuable employee
- How do you know your feature has been deployed successfully without checking metrics? Which metrics? Hubot probably can find all of those and bring those to light for everyone to see. That means everyone will gain from seeing what you typed, pointing out any typos if you can't find that correct Graphite syntax, or Hubot will just aggregate things for you so you have to spend less time thinking about numbers and more time making sense of it all.

### Abstract
Have you been told that your company is moving to a more DevOps development culture, but you have no idea what that really means? Everyone wants to run a more productive and agile engineering team by balancing the competing priorities of rapid releases and stable systems. DevOps is a movement that everyone is either wishing they had, talking about setting up, or getting ready to implement. But how does a chat robot fit into this, how can it help speed things up, and how can everyone on the team learn from each others' successes and failures at the same time?

In this talk we'll introduce you to Hubot, an open source robot who sits in your company's chat client to help your developers by doing most of the heavy lifting. We'll look at how he can bring GitHub and many core DevOps tools and philosophies to developers' fingertips and why everyone on the team gains from this benefit. We'll also see how easy it can be to configure Hubot to plug into other tools that integrate with GitHub and what results we can expect to see from using Hubot. By the end of this session, we will have outlined why using Hubot is better for individuals and teams, while increasing the speed to develop any of your features.

### Outline
General outline to build a story: Mention the problems, introduce a solution, tie the solution to their heartstrings by proving it with real examples, and end with next steps of how they can get towards this with GitHub

- Introduction ("Dearly beloved, we are gathered here today to get through this thing called collaboration")
  - DevOps is so hot right now
  - What even is devops?
    - Define what I mean by it so it makes sense for this talk
  - What are some problems devops tries to fix
  - Preface from Automation and Monitoring book with Hubot as a quote
- Hubot
  - What is a Hubot? Why do I care
  - Rise of the bots
  - Microsoft is even into it. So if you're not doing this, you're doing it wrong.
  - What is my purpose? https://pbs.twimg.com/profile_images/534547089837928448/IOmSlaOQ_400x400.png
- Chatops
  - Okay, Hubot has to live somewhere, that's easy: Heroku!
  - But, how do we talk and work with Hubot? Let's give him a podium and a big microphone
    - SLACK in big letters
  - Hubot comes with lots of adapters to work with. I recommend using terminal to get started to get used to using Hubot, but then just set up a slack room and invite your best robot.
  - Definition of what chatops is
  - things like `hubot ghe-backport`
  - this section is similar to @dirkjan's, but we can just duplicate efforts to ensure everyone has the same message
- Automation. Roooobawwtttttttttt
  - Dirty, Dull, Dangerous quote?
  - Regardless of development teams, how does your support team  know when an urgent ticket came in about a customer?
    - sure email, yeah email sucks and isn't in front of people constantly
  - Do you know who is on call if your email server falls over?
  - How do you find out web performance?
    - Is it on some cool graphs that look great as new hires walk through your office or the non-engineering team people can see that looks fancy?
    - What if it was in the chat?
  - What other things are you doing manually?
    - Issues assigned to you?
    - Or integrations Jira, Huboard, trello, Asana?
  - Whats the status of that build? Would you rather re-run in?
  - github chatterbox for automating adding hubot to more repos. automation on automation
  - "Exception rates increasing lately since person-x deployed last! go check it out LINK"
  - How do you deploy today?
    - Are your deploys as boring as possible? Thanks Zach!
    - Tie this into some development tool. My vote is Heroku
- Example? (_OPTIONAL_ Would be nice to tie all of it together in some example, showing me in chat asking hubot for something assigned to me. Work on it and push it to GitHub, @mention a few people or a team, have hubot tell me the CI status, branch deploy when I say so (reverse merge too you robawt), Once the branch merges it closes out the thing assigned to me (easy if it was github issue, but maybe asana or something), have hubot auto-deploy master!
  - "Problem 1: how does work get assigned to you? do you have to go searching for what work it is? What if hubot could tell you?"
    - https://github.com/github/hubot-scripts/blob/master/src/scripts/list-jira-bugs.coffee
  - "Problem 2: how do you test?"
    - TravisCI, but hubot reporting that (basically github into slack via hubot)
  - "Problem 3: how do you deploy?"
    - Heroku through hubot?
  - "Problem 4: How do you collaborate and work on all of this with everyone all of the time? (@jnewland quote?)"
    - ChatOps
- Next steps
  - Summarize what we talked about: we have these problems, there are many ways to fix problems, devops is one way that's currently got a lot of traction and I love it, Hubot is the most important person to collaborate with, everyone should be able to collaborate with Hubot in Chat, make hubot do the dirty, dull, or dangerous work but if you collaborate with everyone all of the time then you're always learning and everyone becomes better all of the time.
    - A rising tide rises all ships quote?
    - Prince quote to end it as well? Nothing can stop us now, I'm gonna show you how (let's work)
      - "When working in the terminal, _Take a look around u At least u got friends_ and Hubot

- Thanks!
- References
  - https://leanpub.com/automation-and-monitoring-with-hubot
  - https://zachholman.com/posts/deploying-software
  - https://blog.newrelic.com/2015/08/18/chatops/
  - https://www.atlassian.com/continuous-delivery
  - https://reddit.com/r/chatops
  - http://www.wired.com/2015/10/the-most-important-startups-hardest-worker-isnt-a-person/
  - http://techcrunch.com/2016/04/07/rise-of-the-bots-x-ai-raises-23m-more-for-amy-a-bot-that-arranges-appointments/
  - http://techcrunch.com/2016/05/10/facebook-chatbot-analytics/
  - https://dev.botframework.com/
  - http://www.adultswim.com/videos/rick-and-morty/something-ricked-this-way-comes/
  - https://www.ge.com/digital/blog/dull-dirty-dangerous-its-robot-work

# Feedback
- deeper dive into some example
  - showing the jira script and showing it work live :+1:
- Hubots personality
  - "meatbags" in the office instead of just saying humans or people.
- Show more enthusiasm about a particular command
  - "oh, and this is one of my _Favorite_ things! watch this"
