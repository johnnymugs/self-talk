!SLIDE

#Self Discovery: Looking for Insight in Javascript’s Esoteric Roots

= Who am I
  - @johnnymukai
  - Senior Software Engineer at PINCHme
  - love Javascript, but not very good at it.

= Javascript is unique
There are a lot of things about Javascript that make it different from other languages.

= Slots
# we can just pop a new slot right onto a function
``````
record = {};
record.artist = "Jim Carrol";
record.title = "Catholic Boy";
record.play = function(){
  //...
};
``````

= Functions are (kind of) objects with slots/properties
``````
var someFunc = function woohoo() {
  return woohoo.wat;
};
someFunc.name; // woohoo
someFunc.wat = 'What what';
someFunc(); // 'What what'
``````

= Prototypes
``````
var ConstructorFunction = function(){
// ...
};
var cf = new ConstructorFunction();
``````

= Ever wonder where some of these ideas came from?

= I wondered!

= Start at the beginning
  - Noticing CofffeeScript
  - workarounds for classes in CoffeeScript
  - lots of griping among colleagues about how terrible Javascript is (because of inheritance)
  (Seems JS new keyword is a concession to Java)

= But!
The thing is, as full of land mines as Javascript is, and as much as some of my colleagues like to malign it,
Javascript is pretty fun.
Deep down I know Mr. Eich must be a pretty smart guy, because for all its warts, there's something about Javascript
that I just can't put my finger on that makes it really fun.

= With the rise of FP people have looked at Scheme's influence
  (see Raganwald et al)

= But a lot of these curious features are really in Javascript's approach to OOP and nothing to do with FP or Scheme.
-These were the features I became curious about.

= Another
  As Eich was working on LiveScript, soon to be called Javascript another programming language was making waves.
  It was meant to be the successor to Smalltalk, the next big OOP thing.

= Java?
= Java?
No!

##### need an intro to Self much better!
= Xerox - what was going on then?

= Self
  Everything is an object (like Smalltalk)

= Self
  # blockquote
  # title = Self: The Power of Simplicity, Ungar and Smith, 1991
  SELF is an object-oriented language for exploratory programming based on a small
  number of simple and concrete ideas: prototypes, slots, and behavior. ((*Prototypes*)) combine inheritance
  and instantiation to provide a framework that is simpler and more flexible than most object-oriented
  languages. ((*Slots*)) unite variables and procedures into a single construct. This permits the inheritance
  hierarchy to take over the function of lexical scoping in conventional languages. Finally, because
  SELF does not distinguish ((*state from behavior**)), it narrows the gaps between ordinary objects,
  procedures, and closures. SELF’s simplicity and expressiveness offer new insights into objectoriented
  computation.
  ((*Emphasis mine*))

= Some of these concepts surely sound familiar

= Why?
  - We can get into Self's influence on Javascript in a minute, but let's take some time
  to talk about the forces that brought about Self.

= Let's set the stage
  - 80s & Smalltalk

= Smalltalk picture

= Smalltalk
  - to be THE OOP language
  - Alan Kay
  - Hugely popular
  - Hugely influential
  - needs to be filled out more

= Smalltalk
  probably everyone in this room is familiar with smalltalk
  smalltalk for those not familiar was a hugely influential language by alan kay and co
  managed environment
  everything is an object
  you pass messages between objects

= So what happened?
  - people became disatisfied with class-based OOP
  - as early as XYZ there were proposed prototypal languages
  - talk more about issues with classical OOP

= Classes versus Prototypes in Object-Oriented Languages
  - Alan Borning, 1986

= The 90s: Enter Self
  - Self was looking to fill a particular void
  - The Next Smalltalk - prototypes

= The Original Self Video

= The aims of self

= Programming as experience

= Concreteness of object, intuition

= No distinction between running and editing a program

= aside
  - some of these ideas seem pretty nuts -- run/edit
  - but these were heady times
  - remember JIT compilation etc

= So this was the state of OOP when Eich was developing Javascript

= The argument for prototypes
When I started work on this talk, when I first started looking at Self and trying to think about prototypes in Javascript
I was coming from the Ruby-school of OOP
Where Coffeescript was this saving grace that was going to fix the weird OOP of Javascript
And I thought I'd be really digging and looking for an argument

= Prototypes have already been embraced
But there are some really smart programmers out there, people way smarter than me,
Who are already making this argument.

= Douglas Crockford
  - need an example here

= Eric Elliot
  - some of EE's talks

= (Just to name a few)
  Programmers who use Javascript extensively probably know way more about prototypes than I
  Object literals in callbacks
  The power of prototypes are having a basic object at hand at all times.
  Polymorphism for reals - you don't have to figure out what a chair is to implement a bench, as long as they respond to
  sit() // or whatever

= Where I thought I was going with this talk
  in sum, when I started writing this talk I'd be writing a classes vs prototypes argument

= What I actually learned from researching Self
  but I was wrong!

= Classes or Prototypes
  Reading all the literature from Borning up to Ungar and Smith they all raise the question
  Do we need classes? Are prototypes supposed to replace classes?

= In the 90s this was just a question
  But they made this assertion, basically "If classes are important, programmers will make them."
  Basically, classes aren't bad, they just aren't necessary for everything a programmer does.
  Prototypes are more basic, and since we can implement classes with prototypes, let's experiment with making
  this more basic component available to the programmer.

= Programmers DID implement classes in Javascript
  Setting aside the `new` keyword and constructor functions, programmers implemented the class interface they wanted
  So in a sense contemporary Javascript programming answers, in the practical every-day application world,
  many of these questions.
  # edit
  And they were right! Classes are the right tool for the job, but prototypes are more flexible. As we've needed classes,
  we've build them in Javascript. But you can't argue against the simplicity of the object literal. Prototypes are more
  flexible than classes, but there's no need for us to be dogmatic about them either.

  As I see it, the fact that we've built classes for Javascript proves the points, here in the real world, of these papers
  back in the 80s and 90s, that prototypes are more flexible and that classes emerge as needed.

= Summary

= But let's not forget what else Self contributed to Javascript
  - Rapid prototyping
  - Programming as experience
  - Spirit of experientation and exploration

= Break

But Self was more than Smalltalk with prototypes.

Spiritual influence: variable hoisting, experimentation, accessability

= Programming Language Timeline
  - 1958 LISP
  - 1972 Smalltalk & C
  - 1975 Scheme
  - 1983 C++
  - 1987 Perl
  - 1987-1990 Self
  - 1995 Javascript & Ruby

