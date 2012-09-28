Speaker: Jeremy Mikola

Slides: https://speakerdeck.com/u/jmikola/p/being-a-good-oss-contributor

# Being a Good OSS Contributor

OSS projects need:
- Evangelism
- Documentation
- Development
- Support

## Evangelism

How do we discover?
- Twitter
- Word of mouth
- Github

How do we elect to use?

Become motivated to contribute?

### Share your experience
- For current and prospective users
  - Blog posts
  - Case studies
- For project members
  - Answering RFCs
  - weighing new features or changes
  - highlighting what works and doesn't

### Feedback guides decision making *

Praise -> reinforcement

Criticism -> reevaluation

* except when it doesn't

### Don't omit criticism
- Positive feedback loops are dangerous
- the best criticism is constructive
- good decisions require objectivity

#### Don't be a fanboy

### Growing the Community
- As individuals
  - Attend conferences
  - host local meetups
  - make friends
- As companies
  - Sponsor the above

## Documentation

How do we...
- Get up and running?
- Learn how to use a project?
- Get acquainted with a new API?

Documentation comes in:
- Code
- API docs
- Test cases
- README
- The Book
- Cookbooks and tutorials
- Starter apps and distributions

Great documentation:
- Consistent writing style
- Users make the best authors
- Evolves as the code changes

#### Wrong documentation is dangerous

Before you commit:
- Follow conventions
  - Formatting
  - Structure
  - Writing Style
- Test your changes
  - Content: grammar, spelling, links
  - Syntax: reStructured Text, Markdown, HTML
  - Build: Sphinx, Docbook

#### Translation opportunities

## Support
Users expect things to work
- Some users ask questions
- Good users file bug reports
- Awesome users submit patches

Support is:
- Often a thankless job
- Necessary for growth
- Never finished

The Relentless flow of questions
- Why is the user asking this?
- Refer to existing content if possible
  - previous discussions
  - relevant documentation
- Good exchanges deserve visibility

Bug reports
- Encourage users to report _actual_ issues
  - handle security vulnerabilities responsibly
- Triaging saves time
  - identify duplicate and invalid reports
  - cross-reference related or upstream issues
- Fill in the gaps
  - Collect background information
  - Create failing test cases
  - Document workarounds

Code Reviews
- Ensure the test suite passes
  - Is the current test coverage sufficient?
  - Avoid arguments with travisbot
- Object calisthenics (Jeff Bay)(helpful principles, but don't go overboard)
  - Summary by Ben Nadel-- not official: http://www.bennadel.com/resources/uploads/2012/ObjectCalisthenics.pdf
-Coding standards and conventions
  - https://github.com/klaussilveira/phpcs-psr
  - https://github.com/fabpot/PHP-CS-Fixer

#### Teach others to do what we do
Support is a big part of it

## Development

Taking the first step
- How many OSS projects started because of a tangible need for some basic functionality?
- How many core developers got their stary by fixing a small bug?

Reconnaissance
- Start with bug fixes or small tasks.
- Collect feedback prior to major contributions
- Join developer chats and roadmap discussion

Be a humble contributor
- Who are you implementing this for?
- Review your own work before you expect someone else to.
- Don't turn code reviews into religious debates

#### There are no small contributors, just small changesets.

#### Don't create borders where there are none.

### Notable mention
- @javiereguiluz
- @pborreli