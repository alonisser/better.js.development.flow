class center, middle

# A Better frontend development workflow  
one step at a time   

Me: alonisser@twitter.com. also write in http://4p-tech.co.il/blog

## The holy grail: 
fast feature development, Integration and deployment.

## The Spolsky 12 points test:

  1  Do you use source control?
  2  Can you make a build in one step?
  3  Do you make daily builds?
  4  Do you have a bug database?
  5  Do you fix bugs before writing new code?
  6  Do you have an up-to-date schedule?
  7  Do you have a spec?
  8  Do programmers have quiet working conditions?
  9  Do you use the best tools money can buy?
  10 Do you have testers?
  11  Do new candidates write code during their interview?
  12  Do you do hallway usability testing? 

I'm not sure I'll subscribe to the whole list.

## Remember:  
TDD, BDD, XP etc' are just methods (and good methods) to achieve a puprose.  
we should stay focused on the target, while borrowing tools and Ideas.


## The underlying idea: developer driven development (Hackers gonna hack)
The 3 virtues of the programmer (lary wall - Creator of Perl):
1 Laziness 
2 Impatience
3 Hubris

lets have fun!

## A common cause: **Fast** (and faster) developer feedback

## Automate Everything:  

code, Db, testing, deployment, etc  
manual doesn't scale (But **you** don't need to scale yet)

class center,middle

# The tools:

## jsTooling
After many years of barren land The js/frontend world is suddenly exploding with new tools and methods: Grunt, Yeoman, bower, Phantomjs, THe whole Node/npm stack.  
many decision:
 * full stack vs standalone
 * boilerplate vs opinionated

## Introducing [JShint](http://www.jshint.com/about/)
Js "static" code analysis tool.
can be very annoying and verbose, But teaches about good JS.

## JSHint
 * A config file .jsfint with flags or --config - choose when to silence it.
 * Can also read directive from special comments in the code
 * can check specific files and a whole directory

## How to enforce?!

## Git to the rescue!
would run any executable connected (or symlinked) to here ```./git/hooks/pre-commit```

more goodies:
 1 git submodules
 2 git branch and git checkout. cheap and easy branching (A must have in my opinion)

# Need for speed!
Yslow - Best practices are your friends (most of the time)
 * Linting (jshint is fine)
 * concat
 * minification and uglification
 * css as well as js
remember - everthing can be automated to work for you!

## Intern (or Karma/Jasmine/mocha and the rest)
A js testRunner

## introducing Grunt - a js build tool
 * Gets lots of love lately from frontend developers.
 * A lot of contrib Grunt task.
 * You don't **have** to use a js build tool. make, rake,ant etc would work
# Functional testing
selenium and selenium IDE

## Understand your KPI
log=>measure=>act  
**I'm** not sure you should log **Everything** , depending on the what you want to know(KPI)

## A build server - wrapping everything together
choose the one you like (jenkins is quite the standard but there are others, also as service)
 * You should have one
 * A more comprehensive test suite (unittesting, functional, other) and lint then the one in the pre-commit.
 * maybe using a staging site. can wait for human (QA) input for go/nogo
 * can use measurements (is the page slower after the commit?)
 * automatic deployment scripts from the Build server.