class: center, middle

# A Better frontend development workflow  
(one step at a time)

Me: @alonisser ([twitter](https://twitter.com/alonisser))  

Tech blogging in http://4p-tech.co.il/blog.  
social activist and [blogger](degeladom.wordpress.com)

presentation with css/js/markdown via [remark](https://github.com/gnab/remark)

---
class: center,middle

#part 1: A framework

where I'm coming from
---
class: middle

# The holy grail:  

**Fast** feature development, Integration and deployment.
---

## The Spolsky 12 points test:

1.  Do you use source control?
2.  **Can you make a build in one step?**
3.  **Do you make daily builds?**
4.  Do you have a bug database?
5.  Do you fix bugs before writing new code?
6.  Do you have an up-to-date schedule?
7.  Do you have a spec?
8.  **Do programmers have quiet working conditions?**
9.  Do you use the best tools money can buy?
10. Do you have testers?
11.  Do new candidates write code during their interview?
12.  Do you do hallway usability testing? 

Bumped into this once and liked it. 
I'm not sure today I'll subscribe to the whole list, but I adopted some concepts.
---
class: middle

## The buzz:
TDD, BDD, XP etc'

All just methods (and good methods) to achieve a puprose.  
we should stay focused on the target, while borrowing tools and Ideas and common cause.
---
class: middle

## The underlying idea: developer driven development

###Hackers gonna hack..  
Remember The 3 virtues of the programmer (lary wall - Creator of Perl)?:  
1. Laziness  
2. Impatience  
3. Hubris  

lets have fun!
---
class: middle

## A common cause: **Fast** (and faster) feedback.
 * automated feedback
 * fellow coders feedback
 * integration feedback
 * most important: customer feedback (but you have to ship to get that!)
---
class: middle

## Automate Everything:  

Code, Db, testing, deployment, etc  

 * manual work doesn't scale (But **you** don't need to scale yet).
 * manual debugging and testing doesn't scale and **doesn't work**.
---
class: center,middle

# Part 2: The tools
---
class: middle
## jsTooling
After many years of barren land The js/frontend world is suddenly exploding with new tools and methods: Grunt, Yeoman, bower, Phantomjs, The whole Node/npm stack and ecosphere.   

choices, choices, choices:

 * full stack vs standalone
 * boilerplate vs opinionated
 * right tool for the job
 * style

---
class: middle
## Introducing [JShint](http://www.jshint.com/about/)
Js "static" code analysis tool.
 * can check specific files and a whole directory
 * can be very annoying and verbose, But teaches about good JS.
---
class: middle

## configurting JSHint
 * A config file .jsfint with flags or --config - choose when to silence it.
 * Can also read directive from special comments in the code

---
class: middle
## How to enforce?!

### Git to the rescue!
would run any executable connected (or symlinked) to here: ```./git/hooks/pre-commit```  
Useful for basic automated syntax test or linting

more goodies:

1. git submodules (for dependencies)
2. git branch and git checkout. cheap and easy branching (A must have in my opinion)

poor man's build (we'll look to that later)
---
class: middle

# Need for speed!
 * speed is a feature.

 * introducting [Yslow](http://developer.yahoo.com/yslow/):
 * Best practices are your friends (most of the time)

recommandations include (but not exclusive):

 * concat
 * minification and uglification
 * css as well as js
 * much more
remember - everthing can be automated to work for you! (see grunt later)
---
class: middle

## [Jasmine](http://pivotal.github.io/jasmine/)
 * A js [testRunner](./examples/jasmine/specRunner.html)
 * simple UnitTesting

## There are more options:
 * Karma, Mocha, Chai
 * choose the one that works for you
 * Zombie etc'

---
class: middle
# Functional testing
 * [Selenium](http://seleniumhq.org/) and selenium IDE: Record a Test from the browser (install with firefox)
 * edit the test (selenize looks like an html table)
 * many plugins: including screenshot on failure etc.
 * There are also binding to server side programming languages
 * an a cloud service -[Sauce labs](https://saucelabs.com/) that can handle the testing for you (intern integration!) including language binding the webdriver testing with different browsers. if you prefer easier setup in trade for money.
---
class: middle
#Functional testing
 * There is also a more 'js' way for backend functional testing. (test a browser with js..)
 * **[Casper.js](http://casperjs.org/)** over Phantom.js -  a webkit based headless browser. (wrote a [blogpost](http://4p-tech.co.il/blog/?p=1016) about this one)
 * currently(1.1dev) casper can also run over slimer.js. A gecko based headless browser.
 * more casper/phantom goodies: capture to png. [phantomcss](https://github.com/Huddle/PhantomCSS) to check rendering against pre generated png.
 * another headless browser is zombie.js, nice api, less ecosphere.
---
class: middle
## The [Intern](http://theintern.io/)  
```bash
npm install intern
```

 * The **new** Hotness
 * Integrates unit testing with functional testing with selenium and phantomjs. coverage etc.
 * Didn't play with this enough to testify.
---
class: center, middle
# Part 3: The Build
---
class: middle
## Introducing [Grunt](http://gruntjs.com/) - a js task running tool
 * Gets lots of love lately from frontend developers.
 * A lot of [Grunt tasks](http://gruntjs.com/plugins) in repos.
 * Best practice and common in contrib plugins.
 * You don't **have** to use a js build tool. make, rake,ant etc would work if you like them better.
---
class: middle
## Understand your KPI
 * log=>measure=>act  
 * **I'm** not sure you should log **Everything** , depending on the what you want to know.
---
class: middle

## A build server - wrapping everything together.

choose the one you like ([jenkins](http://jenkins-ci.org/) is quite the standard but there are others, also as service)

 * You **should** have one.
 * A more comprehensive test suite (unittesting, functional, other) and lint then the one in the pre-commit.
 * Maybe using a staging site. can wait for human (QA) input for go/no-go
 * Can use measurements (is the page slower after the commit?) - intgeration with Yslow
 * automatic deployment scripts from the Build server.
 * There are also [cloud services](https://www.codeship.io/) for that.

---
class: center, middle
#Questions? 
