# Outline

## Pull Request
- What are they?
- How do you use them?
- What are ways to do them well

### Testing, all the time.
- White paper research
- "Use Travis CI, or some other testing service"
- Link to a RubyHoedown 2012 talk maybe where someone (big in ruby) was saying that even a few minutes a day of spending time testing would roll up into minutes lost, then hours, then days over the course of a project

### Summary
- Use Pull Request
- Talk to your team
- Speak like a human

## Code Review
- What is it?
- Many levels of code review
  - We are often asked by customers and new users of GitHub about code review and we tell them we have code review. Which I agree with, we do. Through pull request and good social interactions, you can adhere to a culture of "no one ships alone". What I mean by this is that if you're new, and you're working on a teacher, you should not merge until someone on another team or a mentor, or someone senior, or just another person on YOUR team looks at the work and shares the responsibility.
  - This has worked for us for many years, but it's not the only way to do it. As we've grown – both as a company and the number of users – we've heard from our customers and found out about reasons why you would want more rigorous (or gated) code review. The first thing we've done about this is build out protected branches.


## Notes
- [Breaking through with continuous integration]( https://www.atlassian.com/agile/continuous-integration)
- [Why code reviews matter
(and actually save time!)](https://www.atlassian.com/agile/code-reviews)
- [When to do code reviews when doing CI](http://programmers.stackexchange.com/questions/121664/when-to-do-code-reviews-when-doing-continuous-integration)
- [Wait For It: Determinants of Pull Request Latency on GitHub](https://bvasiles.github.io/papers/msr15.pdf)
- [Why You Should Use Continuous Integration and Continuous Deployment](http://blog.teamtreehouse.com/use-continuous-integration-continuous-deployment)
  - _It’s too easy for us as developers to say that a specific change won’t break something and later realise it did break the app. Often we are simply too lazy to really run all of our tests. This is where an automated system that runs or tests whenever we do any changes continuously can help us from falling into the trap._
