Hello again Mr. Ungar,

Please find below my notes for my upcoming talk on Self's influence on JavaScript. It's in pretty rough shape as I plan on adlibbing from notes/slides mostly, but I tried to sort of type out the gist of each part that I'm trying to cover. I hope it makes sense and I hope it's enough for your stamp of approval or criticisms. Sorry to get this to you so late, it's been a hectic couple of months.

Thanks so much for speaking with me. Studying Self has been really inspirational and I hope to keep up with studying it after I get back to the States after delivering this talk. After digging in, I still feel like I've only scratched the surface. I hope you don't mind that I call Self esoteric below. I'm really shocked at how few people outside of academia have heard of Self, while on the other side, people frequently invoke it as a strong influence.

There is one thing that I didn't get to ask you that's been plaguing me. If you don't mind me asking, how is a new programming language like Self conceived? I know a few game developers and when they are proving out ideas for new multiplayer strategy games, frequently they will write the rules out and play the game among friends on paper prototypes. Is there any analgous strategy for a new programming language? Do you just start coding? Do you start with a simple syntax and an example program?

Also, in your talk Self Whys and Wherefores, you mention that the students should ask you about your funny job interview story. Do you mind sharing that?

Thanks so much, again!


Johnny

Self Discovery:
Looking for insight in JavaScript's esoteric roots

(intro slide)
- Jonathan Mukai-Heidt
- Senior Software Engineer at PINCHme
- @johnnymukai / johnnymukai@gmail.com
- Terrible JavaScript programmer

I'm kidding a little about being a terrible JavaScript programmer, but sometimes I'm really blown away by JavaScript.
I'm really excited to be giving this presentation here in Beijing.
I started programming JavaScript back in 1998 or 1999.
Back then, JavaScript was this little thing you would use to make a menu pop up or annoyingly move parts of the DOM around.
A lot of the people in this room may not remember but back in the 90s we were writing exceptionally simple DOM manipulations in JS and that was it.
It was legendarily implemented in an exceptionally short time, and people really thought it would go the way of the buffalo.
They thought that Java in the browser or Flash was the way things were going.
I remember when Google started using AJAX in search results and it blew my mind.

That was back in the late 90s, early 2000s. Now I have reason to be blown away again.
I went through a period where I wasn't programming any front-end stuff or I was writing very little of it anyway.
In the past three years or so I've gotten back into it and I can't believe how far the community and the libraries have come -- to make no mention of node.
I tell people I feel like Rip van Winkle.
I went up into the mountains and now that I've come back down, JavaScript has taken over!

Anyway, I hope the reason for bringing up my own rambling backstory will make sense in a minute.
What I'd like to do today is give you all a bit of a history lesson.

What I'd like to talk about today is Self.
Self was and still is an ambitious and wholly unique language that had a very strong influence on JavaScript.

There's a lot of fascinating history here, which I think is interesting enough to warrant a talk on its own.
But there's also a lot of lessons to be learned from Self.
I hope that after this talk you'll be able walk away not just with a greater sense of JavaScript's place in programming history,
but also with some practical lessons.
And most importantly, a little inspiration.

So how did I come to be interested in Self?

JavaScript is a unique language
There are a lot of things about JavaScript that make it different from other languages.

// Objects are a collection of slots

record = {};
record.artist = "Jim Carrol";
record.title = "Catholic Boy";
record.play = function(){
  //...
};

We can just add these slots on at will, and they can hold both values and functions.

// Functions are callable objects
// with properties

var timesCalled = function timesCalled(){
  times.calls = times.calls || 0;
  times.calls++;
  return times.calls;
};

timesCalled() // => 1
timesCalled() // => 2

// (a poor example but it serves my purposes)

// Functions really are special in JS
// Just look at jQuery AJAX callbacks
$.ajax({
  success: function() {
    alert("Great success!");
  },
  failure: function(){
    alert("Oh noes!");
  }
})

// Inheritance through prototypes...

original = {
  title: 'This is a bad placeholder example',
  action: function() { /.../ }
  };
copy = Object.create(original);

