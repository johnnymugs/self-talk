!SLIDE
.notes queue up video
.notes queue up Self
<link rel="stylesheet" href="style.css" type="text/css"/>

# Self Discovery:
## Looking for insight in JavaScript's esoteric roots

!SLIDE
# Hello!
- Jonathan Mukai-Heidt
- Senior Software Engineer at PINCHme
- @johnnymukai / johnnymukai@gmail.com
- terrible JavaScript programmer

!SLIDE
# Self
.notes brief five second intro to self
.notes it influenced JS and its interesting

!SLIDE
# JavaScript is a unique language
.notes There are a lot of things about JavaScript that make it different from other languages.

!SLIDE code
// Objects are a collection of slots

record = {};
record.artist = "Jim Carrol";
record.title = "Catholic Boy";
record.play = function(){
  //...
};

!SLIDE code
// Functions are callable objects
// with properties

var someFunc = function woohoo() {
  return woohoo.wat;
};
someFunc.name; // woohoo
someFunc.wat = 'What what';
someFunc(); // 'What what'

!SLIDE code
// Inheritance through prototypes...

// alert('fill me out!');

!SLIDE
# Every wonder where these ideas came from?

!SLIDE
# I wondered!

!SLIDE
# Start at the beginning
.notes this slide needs work
.notes Noticing CofffeeScript
.notes workarounds for classes in CoffeeScript
.notes lots of griping among colleagues about how terrible JavaScript is (because of inheritance)

!SLIDE
# However!
.notes The thing is, as full of land mines as JavaScript is, and as much as some of my colleagues like to malign it,
.notes JavaScript is pretty fun.
.notes Deep down I know Mr. Eich must be a pretty smart guy, because for all its warts, there's something about JavaScript
.notes that I just can't put my finger on that makes it really fun.

!SLIDE
# FP and Scheme
.notes this influece has gotten a lot of attention
.notes at least in the circles I'm familiar with

!SLIDE
# Raganwald
<img src="img/allonge.jpeg" />

!SLIDE
# JavaScript's approach to OOP
.notes but I was really curious about JS's
.notes unique approach to OOP
.notes there's just some features there that you don't find elsewhere

!SLIDE
# Where from?
.notes where did those features mentioned earlier come from?

!SLIDE
# Another influential language
.notes besides Scheme
.notes As Eich was working on LiveScript, soon to be called Javascript another programming language was making waves.
.notes It was meant to be the successor to Smalltalk, the next big OOP thing.

!SLIDE
# Java?

!SLIDE
# NO!

!SLIDE
Self
====

  .lefty SELF is an object-oriented language for exploratory programming based on a small
  number of simple and concrete ideas: prototypes, slots, and behavior. _Prototypes_ combine inheritance
  and instantiation to provide a framework that is simpler and more flexible than most object-oriented
  languages. _Slots_ unite variables and procedures into a single construct. This permits the inheritance
  hierarchy to take over the function of lexical scoping in conventional languages. Finally, because
  SELF does not distinguish _state from behavior_, it narrows the gaps between ordinary objects,
  procedures, and closures. SELF’s simplicity and expressiveness offer new insights into objectoriented
  computation.

  (_Emphasis mine_)

  Self: The Power of Simplicity, Ungar and Smith, 1991

.notes this is kinda like BAM! SELF
.notes do you want to intro Borning et al more
.notes or is this a good transition?

!SLIDE
# Sounds familiar right?

!SLIDE
# Where did _these_ ideas come from then?
.notes We can get into Self's influence on Javascript in a minute, but let's take some time
.notes to talk about the forces that brought about Self.

!SLIDE
# Let's set the stage
It is the 1980s and Smalltalk is king.

!SLIDE fullpage
<img src="img/bytebloon.jpg" />

!SLIDE
Smalltalk
=========
- THE OOP language
- Alan Kay, Xerox PARC
- Hugely popular, hugely influential

!SLIDE
Smalltalk
=========
- Managed environment
- message passing (from Simula)
- meta/eigenclasses
- "Everything is an object"

!SLIDE
Smalltalk
=========
- major ideas like "everything is an object" are present in Ruby, Python
- syntax influence on Objective C

.notes this "legacy slide" could use some love maybe?

!SLIDE
# So how was Self trying to improve on this?
.notes As early as 1986, six years after Smalltalk
.notes people are already noticing some problems with classical OOP

!SLIDE
# When designing a new object, one must first move to the abstract level of the class, write a class definition, then instantiate it and test it, rather than remaining at one leve, incrementally building an object.

  (from A. Borning "Classes versus Prototypes in Object Oriented Languages", 1986)

.notes this is something we completely take for granted in Javascript with object literals
.notes he goes on to talk about meta-classes and the difficulty this presents new learners
.notes (maybe expand here)

!SLIDE
# The emphasis on classes in the programmer's interface is at odds with the goal of interacting with the computer in a concrete way.

  (Borning, continued)

!SLIDE
# For an object to have a distinct message protocol, a separate class must be created for it.

  (Borning, continued)

!SLIDE
# Enter the 90s and Self
.notes this was the void Self was trying to fill
.notes Self was to be the next Smalltalk
.notes the next step in the evolution of OOP

!SLIDE
# The original Self video

!SLIDE
# Programming as experience

!SLIDE
# Intuitive concreteness of the object

!SLIDE
# No distinction between running and editing a program

!SLIDE
# These were heady times

!SLIDE
# Demo of a Self program?

!SLIDE
# So this was the state of OOP when Eich was developing JavaScript

!SLIDE
# Some practical notes

!SLIDE
# ...Or "What I learned while researching Self"

!SLIDE
# I thought this talk would be about Prototypes vs. Classes
.notes makes sense right?
.notes people arguing over JS's shitty inheritance etc
.notes I was coming from the Ruby-school of OOP
.notes Where Coffeescript was this saving grace that was going to fix the weird OOP of Javascript
.notes And I thought I'd be really digging and looking for an argument

!SLIDE
# Prototypes have already been embraced
.notes I found there wasn't really an argument for prototypes that
.notes hadn't been argued
.notes But there are some really smart programmers out there, people way smarter than me,
.notes Who are already making this argument.

!SLIDE
# Douglas Crockford
  <img src="img/crockford_lrg.jpg" />

!SLIDE
# Douglas Crockford
  .lefty Five years ago I wrote Classical Inheritance in JavaScript. It showed that JavaScript is a class-free, prototypal language, and that it has sufficient expressive power to simulate a classical system. My programming style has evolved since then, as any good programmer's should. I have learned to fully embrace prototypalism, and have liberated myself from the confines of the classical model.

  http://javascript.crockford.com/prototypal.html (from 2006)

.notes 2006, yikes!

!SLIDE
# Eric Elliot
  <img src="img/elliot_rc_lrg.jpg" />

!SLIDE
# Eric Elliot
  Classical Inheritance Is Obsolete – How To Think In Prototypal OO

  http://ericleads.com/2013/06/classical-inheritance-is-obsolete-how-to-think-in-prototypal-oo/

!SLIDE
# Eric Elliot
  https://github.com/dilvie/stampit

.notes (see, I'm not SO late to the game!)

!SLIDE
# Maybe I'm preaching to the choir
.notes Programmers who use Javascript extensively probably know way more about prototypes than I
.notes Object literals in callbacks
.notes The power of prototypes are having a basic object at hand at all times.
.notes Polymorphism for reals - you don't have to figure out what a chair is to implement a bench, as long as they respond to
.notes sit() // or whatever

!SLIDE
# But I shouldn't have been surprised
.notes Reading all the literature from Borning up to Ungar and Smith they all raise the question
.notes Do we need classes? Are prototypes supposed to replace classes?

!SLIDE
# Contemporary JavaScipt is this hypothesis made manifest
.notes In the 90s this was just a question
.notes But they made this assertion, basically "If classes are important, programmers will make them."
.notes Basically, classes aren't bad, they just aren't necessary for everything a programmer does.
.notes Prototypes are more basic, and since we can implement classes with prototypes, let's experiment with making
.notes this more basic component available to the programmer.

!SLIDE
# JavaScript is dynamic enough for us to implement whatever kind of inheritance we want
.notes Setting aside the `new` keyword and constructor functions, programmers implemented the class interface they wanted
.notes So in a sense contemporary Javascript programming answers, in the practical every-day application world,
.notes many of these questions.
.notes TODO
.notes And they were right! Classes are the right tool for the job, but prototypes are more flexible. As we've needed classes,
.notes we've build them in Javascript. But you can't argue against the simplicity of the object literal. Prototypes are more
.notes flexible than classes, but there's no need for us to be dogmatic about them either.
.notes
.notes As I see it, the fact that we've built classes for Javascript proves the points, here in the real world, of these papers
.notes back in the 80s and 90s, that prototypes are more flexible and that classes emerge as needed.

!SLIDE
# Self was more than Smalltalk with prototypes

!SLIDE
# Self's spiritual influence on JavaScript
- Rapid prototyping
- Programming as experience
- Spirit of experientation and exploration

!SLIDE
# Even the bad parts
.notes even things like variable hoisting, these were done to make programming
.notes easier for the beginner (though they ultimately had the reverse effect)

!SLIDE
# Thanks!
# 謝謝