Every wonder where these ideas came from?

I wondered!

A few years ago when I got back into doing web work, I was and still am mostly doing Rails.
This was when Coffeescript was brand new and it was big news that it had been pulled into Rails as a default.
Now this surprised me because even though I think Coffeescript is cool, in all this discussion about it people were really harping on Javascript.
When people griped about JavaScript back in the early 2000s, they were just misguided, I thought.
They hadn't seen what you could do in the browser with AJAX.

But now the arguments I'm hearing about JavaScript are about its strange inheritance mechanisms.
I'm noticing a big thing that people are pushing in Coffeescript is this class wrapper it gives you on top of native JS inheritance.

However!
The thing is, as full of land mines as JavaScript is, and as much as some of my colleagues like to malign it,
JavaScript is pretty fun.
Deep down I know Mr. Eich must be a pretty smart guy, because for all its warts, there's something about JavaScript
that I just can't put my finger on that makes it really fun.

So I started looking into JavaScript's influences.

Functional programming and Scheme
I found that Scheme's influence had gotten a lot of attention lately.
(At least in the circles I'm familiar with, probably with the rise in interest in functional programming)


But I was really curious about JS's unique approach to OOP.
There's just some features there that you don't find elsewhere.

I wanted to know where these ideas came from.

JavaScript's other big influence.
As Eich was working on LiveScript, soon to be called JavaScript another programming language was making waves.
It was meant to be the successor to Smalltalk, the next big OOP thing.

Self
====

  SELF is an object-oriented language for exploratory programming based on a small
  number of simple and concrete ideas: prototypes, slots, and behavior. _Prototypes_ combine inheritance
  and instantiation to provide a framework that is simpler and more flexible than most object-oriented
  languages. _Slots_ unite variables and procedures into a single construct. This permits the inheritance
  hierarchy to take over the function of lexical scoping in conventional languages. Finally, because
  SELF does not distinguish _state from behavior_, it narrows the gaps between ordinary objects,
  procedures, and closures. SELF’s simplicity and expressiveness offer new insights into objectoriented
  computation.

  (_Emphasis mine_)

  Self: The Power of Simplicity, Ungar and Smith, 1991

Sounds familiar right?

Where did _these_ ideas come from then?
We can get into Self's influence on Javascript in a minute, but let's take some time to talk about the forces that brought about Self.

Let's set the stage.
It is the 1980s and Smalltalk is king.

Smalltalk
=========
- THE OOP language
- Alan Kay, Xerox PARC
- Hugely popular, hugely influential

Smalltalk
=========
- Managed environment
- message passing (from Simula)
- meta/eigenclasses
- "Everything is an object"

Smalltalk
=========
- major ideas like "everything is an object" are present in Ruby, Python
- syntax influence on Objective C

So how was Self trying to improve on this? (and what prompted Ungar and Smith to try to improve upon it)
As early as 1986, six years after Smalltalk people are already noticing some problems with classical OOP.

"When designing a new object, one must first move to the abstract level of the class, write a class definition, then instantiate it and test it, rather than remaining at one leve, incrementally building an object."

  (from A. Borning "Classes versus Prototypes in Object Oriented Languages", 1986)

This is something we completely take for granted in Javascript with object literals
He goes on to talk about meta-classes and the difficulty this presents new learners

"The emphasis on classes in the programmer's interface is at odds with the goal of interacting with the computer in a concrete way."

"For an object to have a distinct message protocol, a separate class must be created for it."

  (Borning, continued)

One really succinct way that David Ungar, one of the authors of Self sums this up is,
"Everything is a tool for dealing with objects, not the objects themselves."

Enter the 90s and Self
This was the void Self was trying to fill.
Self was to be the next Smalltalk, the next step in the evolution of OOP.

(Play a portion of the original Self video)

-  Programming as experience
-  Intuitive concreteness of the object
-  No distinction between running and editing a program

So this was the state of OOP when Eich was developing JavaScript.

Now, for some practical notes.

...Or "What I learned while researching Self"

I thought this talk would be about Prototypes vs. Classes.
Makes sense right? People were arguing over JS's strange inheritance etc.
I was coming from the Ruby-school of OOP.
Where Coffeescript was this saving grace that was going to fix the weird OOP of Javascript.
And I thought I'd be really digging and looking for an argument for prototypes.

But really, prototypes have already been embraced.
I found there wasn't really an argument for prototypes that hadn't already been argued pretty adeptly.
There are some really smart programmers out there, people way smarter than me, who were already making this argument.

Douglas Crockford
  "Five years ago I wrote Classical Inheritance in JavaScript. It showed that JavaScript is a class-free, prototypal language, and that it has sufficient expressive power to simulate a classical system. My programming style has evolved since then, as any good programmer's should. I have learned to fully embrace prototypalism, and have liberated myself from the confines of the classical model."

  http://javascript.crockford.com/prototypal.html (from 2006)

2006, yikes! I'm really late to this party.

Eric Elliot
  Classical Inheritance Is Obsolete – How To Think In Prototypal OO

  http://ericleads.com/2013/06/classical-inheritance-is-obsolete-how-to-think-in-prototypal-oo/

  https://github.com/dilvie/stampit

(see, I'm not SO late to the game!)

Programmers who use Javascript extensively probably know way more about prototypes than I.
We're already leveraging this power, maybe without realizing it, in a very common callback pattern.
(Passing object literals in callbacks)
The power of prototypes is this having an object at hand at all times.

Cognitive burden
This is another thing that Ungar returns to again and again in papers and talks.
There is just a lot of cognitive overhead when you're dealing with classes and you're immediately dealing with
some indirection from the object at hand.

But I shouldn't have been surprised.
Reading all the literature from Borning up to Ungar and Smith they all raise the question
Do we need classes? Are prototypes supposed to replace classes?

In the 90s this was just a question.
But they made this assertion, basically "If classes are important, programmers will make them."
Basically, classes aren't bad, they just aren't necessary for everything a programmer does.
Prototypes are more basic, and since we can implement classes with prototypes, let's experiment with making this more basic component available to the programmer.
Contemporary JavaScipt is this hypothesis made manifest.

Because of prototypes, JavaScript is dynamic enough for us to implement whatever kind of inheritance we want.
Setting aside the `new` keyword and constructor functions, programmers implemented the class interface they wanted. (See Coffeescript, various libraries for implementing classes and class-like objects.)
So in a sense contemporary Javascript programming answers, in the practical every-day application world, many of these questions.
And they were right! Classes are the right tool for the job, but prototypes are more flexible. As we've needed classes,
we've build them in Javascript. But you can't argue against the simplicity of the object literal.
What I'm trying to say I think is that prototypes are more flexible than classes, but there's no need for us to be dogmatic about them either. We can have our cake and eat it too.


However, I don't want to get too hung up on prototypes either.
Self was more than Smalltalk with prototypes.

Self left a spiritual influence on JavaScript as well. (To speak nothing of the technical legacy of Self)
- Rapid prototyping
- Programming as experience
- Spirit of experientation and exploration

Think about Atwood's law. "Whatever can be done in JavaScript will be done."
David Ungar gave a great talk in 2009 after he received the Dahl-Nygaard award for his work on Self.
It's a great talk to watch, you can see it on Stanford's YouTube page.
The whole talk is full of great quotes but two really stick out to me.

"If you're going to be creative and innovative, you can't be serious."

"With great people, you can do anything! Don't waste them on the possible!"

This is why I think JavaScript is so fun, it's why Atwood's law is so funny and so true
JavaScript's flexibility, combined with its ubiquity somehow drives people to do incredible things.
(Some of them more practical than others)

It has to do with the choice to use prototypes, but a core contribution to JavaScript and the programming world at large that Self gave us was this spirit of experimentation and creativity and innovation.

The thing you have to remember about Self was that these guys weren't just trying to make programming easier.
They were trying to change what programming was.
And they didn't stop to think, "well, this is difficult or this is impractical."
They dreamed up the world they wanted and they built it.

As Ungar says in that same talk, "There's nothing like it, even today."


