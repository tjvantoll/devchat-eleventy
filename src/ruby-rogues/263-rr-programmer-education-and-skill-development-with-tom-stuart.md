---
layout: layouts/post.njk
title: >
  263 RR Programmer Education and Skill Development with Tom Stuart
date: 2016-06-08 07:00:32
episode_number: 263
duration: 01:03:48
audio_url: https://media.devchat.tv/ruby-rogues/RR263ProgrammerEducationandSkillDevelopment.mp3
podcast: ruby-rogues
tags:
  - ruby_rogues
  - podcast
---

## Check out [Ruby Remote Conf](https://allremoteconfs.com/ruby-2016)!

&nbsp;02:39 - Tom Stuart Introduction

- [Twitter](https://twitter.com/tomstuart)
- [GitHub](https://github.com/tomstuart)
- [Blog](https://codon.com)
- [Ruby Rogues Episode #120: Book Club: Understanding Computation with Tom Stuart](https://devchat.tv/ruby-rogues/120-rr-book-club-understanding-computation-with-tom-stuart)
- [Understanding Computation by Tom Stuart](https://computationbook.com/)
  03:17 - “Computer Scientist”; [Computer Science](https://en.wikipedia.org/wiki/Computer_science)04:17 - Static Typing, Type Systems
- [Tom Stuart: Consider Static Typing @ RubyConf Australia 2015](https://codon.com/consider-static-typing)
- [Matz's Opening Keynote at RubyConf 2014](https://www.youtube.com/watch?v=85ct6jOvVPI)
- [The Halting Problem](https://en.wikipedia.org/wiki/Halting_problem)
  18:44 - The Direction, Adoption Curve, and Use of Ruby33:36 - Multicore Growth and Concurrency =\> What programming language should I learn?
- [Moore’s Law](https://en.wikipedia.org/wiki/Moore's_law)
  &nbsp;Picks
- [Halting State by Charles Stross](https://www.amazon.com/Halting-State-Ace-Science-Fiction/dp/0441016073) (Sam)
- [The Belgariad by David Eddings](https://en.wikipedia.org/wiki/The_Belgariad) (Chuck)
- [Fully Alive: Discovering What Matters Most by Timothy Shriver](https://www.amazon.com/Fully-Alive-Discovering-What-Matters/dp/0374535825) (Chuck)
- [The 8000th Busy Beaver number eludes ZF set theory: new paper by Adam Yedidia and me](https://www.scottaaronson.com/blog/?p=2725) (Tom)
- [Martin Kleppmann: Staying in Sync: from Transactions to Streams](https://www.infoq.com/presentations/event-streams-kafka) (Tom)

### Transcript

**SAM:&nbsp;** Just be warned that if things really grind to a halt, I'm going to bring up Cucumber.

**TOM:&nbsp;** Oh god.

**CHUCK:&nbsp;** [Laughs]

**_[This episode is sponsored by Hired.com. Every week on hired they run an auction where over a thousand tech companies in San Francisco, New York, and L.A. bid on Ruby developers providing them with salary and equity upfront. The average Ruby developer gets an average of 5 to 15 introductory offers and an average salary offer of $130,000 a year. Users can either accept an offer and go right into interviewing with a company or deny them without any continuing obligations. It's totally free for users. And when you're hired, they give you a $1,000 signing bonus as a thank you for using them. But if you use the Ruby Rogues link, you'll get a $2,000 instead. Finally, if you're not looking for a job but know someone who is, you can refer them to Hired and get a $1,337 bonus if they accept the job. Go sign up at Hired.com/RubyRogues.]_**

**_[I'm excited to tell you about a new sponsor to the show, Rollbar. One of the frustrating things about being a developer is dealing with errors. Ugh. Relying on users to report errors, digging through log files to debug issues, or a million alerts flooding your inbox ruining your day. With Rollbar's full-stack error monitoring, you get the context and insights and control you need to find and fix bugs faster. It's easy to install. You could start tracking production errors and deployments in eight minutes or less, or automatically create new issues in GitHub, JIRA, Pivotal Tracker, et cetera. They have a special offer for Ruby Rogues listeners. Go to Rollbar.com/RubyRogues to sign up and get the bootstrap plan free for 90 days. That's 300,000 errors tracked free. Give Rollbar a try today. Go to Rollbar.com/RubyRogues.]_**

**_[This episode is sponsored by Shippo. Shippo is a shipping API that connects you with over 15 different shipping carriers such as FedEx, UPS, USPS, Canada Post, and UberRUSH in one integration. You can use Shippo's APIs to compare shipping rates across carriers, print discounted labels, validate shipping addresses, track packages, and power your shipping in many different ways. You can connect directly to the API or use the provided Shippo Ruby gem to print your first label in a few minutes. The Shippo API is free to use. You only pay for the actual shipping label and a five-cent label fee. Sign up by going to GoShippo, that's G-O-S-H-I-P-P-O dot com slash Ruby Rogue to get six months with zero label fees.]_**

**CHUCK:&nbsp;** Hey everybody and welcome to episode 263 of the Ruby Rogues Podcast. This week on our panel we have Sam Livingston-Gray.

**SAM:&nbsp;** Hello from sunny Portland, Oregon.

**CHUCK:&nbsp;** I'm Charles Max Wood from DevChat.tv. Go check out RubyRemoteConf.com. We have a special guest this week and that's Tom Stuart.

**TOM:&nbsp;** Hello from medium sunny London.

**CHUCK:&nbsp;** So, we've had you on the show before and we'll put a link to that in the show notes. But do you want to introduce yourself since it's been a while?

**TOM:&nbsp;** Yeah, sure. I'm Tom. I'm a Ruby developer. At the moment I kind of work as a freelancer/consultant/floating developer/computer scientist guy. I was on the show I think nearly three years ago. [Chuckles] Can that be right?

**CHUCK:&nbsp;** It can be. I don't know exactly the dates on that, but yeah. It can be.

**TOM:&nbsp;** Let's say yeah, I wrote a book called 'Understanding Computation' and since then I've been doing more Ruby and doing more mathematics and giving a bunch of conference talks. So, that's who I am.

**SAM:&nbsp;** It's interesting that you identify yourself as a computer scientist. At least the few times that I've asked around, those of us with Computer Science degrees are decidedly in the minority in the Ruby community.

**TOM:&nbsp;** Yeah, I get that. I get that impression. But I don't know. I guess that's just [chuckles] how I think of myself and increasingly it feels like that's the kind of differentiating skill that I can bring to the work I do is just actually having that background in mathematics and computer science and just having a slightly different perspective on things. Most of the best programmers I know don't have any computer science background. So, it's actually a way to be slightly different.

**CHUCK:&nbsp;** Sam, do you have a Computer Science degree?

**SAM:&nbsp;** Yeah, I have a Bachelor's. I actually started my programming career as a self-taught Access developer. I've just outed myself. But then I went back after a couple of years to get the CS degree.

**CHUCK:&nbsp;** Ah, gotcha. I have a Computer Engineering degree. Does that make me part of the club?

**SAM:&nbsp;** We'll let you into the lobby.

[Laughter]

**SAM:&nbsp;** But you know, you're right. It does give an interesting lens through with to view some of the discussions in the Ruby world. As for instance you talk, 'Consider Static Typing' which talked a little bit about Matz's keynote at RubyConf, what was it, 2014?

**TOM:&nbsp;** Yeah, that's right. That was a talk I gave I think last year. And actually I don't quite know, when I gave that talk it was all about trying to unpack what Matz had said in his keynote and what his plans were for Ruby 3 just based on the stuff that he'd said at RubyConf. And so, that was a little bit of kind of reading the tea leaves and trying to figure out what he was thinking and where they were going to go with that stuff. And then since then I don't really know [chuckles] I must admit I haven't been keeping up with it that much. I assume that work is being done. But yeah, that was really just a moment in time trying to figure out what might be happening here, what might the words that he used to describe the possible static type system actually mean and what might the implications for Ruby be and stuff like that.

But yeah, just you mentioning it now makes me realize that if someone asked me now what my opinion was, how my opinion had changed since I gave that talk, I think I'll have to be like “Oh, well I don't actually know.” I don't know what the latest about that is. In fact, I don't even know if Matz has said anything at all about static typing since then. But I guess at some point maybe the next RubyConf keynote we'll find out all of the magical answers. Unless it all came out in RubyConf last year and I just didn't know about it.

**SAM:&nbsp;** No, I think the big highlight of that one for me was the lonely operator which makes it easier to ignore nils. But…

**TOM:&nbsp;** Ah, right. Everyone wins.

[Laughter]

**SAM:&nbsp;** Nobody wins.

[Chuckles]

**CHUCK:&nbsp;** I can just imagine. I talk to Rubyists about static typing and they're all “No!” There's weeping and wailing and gnashing of teeth. And “We can't do that. It's a dynamic language and we like it.” And I'm really curious just… I do see some benefits to static typing. But most of the typing systems I'm into these days, if they have a typing system beyond the rudimentary “This is a number and this is a string” that Ruby does have, it's in TypeScript. So, it's more that it enforces it and it checks it but it's not really a strong static typing system.

**TOM:&nbsp;** I think you're right about people being resistant to it. I imagine people who use Ruby, they kind of like the fact that you don't have to compile it and you don't have to deal with, beyond, as long as you haven't made any syntax errors you can pretty much write whatever code you want. And then if you have a bug in your code that's sitting there quietly for months and months and it's not until three months down the line that some exceptional condition triggers some weird thing that you hadn't spotted, I think people kind of like that. And I think it's going to be a hard sell to get any kind of static typing into Ruby. It's not immediately obvious to me, but it's a thing that is desirable.

It's I think in general, static typing is good. And I like statically typed languages and I think they work really well. But whether that's something that's going to work for the language that Ruby is, I don't know. Yeah, at this stage I guess we're still in that kind of wait and see phase of seeing like “Is anything actually going to happen? Or is this just going to be a thing that Matz talked about one year and then everyone freaked out and then he never mentioned it again?” So, I guess we'll have to see how that plays out. But ultimately if you're a Ruby developer and you wish that you were programming in a statically typed language, an easier option than waiting to see what happens in Ruby is just to switch to a statically typed language. And then you get a whole different bunch of trade-offs, right? So…

**CHUCK:&nbsp;** Mmhmm.

**SAM:&nbsp;** Right.

**TOM:&nbsp;** I guess it's just history will decide whether this is something that becomes relevant for us. But I don't know.

**CHUCK:&nbsp;** I think the strength of something like TypeScript is you can actually specify the interface of the type. So, you can say it has to have these attributes. And the attributes can be functions or methods in Ruby's case or they can be actual attributes that hold some value. And so, that being said I think that makes a lot more sense than having a strong typing system where you're saying “It has to return an object of this class” and instead say “It has to respond to this interface.”

**TOM:&nbsp;** Right. And that kind of structural sub-typing stuff of thinking about the types of things as being about what methods they respond to and things like that is one of the things I discussed in that talk. And I think that's one of the things that Matz was gesturing towards when he gave his RubyConf keynote, however long ago it was. I don't know. People are generally very resistant. A lot of people have had bad experiences with static type systems. I know I have.

**SAM:&nbsp;** Right.

**TOM:&nbsp;** But it's easy to just wave your hands and say stuff that isn't very meaningful. But in the abstract the idea of a static type system is to take information out of the brain of the programmer, like all of the stuff that…

**CHUCK:&nbsp;** Yes.

**TOM:&nbsp;** The programmer knows about what their expectations are, what invariants they're expecting to see in their code, and actually writing that stuff down in the concrete syntax of the program. And that in itself as a broad idea is good. And then its' just the actual concrete implementations of that idea that people have trouble with. Either because well people will complain that some type systems are not smart enough. “I'm frustrated because my type system doesn't understand the invariants and the constraints that I have in my head. There is no syntax that lets me write down what I know about the type of this value. That's frustrating.” And the other end of the spectrum, languages like Haskell, people get frustrated because they think the type system is too powerful and knows too much and has too…

**SAM:&nbsp;** And out to get them. [Chuckles]

**CHUCK:** &nbsp; Yeah.

**TOM:&nbsp;** Right, exactly. And then you get this kind of errors from the type checker that are so verbose and complicated that it feels like it's overrun your ability to actually understand the code you're writing. So, I'm sure over time language design is going to hone in on that sweet spot. And I think you can see with the success of languages like Swift and Rust that those do live in a nice sweet spot where they give you a decent amount of safety and let you express a decent amount of information especially with the borrow checking stuff in Rust. It understands quite well some of the aspects of the way that you're using those values and when they get allocated and when they can be safely deallocated and stuff like that. But without going down this really [baroque] route of having a massively complicated type system. Although there are people who find the borrow checking stuff in Rust to be more than they want to think about when they write a program. So, maybe we'll always have this kind of spectrum of languages that appeal to some people are naturally more conservative and some people are naturally more, want to be free.

So, a lot of people are having conversations at the moment about the direction that Ruby's going in or what the future of Ruby is or I guess even aside from the conversations about Rails and Rails 5 and the direction of Rails. There's a general background noise of people talking about what's the future of Ruby going to be, what languages are we going to be using in five or 10 years, and how do we make that be Ruby or not? And so, I guess I'll be interested in another three years [laughs] to A, if Ruby Rogues still exists, to come on and do like a well, you know, has Ruby become more or less popular? Has it changed? Has it… are there more people who are interested in it? Is it something that's gradually becoming less popular as people are building larger systems or more complex systems or systems with higher performance requirements? Or I guess only time will tell whether the sort of happy place that Ruby has occupied in the language landscape and completely ignoring static typing as it has up until now, will it be able to continue doing that? Will Ruby 3 also completely ignore static typing? I don't know.

So, at the moment it feels like we're in a little bit of an intermediate stage where we've had a major… Ruby 2 came out a while ago. And Ruby 3 is going to come out at some point. But right now none of us know what that's going to look like. So, I think the potential speculation about what features might it have that are gesturing in that direction of Rust or of Swift or any of those other kind of statically typed but not all in on static typing languages like those… it'll be interesting to see how much Ruby resembles those things and how much it just completely ignores them and goes off in its own programmer happiness direction, you know?

**SAM:&nbsp;** Yeah. Well, one of the impressions that I took away from that keynote was that his idea of soft typing more or less had to do with looking at the methods that got sent, or the messages, excuse me, that got sent to an object in a particular method. And using that to assemble a bag of methods or an interface of sorts that that object must implement. It has to respond to these three things because they get sent during this method. And I didn't get the impression that it was going to be possible in Ruby to do much more than that, which doesn't seem like a particularly strong type system to me. But maybe it's better than what we have already.

**TOM:&nbsp;** Yeah, possibly. Even at the time I spent quite a lot of time thinking about it and talking to people about it. And it wasn't entirely clear to me what the trade-off is going to be there in terms of, is this really going to provide that much benefit? Is it really going to be able to catch very many… ultimately what you want is to be able to catch these runtime, sorry, compile-time mistakes ahead of runtime. And it wasn't immediately obvious to me that it was going to be able to do that without sacrificing some of the features of Ruby that people really like.

**SAM:&nbsp;** Right.

**TOM:&nbsp;** The ability to dynamically define methods and support method missing and all that kind of stuff. At this stage we are living in a world where Ruby 3 really does need to be able to run Rails. That's important.

**SAM:&nbsp;** [Laughs] Right.

**TOM:&nbsp;** [Laughs] If they ship a version of Ruby where all of the language features that Rails uses are not supported then I don't think that's going to… it's going to be like a… I was going to say it's going to be a Python 3 situation. But actually I shouldn't say that because A, I don't know anything about the Python community and B, it does seem like people are actually adopting Python 3 now. For the longest time it felt like everyone was stuck on Python 2 forever. But I check back in periodically and it seems like Python 3 is finally properly taking hold. It's kind of like IPv6. If you wait for long enough eventually the new thing is going to claw its way into your consciousness. So…

**SAM:&nbsp;** [Laughs]

**TOM:&nbsp;** Maybe that's how it's going to be with Ruby 3. But not if it doesn't run Rails.

**SAM:&nbsp;** Right. Well, you raise an interesting point there about the dynamic extension available in Ruby where you can add methods to a class or even to an individual instance of a class or an object I should say. And given that and how much wacky stuff can happen on the fly at runtime, I wonder if deciding what interface an object has when it enters this call is more or less equivalent to the halting problem.

**TOM:&nbsp;** Yes, I think so. Ultimately the stuff that you really want to know about your program may in the end be undecidable. Obviously if your language is Turing-complete, then there are always going to be things that you can't predict ahead of time. There are always going to be thing where the only way you can figure out what's going to happen is to run the thing. And so, with a static type system we're always looking to try and constrain the programs to some kind of nicely understood subset of those behaviors so that ahead of time the compiler can actually check some of the properties of the program. But I think you're right. I think it would be very, very easy to come up with a Ruby program where the ability to check whether a particular object satisfied some particular set of supported methods was equivalent to deciding whether a program was going to halt or not.

And so, yeah at the time it felt to me like a very difficult challenge to retrofit an existing language like Ruby that's so free and plays fast and loose with the whole idea of… it doesn't even make sense to talk about classes and methods in some respects because compared to a language like C++ for example which if you de-sugar it enough times is ultimately just like a load of virtual method tables and you're ultimately just compiling stuff down to when you call this method on this thing that's just running this function. And Ruby isn't like that or you know, Ruby is incredibly dynamic and incredibly like “Well, we're just going to Smalltalk style send messages. And when those messages arrive maybe something different is going to happen every single time you send that message.”

And so, it seems in principle, it seems very hard to me to come up with a static type system that's able to deal convincingly with, well with the interesting problems. It's easy enough to have a type system that can tell you that a function's going to return an integer so that when you call it and you add another integer onto the result it can tell you that that's not going to go wrong. That stuff is fairly straightforward. But it's…

**SAM:&nbsp;** Right.

**TOM:&nbsp;** The long [table] of other things that we want to be able to do in Ruby programs and in Rails applications and stuff that I think are going to be the real challenge. So, I wasn't particularly optimistic when I gave that talk just over…

**SAM:&nbsp;** [Chuckles]

**TOM:&nbsp;** Over a year ago. And I remain not particularly optimistic now because I don't know that there is necessarily the, I don't know what the word is. At the time I was saying that I thought it was more like a PhD thesis than a pull request.

**SAM:&nbsp;** Right.

**TOM:&nbsp;** And I still feel like that. I think that it's the kind of thing where it's possible to incrementally improve an open source programming language. And sometimes to take large incremental improvements, large steps, so things like making the garbage collector better, changing from a, and it's just a straw man, but changing from a stop the world garbage collector to one that's more incremental and then to one that's generational. And you can keep turning the crank on the garbage collectors and you can keep profiling and then tuning them and exert selective pressure on the garbage collector and have a hundred really smart nerds who are all trying to make it faster and reduce memory pressure and stuff. Those things do tend to incrementally better over time.

But things like a type system don't really work that way. That needs to be a kind of, especially when you don't have a static type system to begin with, it really does need to be a big bang. You need to just say “Right, we're going from zero to this.” And the thing that you're going to really has to work. And so, it's very hard to see. Well, it's hard to imagine who in the world is going to do that. I don't think Matz is going to do it. I might be wrong. Maybe he has the time and the energy to undertake a project of that scale. But I kind of doubt it. I expect that his life is busy. So, I don't know. I don't know if someone out there is going to emerge from a cave and say that they figured it out. I don't know if a company is going to decide that they're going to earmark five million dollars to fund a research project for a whole bunch of people to work on this. It just doesn't seem like something that's incredibly likely to happen. But I'm not super pessimistic about it. But it just, it's one of those things that would make me happy if someone did it. But I don't have the time and the energy to do it. And I don't know anyone else who does.

**CHUCK:&nbsp;** I kind of want to go back a little bit to an idea that we were talking about before with just the direction of Ruby and then the adoption curve of Ruby. Are we still going to be using it in five years? I've talked to a lot of people who ask me periodically, especially since they know I have one foot in the Ruby community and one foot in the JavaScript community. It's like “Well, is Ruby still something worth picking up? Is Rails still something worth learning?” And I typically tell them yes. And then their response is something along the lines of “Yeah, but from what I can tell the Ruby community is not growing.” And from what I can tell, I can see that it is growing and I can see that maybe JavaScript's growing a little bit faster. Which is why percentage-wise on GitHub or what have you, you see more stuff coming out in JavaScript than in Ruby.

But I'm curious what your take is on that, as far as how much of Ruby remaining relevant in several years is going to happen versus people moving onto the next cool or interesting thing. Because there is a lot of cool stuff happening in JavaScript these days. And I think that's part of the appeal that gets people moving over.

**SAM:&nbsp;** Well, I think it's important to point out as part of answering that question that the metrics that we have for popularity are all relative to other languages.

**CHUCK:&nbsp;** Yeah.

**SAM:&nbsp;** So, it may be the case that JavaScript is gaining percentage points a little bit faster than Ruby. But at the same time, there are always a bunch of new programmers entering the field. So, even if our relative percentage points are declining somewhat which they may be, we're still adding lots of people and there are still lots of jobs. So, what do you think, Tom?

**TOM:&nbsp;** I agree with what you both [chuckles] just said. You know, I think there are a few obvious things to say, which are that Ruby went through this initial… I started doing Ruby a decade ago. And well, I guess over a decade ago actually. And there was obviously a period in the late noughties where it felt like the rise of Ruby on Rails was fairly meteoric. And everyone was hiring for it. And now we've gone into a post-youth stage. I hesitate to say middle-aged. But it's kind of the language has matured and the community has in most respects matured. And we're now in this kind of comfortable middle age I suppose where it's no longer a risky prospect, or at least not in the way that it used to be, it's no longer a risky prospect to base your startup or your new business on Ruby or on Rails.

I remember in London in the noughties there was only a small number of companies in London who were using Ruby. And so, there was a real sense of when you went to the London Ruby user group meetups it was a small group of people. And there was something unique connecting you all which was that you were all enthusiastic about this programming language that other people weren't using and people spoke really excitedly about “Oh, have you heard this website uses Ruby or this company is using Ruby internally?” And it was like a real big deal and people felt that they had a [inaudible] emotional connection to anyone else who was in the same small boat as them. And those days…

**SAM:&nbsp;** Yeah.

**TOM:&nbsp;** Are long gone, right?

**SAM:&nbsp;** Mmhmm.

**TOM:&nbsp;** It's no longer… I live in Shortage in East London. I can't throw a rock out of my window without hitting a Ruby developer. You might be right that there are more JavaScript developers. I think there will always be more JavaScript developers. But Ruby has reached a point now where it's become more of a safe option. And I think the people who, it depends what attracted you to Ruby in the first place I think. Because there was a point in time where Ruby had that kind of novelty around it. And if you're a person who is attracted fundamentally to novelty then maybe Ruby attracted you because it was the new shiny. Whereas now if you're that person, then I don't see why you would want to continue using Ruby because like Chuck said, there are loads of interesting new things you can go and make stuff in. Like I mentioned, in Swift or in Rust or in Elixir or there are loads of other cool new things.

And yeah, there's cool stuff happening in JavaScript. JavaScript is, despite in many respects being an old language, to me JavaScript feels, has more of an old and crusty feel than Ruby does. But it's seeing a lot of attention and people like Google and Apple are investing a lot of energy into it. And so obviously we're seeing the constant treadmill of new ECMAScript specifications and new features and all of the stuff that's buzzing around the zeitgeist around “Oh, we should have promises and async/await” and all of these kinds of fun language features are showing up into JavaScript. So, JavaScript although it is old and crusty in one respect is also much more of a sponge for new ideas. And obviously because every computer in the world give or take has got JavaScript on it, it's like an extremely tempting platform to deploy stuff onto.

So, I think that Ruby can't compete with that. Ruby isn't available on every computer. And it doesn't have quite the same… it's not new and exciting anymore. Well, it's not new anymore. Whether it's exciting or not is up to you. But I count myself as a… I'm not particularly attracted to novel things. I actually get quite exhausted by novelty. I have a limited capacity for learning new things. Every day there's only so much new…

**SAM:&nbsp;** [Laughs]

**TOM:&nbsp;** Interesting stuff that I can learn, right? And so, I am actually very cautious about the new things that I choose to learn because I'm conscious that I can never learn everything. And every new thing that I learn is using up a little bit of my mental energy. And so, I have to… and there's also this sense of it being a cumulative investment, right? Once you start learning a thing then you get good at it and you've developed your skills. And if you are constantly jumping to the next new thing, then you would just be a perpetual junior developer.

And so, when I became a Ruby programmer previous to that I was… well professionally the last language I had been paid to write was Java. But for the intervening years I'd been an OCaml programmer. So, I'd made this transition from being an industry… I'm trying to think of what the nice thing to say about Java is. Like Java is I guess is like a lingua franca. It's kind of a lowest common denominator. That sounds bad. I don't mean for that to be a slight. That's why Java ate the world is because it's a straightforward language that works that everyone can be taught in their undergraduate computer science classes. And everyone can immediately go and be productive with it. And that's an amazing feat of design and engineering.

But I transitioned from that world of just workman-like imperative computer programming into the world of doing OCaml functional programming and just thinking about programs in a totally different way. And so, for me to switch to Ruby I think I did that because… for a similar reason. Like when I switched from Java to OCaml, OCaml wasn't a new language. It was a kind of weird niche academic functional programming language which ironically is becoming more popular now. I hear people talking about OCaml and it kind of reminds me of the past. But it's feeling a bit hot and new now. But you know, when I decided to make that jump into Ruby it was because it had that feel of “Oh here's another different way of thinking about writing programs.”

I had done some Smalltalk in the past but never professionally, never in anger. And something about Smalltalk always felt a little bit… Smalltalk is actually very esoteric. I don't think it gets enough credit for just how esoteric a language it is. And so, it never quite managed to suck me into its gravitational pull. Whereas Ruby had this… it was quite new but it also felt more conventional. It felt a bit like Perl or Python but more interesting than those things. It captured my attention not necessarily for the novelty but for the way it wanted you to think about writing computer programs and the multi-paradigm… is it an OO language or is it a functional language or is it just a straightforward procedural language? It's kind of all of those things. And of course the culture around Ruby at least a decade ago was very fertile and had lots of interesting ideas in it. And that really attracted me. And it still does. I still really enjoy that.

So, I'm not quite at the point where… I certainly… most of the… well, I was going to say most of the work I do is in Ruby. Increasingly I'm getting to that inevitable point in my career where I spend less and less of my billable hours actually typing lines of code and more and more of those billable hours talking to humans and thinking about…

**CHUCK:&nbsp;** [Gasps]

**TOM:&nbsp;** Yeah, I know right?

**CHUCK:&nbsp;** Not humans.

**TOM:&nbsp;** [Laughs] They're the worst. But even so, I don't find myself itching to just dump Ruby and just pick up something new and cool. And I'm sure I will. There will be. I've dabbled in all of these languages I've mentioned. I've definitely brew installed them and gone through a few tutorials and kind of stroke my chin and nodded appreciatively. But none of them has quite got its hooks into my brain the way that Ruby did a decade ago or the way that OCaml did before that. Or even I guess the way that Java did before that, or the way that BBC BASIC did when I was four or five years old or whatever it was. So, that's quite a rambling long winded non-answer to the question. But I think it's right that… and I think right not just correct but also it's like I think that this is a thing that should happen. That Ruby has matured and it's become a little bit less volatile and it's kind of found its niche. People know what Ruby is good for. People know what Rails is good for. Most people what Rails is bad for. And people are…

**SAM:&nbsp;** Oh you would think that, mister. But no.

[Laughter]

**TOM:** But you know, it makes total sense to me that people… I really like, maybe I shouldn't say this on this podcast, but I really like JavaScript. I think it's as a language obviously it has a lot of historical cruft. It has a lot of problems. But again, I think JavaScript is also satisfyingly weird in the way that Smalltalk is. I don't think people give it enough credit for how weird it is. I think for all of its problems it is amazing it's deployed on so many platforms and that it really is… JavaScript, despite having virtually nothing in common with its namesake Java, it really has achieved the thing that Java didn't which is that you can run JavaScript programs basically everywhere. And Java, Sun Microsystems at the time, thought that the way that that was going to happen was by deploying the JVM to every microprocessor in the world. But it turns out that we don't need to deploy a virtual machine because we don't have to wait for every single computer on the planet to have a web browser on it. And then you have a kind of universal runtime for free. So, I think that's amazing. I think it's exciting.

I really like writing JavaScript. I think it's a simple, straightforward language for the most part. And I'm glad to see that it's maturing in a way that it has not before. It's still, I still find it very frustrating. I find all of the tooling is still not mature enough for me to feel happy. Every time I clone some repo from GitHub and I look at the readme and it says, “Well first you have to Grunt and then you have to Gulp and then some Broccoli and then Webpack” you know, like that.

**SAM:&nbsp;** [Laughs]

**TAM:&nbsp;** That stuff drives me up the wall. But that's what Ruby used to be like as well. We're very lucky that we've got Bundler. Rust is very lucky that it's got Cargo and it's going to take I think a bit more time before JavaScript really settles into that comfortable middle age that Ruby has settled into where everyone understands how package management works now. And you don't have to relearn some new tool every time you want to… because it's been a month since the last time you downloaded a piece of software. So, there are pros and cons to that kind of thing.

And so, I kind of look forward to the day when JavaScript has got that kind of maturity that Ruby has now. And I just hope that by that time it hasn't become so encumbered by all these fancy new language features that it becomes too difficult for people to understand. Because right now, or maybe a year ago would have been a more appropriate time to say this, right now JavaScript is pretty simple. And if someone who is just going out into the world and wants to do programming I think JavaScript is actually a pretty good choice. But as it becomes more, as they add more features to it and it gets a bit more computer science-y and a bit more programming language nerdy it might actually become more difficult for people to understand it. And I think that would be a shame.

So again, looking to the future I guess in a few years' time we'll see what has happened with that. And I hope that JavaScript remains a kind of fairly simple, fairly weird but understandable language that everyone feels like they can work in. I know some people are really worried about what the future of Ruby might be. But I don't feel particularly worried about that. Despite all of my computer friends being in the Ruby community I don't feel particularly, I don't know what the word is. Not invested. But if something happened and it turned out that actually it was time for me to switch to Rust then that's what would happen. Or if I decide I want to become an iOS developer and I just forget about writing web applications then that's fine. I'll still have all the friends that I have now. Maybe I'll make some new friends. It doesn't feel… I don't feel that my identity is completely tied up in that allegiance to a particular language.

**CHUCK:** Yeah. I will tell you that most of this question came out of basically two groups asking me similar questions. One is the experienced person saying “Is it time for a career change?” and they're concerned about whether or not they're going to be able to find a job in Ruby in a few years. But I see more jobs being created in Ruby these days, not less. I don't see those jobs going away. So, my answer to them is yes. And you kind of have touched around the edges of the reasons for that. And then the other is new people coming in. “Should I learn Ruby or should I learn something else?” And my answer to them is also the same thing. It's like, “Look. Which of these languages really gets you up and gets you going and gets you creative and gets you creating something?” And the way that you've talked about Ruby is really the way that I feel about it as well. And so, it's like “Look, if you're worried about whether or not you're going to be able to find a job, those problems exist in all these other communities. And the Ruby community is growing, not contracting.”

**SAM:&nbsp;** One thing that I was thinking about as I was preparing for this call was that I've been hearing for at least 10 years this idea that Moore's Law failed us in clock speed but it continues pushing multi-core growth. And that computer programming and language design especially are going to have to adapt to multi-core. And I know Ruby has this one process per core model that seems to be working okay for now. I'm not sure how well that's going to continue. I don't know if something that's more like Erlang or Elixir is going to maybe eat the world because it performs better in those environments. So, I'm not sure what market conditions would affect this conversation either.

**CHUCK:&nbsp;** I want to drive into this real quick. We have some new listeners that probably don't know what Moore's Law is.

**SAM:&nbsp;** Oh yes, thank you.

**CHUCK:&nbsp;** Can you run through that, Sam?

**SAM:&nbsp;** Yeah, so Moore's Law was an observation back in the 60s I believe that the number of transistors or the transistor density I believe doubled approximately every 18 months. And for a long time up until maybe the early noughties that meant that clock speeds kept getting faster and faster up until the point where we ran into this little constraint called the speed of light where it became difficult to get a signal all the way from one end of the chip to the other end of the chip and miniaturization was not keeping up with that by making chips smaller. And so, the solution that the industry went with was to rather than pack a single processor into a smaller and smaller space, they would just pack more processors onto the same die. Is that a fair summation?

**CHUCK:** Mmhmm. And a die is an industry term for the chip, basically.

**SAM:&nbsp;** Right.

**TOM:&nbsp;** And also, my pedantic contribution to that excellent explanation is the other problem is heat.

**SAM:&nbsp;** Right.

**TOM:&nbsp;** It's not just the speed of light. It's the fact that the real constraint there is that the closer you pack stuff together, the more heat needs to dissipate. And you reach a kind of, you reach a point where you actually can’t pack any more transistors onto that silicon without the whole thing just stopping working because of the amount of heat that it's generating. So, it's a combination of the speed of light issues and also the “How do we get this many transistors into this small an area without requiring every desktop computer to be circulating liquid nitrogen?”

**CHUCK:&nbsp;** Yeah well, and when we're talking about heat the thing that's interesting… so, this is what, when I said I was a computer engineering major in college, we were designing these chips. And so, we're taking about millionths or billionths of a meter essentially in these distances. And so, if you get them hot and they change their shape very much then the transistors on the chip are not going to be transistors [chuckles] anymore.

**TOM:&nbsp;** Right.

**SAM:&nbsp;** One big ground wire.

[Chuckles]

**CHUCK:&nbsp;** Yeah.

**TOM:&nbsp;** It's interesting the point being raised there about multi-core and concurrency and all of those issues.

**SAM:&nbsp;** Right. And I don't know JavaScript well enough to know how parallelizable it is. But I know that Ruby probably won't do very well until we do a lot more work on getting rid of the GIL.

**CHUCK:&nbsp;** So, do you want me to explain the argument there?

**TOM:&nbsp;** Please.

**CHUCK:&nbsp;** Because you'll hear people talk about JavaScript and they're like “Well, it's concurrent. And it does all this stuff.” And basically Node.js at this point has similar constraints to Ruby. It has threads but those threads are still bound up on the same chip just like in Ruby, has non-blocking I/O just like Ruby. The concurrency model is event-driven. And Ruby has that but most people don't actually use an event-driven system. And that's really where the primary difference is.

So there may be a model under which you could create Node.js where it would run across multiple cores. I haven't seen that and I don't know what the infrastructure and the underlying C, I think it's C++ programming under the hood looks like to make that all work. It uses the V8 engine and I don't know what constraints that puts on it as well. But JavaScript in many ways has similar issues to Ruby as far as being able to run across multiple cores. And I know I'm going to get yelled at about this but go look it up. It really is the way that it works.

**TOM:&nbsp;** Well obviously, the dominant model of JavaScript execution is a web browser. And in a web browser the expectation most of the time in most cases is that it's going to be single-threaded. And although concurrency in the sense of being able to have pieces of the program that can run in an unspecified or in out-of-order essentially, the idea that your program is made up of lots of pieces and those pieces are going to execute at some point but you're not sure what order they're going to execute in is I think has always been a very present concern for JavaScript programmers. And maybe less so Ruby programmers. But it is a thing that we do think about sometimes.

We do think about in something like a web application you do have to think about well, what if this action, this controller action runs before this other controller action? And in a JavaScript program you have to think very hard about if I've got all of these functions that are bound as event handlers or if I've got this thing that's a callback when the HTTP request completes then what happens if… there's a race now between that HTTP request completing and this other thing happening, user input, or whatever it is. So that kind of, having to think about your program, having an unpredictable order of execution is something that we all have to deal with.

But again, for the Ruby Rogues pedantry corner that's not quite the same as worrying about parallelism. Obviously those ideas are related. And if you have a program where it's okay for different bits of the program to run out of order, especially if the reason why that's okay is because you've removed data dependencies between those parts of the program, then it's nice and straightforward to run those different pieces in parallel. Like say Chuck, Ruby has EventMachine and various other options to allow you to do that kind of evented concurrency. That in a lot of ways makes it easier to write certain kinds of programs. But it doesn't necessarily… it gives you that performance improvement of I'm no longer blocking when I'm waiting for data to come from the disk or for data to come over the network. It doesn't do anything to improve the performance of CPU-bound computation.

Whereas if we had a sophisticated programming language that was able to… if in Ruby you're able to say “I have an array with a million elements in it and I want to map this proc over that array,” if Ruby was able to farm that task out by dividing the array into four pieces and getting each of four independent cores to process a quarter of the array each and then do a map reduce and recombine them at the other end, then that would be great. But there's no indication that Ruby is going in the direction of being a language that's able to express stuff like that. Ruby has side effects. It's very hard to tell whether that code inside your proc is referentially transparent or not. Is it safe to run that out of order? Or actually, does that proc increment a counter that is used on the next iteration? What you're actually mapping over that array is a thing that is incrementing a counter every time and concatenating it into a string or something.

So, the language doesn't really have the built-in ability for you to know that stuff like that is doable. Of course that doesn't mean that you're prevented from writing multi-threaded programs in Ruby. But then, it's all your problem. Now suddenly you've got to figure out how am I going to coordinate? Am I going to have some kind of shared global mutable state between these threads and just hope that they don't stamp all over each other? Which is kind of the situation if you're writing concurrent code in a language like Java. You just have to use the concurrency primitives built into the language and you have to use the features that the language has to build up.

Whether that means you're going to have some kind of classic concurrency mechanisms or if you're going to use, if you're going to build your whole program around “Well, I'm going to use persistent data structures. Everything is going to be immutable and so it's fine. I can share everything because I only ever sort of allocate new memory. I don't stamp over old memory” or you have some kind of actor model where you say “Well, I'm not going to have any shared memory at all and all of my little independent actors are going to communicate via messages” and stuff like that.

I don't know that Ruby is, Ruby has never been particularly, or at least in terms of the language itself there's not very much in it to suggest a direction. And there are plenty of things like Celluloid and EventMachine and all kinds of different user space if you like solutions to that problem. But the language doesn't get that involved whereas some other programming languages like yeah for example Erlang is obviously much more, it takes a much more opinionated stance on that and bakes that kind of stuff in right at the beginning.

Ultimately I think my feeling about it is a bit of a cliché which is that sometimes that's something that you need and sometimes it's not. It's that use the right tool for the job cliché. If you want to write a piece of software that's rooting a million phone calls for second, then by all means use that programming language that Ericsson designed specifically for that purpose. But if you're writing a low-traffic web application where a single thread on your VPS is going to be more than enough to serve the one request per minute that comes in… And there are a huge amount of applications out there like that, then the benefits…

**SAM:&nbsp;** True.

**TOM:&nbsp;** Of being able to write a simple imperative object-oriented program and not think about any kind of concurrency apart perhaps from horizontal scalability, it's the right decision. You don't… not everything has to be multi-core. If you are trying to write a AAA video game you have to think very hard about stuff like that. But if you're just trying to write, well I was going to say something trivial but even if you're just trying to write, if you were launching something like Instagram you could probably get away with building a kind of medium traffic social network without actually having to step up into the world of actors and things like that. But maybe that's just my… maybe I have a biased perspective because I don't work in that world very much. And maybe it's massively more important than I give it credit for.

**CHUCK:&nbsp;** Well, I know that several people have written systems, especially web systems. And in a lot of cases it is simpler just to use something like… so, let me back up because I kind of went down one road and then I kind of went down the other road. But basically… so first off I've played with Elixir and Erlang and I really, really like the actor model and the way that they have that set up. And in a lot of cases the fact that you can have something respond to requests and then turn around and farm it out to as many actors as you need, it's something that's really handy.

And in several cases I've also seen that you can make web requests, which is I think something that a lot of Rubyists do. I don't want to generalize too much but you can make those extremely fast and extremely efficient. But in a lot of other cases, I think you're right in the sense that you pull something together with Nginx and Passenger or Apache and Passenger or you do something where you use Nginx and proxy to Unicorn or something like that. It works fine. And basically then what you have is you have a bunch of single-threaded Ruby processes that all know how to reply to the same request and then their shared memory is effectively the database. This is the collection of data that we operate on, read from, et cetera. And so it doesn't really matter that you don't have this large amount of concurrency.

But at the same time, having looked at some of these Erlang and Elixir systems that do reply quickly and efficiently I can also see that there are definite trade-offs that you're making depending on what you need. Now that said, I think you've also made the point well that for something like a moderately trafficked social media site like you said, one, two, three, four servers is probably fine. And you could just load balance them. And that all works fine. When you get up to the point where you have thousands of servers and you can cut out a quarter of those by making them manage more efficiently by using a system like Erlang or Elixir, then I think in a lot of cases it makes more sense to go that way.

But ultimately when you're building up and you don't have the traffic, you don't have the constraints of having a very, very large system, then your cost is going to be driven by the amount of time it takes your programmers to write the code, not necessarily by the infrastructure you run it on.

**SAM:&nbsp;** That's sort of the classic argument for Rails, I believe.

**CHUCK:&nbsp;** Yeah.

**TOM:&nbsp;** Right, that makes sense. Not to, I don't wish to undercut the question in any way because I think it is an interesting and important topic. But at the same time, it reminds me that sometimes I think that people… Chuck you were saying about being asked by new developers what language should they learn. Should they learn Ruby or should they learn JavaScript or what's the hot thing? And I sort of feel increasingly that it's maybe a bit too much. People get a bit too much focused on that kind of thing. People obsess too much over as if you just have to throw your hat into one possible ring and then you have to become a JavaScript programmer or a Ruby programmer or a Python programmer or whatever.

As I inevitably age and become, have that combination of gaining in experience but also losing in energy and [chuckles] in some ways enthusiasm as time goes on, you kind of get maybe a bit more philosophical about things. It makes me, when people ask me those kinds of questions there is a temptation to do this kind of, “Well, let me show you a big product comparison matrix with 10 possible languages you could learn and let's see which ones have got ticks in which columns. Let's figure out what it is. Do you want parallelism or do you want evented concurrency? Or do you want low-memory usage? Do you want a garbage collector? Do you want memory management at all?” all of that kind of stuff.

But increasingly and especially as I alluded to earlier because I'm doing more and more work that is talking to humans and less and less talking to computers it makes me realize that really, the important skills for people to develop and the important things that they need to learn are not specific to any, and this is a cliché as well, but not specific to any particular language. And in fact it's, I find myself leaning more and more on how can I get people to learn to be, when people want to level up and become a better developer or they want to become a developer for the first time and they're trying to learn how to do that, I find myself trying to focus a lot more on encouraging them to be methodical in their approach to making things. And I think that the choice of programming language is sort of one or two orders of magnitude less important than that.

Which isn't to say it can't make a contribution. But I think people find it very, in some cases people find it very easy to pick up a new language especially if it's their second or their third programming language. Beyond a certain point you've kind of seen them all and maybe for the next application you're building it might be that using Phoenix and Elixir is going to make it a lot easier for you, or if you did it in Swift or in Rust or in Haskell or whatever. Obviously some languages are easier and harder to learn than others. But I think that stuff that is really hard to acquire is that kind of meta-cognitive sense of how do I approach writing a computer program? What is my, what's the rhythm that I have when I'm trying to write software?

And that's the thing that I find, I wish people would invest, consciously invest effort into developing those kinds of skills. And be maybe five percent more relaxed about what programming language they're doing it in. It's very difficult to convince people of that because they just want… they've already stopped listening to you. They just wanted an answer to the question what programming language should I learn? And so, to try and say, “Well, I'm actually going to answer a different question” is maybe not particularly convincing. But that's what I always…

**SAM:&nbsp;** [Chuckles]

**TOM:&nbsp;** Want to say to those people is “Well, learn whatever language you like. And then let's talk about how you can become a disciplined, methodical developer.” And I want to cut out those five to 10 years of frustration of realizing that all of the way that you were trying to do stuff that felt like the easiest and quickest way at the time is actually coming back to bite you. Let me light my pipe and pull up a chair by the fireside and tell you all of the things that you should be trying to focus on.

**SAM:&nbsp;** [Chuckles]

**TOM:&nbsp;** I think that naturally deemphasizes the role of programming languages in being a developer. Which isn't very good for click-baity arguments on the internet.

**CHUCK:&nbsp;** [Laughs]

**TOM:&nbsp;** But that is how I feel. [Laughs]

**CHUCK:&nbsp;** Well, I think it's interesting because, and this is what I generally tell people is that there are so many problems out there to be solved. And there are so many programming languages out there that can legitimately solve them. And there are trade-offs between all of them, sure. But because there are so many problems and so many different people trying to solve these problems, the solution isn't going to be the same solution for every person. And so, as you work through the problem, as you come to understand it and you understand what your tools are then you can select the right one. And for you it might be the screwdriver and for me it might be the hammer. And down the line we both have a house built.

**SAM:&nbsp;** Yeah. And you threw out a bunch of different language features Tom in your sort of imaginary feature matrix. And you did sort of go into this a little bit but I wanted to call out explicitly that what I think is the most important thing that was missing from that feature matrix is how easy is it going to be for humans, especially other humans who are not you, to take over and maintain this in the future? Because unless you're writing a throwaway app or something that you intend to support by yourself for the rest of your life, other humans are going to be the most important factor. And human cognition is the only constraint that isn't changing every couple of years anyway.

**CHUCK:&nbsp;** Yeah, but isn't that a measure of experience? I mean for example if you wrote all of the code in Ruby wouldn't it be easier for me to read it than for somebody who is well-versed in Python but not in Ruby?

**SAM:&nbsp;** Possibly. Some languages I feel do make it easier to make more expressive code than others.

**CHUCK:&nbsp;** I agree.

**SAM:&nbsp;** Like I would not want to try to write anything in Prolog for example. At least, well no, I don't think I need to qualify that statement. [Laughs] I really did not like Prolog when I tried it. But yeah, to the same point though, it's also possible to write bad code in any language, too. So, yeah.

**TOM:&nbsp;** I think you're right. I think that the way that I would always try and sell it to people is about reducing the cost of change. Everyone understands that. Developers understand it and businesses understand it. You can have a conversation with anyone about the biggest risk we have here is that we don't know what the future will bring. We know that all of our assumptions now are going to be wrong. And at some point we're going to need to change what it is that we're doing. And let's just accept that and now let's use that as the guiding principle for making our decisions. And so, that is, that obviously ties into making future maintenance straightforward and making it easier for people to understand the code in the future and stuff like that.

It reminds me of a turn of phrase that John Carmack used when he was talking about this. He said something about time-integrated future suffering. Like the idea that if you kind of, what's the area under the graph of from now until the end of time, how much suffering is this decision going to cause? And it's…

**CHUCK:&nbsp;** [Chuckles]

**TOM:&nbsp;** That's an interesting lens through which to guide the decisions that you're making. And that's the kind of stuff that I try to teach people when I'm trying to teach them to be better developers, is to focus on… people always want to just learn, what are the five secrets, or what are the 10 secrets, or what are the 50 top tips of writing Ruby code or writing a Rails app or writing JavaScript or whatever. And I think that all of those tips tend to come and go. And sometimes it's skinny controller/fat model and then the next time you reload the same blog post it's been changed to be skinny model/fat controller or whatever it is.

Whereas that general principle of we're trying to reduce that time-integrated future suffering, we're trying to reduce the cost of change, we're trying to… and everything else comes out of that. You're going to try and limit the amount of knowledge and responsibility in every piece of code because the less that every piece of code knows and the fewer responsibilities it has, the easier it is to change. We're going to try and make big things out of small composable pieces because that reduces the future cost of change. If we've got lots of small pieces and we understand those pieces well, that makes it easier to maintain every individual piece. There is a cost associated with that because now we have to understand how they're all plugged together. But on balance it's easier to change a small thing than it is to change a huge thing.

So, that kind of guiding principle I think is something that is important to me. And I think that we've been talking all the way through this podcast about almost the fashions. Things ebb and flow and things become popular and then become less popular and new things are born and other things become middle-aged and other things wither away and die. And I think when you've been working in the tech industry for long enough, you get to see that kind of circle of life and new things cropping up and old things dying out. And it's just the way that it goes. But there are some evergreen ideas and some evergreen principles. And I think all of the people who want to learn, I don't know, whatever, agile development or test-driven development or behavior-driven development or RSpec or Cucumber or whatever it is, all of those things ultimately tie back to this idea of how do we accept the fact that we're not going to know what the future brings? And so, we have to make decisions in light of the fact that we're probably going to be wrong.

So, on the assumption that what you're about to decide to do is wrong, what is the least painful thing that you can decide to do now so that when it inevitably turns out to be wrong later, you pay the lowest cost? So, I can't quite remember why that thought popped into my mind. But I think it was just thinking about all of this languages discussion and stuff. I think it's important to keep that perspective that as people go through their careers and as you mature as a developer I think that's the thing.

When I talked earlier about trying to incrementally invest in things and trying to pick things to get good at, I feel myself as having invested, I hope that I've invested more in that kind of set of skills and that judgment than in any one programming language or any one set of technologies. And so, I think when people are thinking about “Oh, a good developer is a good developer in any language” or “They should be able to pick up a new language in a week and just be good at it” I don't know how true that is. I think there are a lot of problems with statements like that. But I think there is a kernel of truth in the idea that someone who has found the strength of character to be able to deal with this like the world is constantly changing and you just have to make decisions not on the basis of what was the most compelling blog post you read last week or…

**SAM:&nbsp;** [Laughs]

**TOM:&nbsp;** What's the coolest feature of the language you're using right now but instead is like this laser-like focus on reducing the cost of change, it seems like that's likely to lead to more success over an infinite time scale.

**SAM:&nbsp;** Caught us off guard.

[Laughter]

**TOM:&nbsp;** I thought you might have a witty comeback. That you'd be like, “No, you're wrong.”

**CHUCK:&nbsp;** Okay. Well, let's go ahead and get to some picks. Sam, do you want to start us with picks?

**SAM:&nbsp;** Sure. I've just got one today. I was going to pick something else but then I was thinking about all this computer science-y stuff after watching Tom's talks. And it reminded me of a novel by Charles Stross. It's called 'Halting State'. And this is a near future. I'm looking at the back of the paperback now and it says it's in the year 2018. It’s a bit further off than that. But this is a sort of detective procedural novel written in a role-playing game sort of style. And it shows some interesting technology. It talks about a little bit about the sorts of things that might just be woven into our daily lives when all of us have augmented reality glasses strapped to our faces. And it's an interesting story.

The one thing I will say about it is that it is written in a bit of a literary gimmick. The entire novel is in the second person. All I will say about that is that you stop noticing it pretty fast, or at least I did. Aside from that, it's a really wonderful book. And if you like this sort of thing, Charles Stross has a bunch of other really fun novels that you will probably also enjoy.

**CHUCK:&nbsp;** Alright. I'm going to pick a couple of books as well. The first one is a fantasy series. I've read it before. I think I read it for the first time in junior high or high school. When I need some down time I turn on an audio book. And this is a series called 'The Belgariad' by David Eddings. Its' a fun series. I really, really have been enjoying it. I'm on the last book at this point. I've just kind of been listening to it all last week. And it was really superb. So, I'm really enjoying that.

The other book I have that I want to pick is called 'Fully Alive' by Ken Davis. And Ken writes, he starts out telling a story basically about his experience. He took his grandkids camping and his granddaughter got lost. And he started to realize what was important to him and how to live fully alive and what it means to live life to the fullest. And I listened to it on an audio book, too. It's about five and a half hours long. I'm probably going to listen to it again this week. I listened to it last week. Because it was just that good. And he really does dig into several areas of your life that you can focus on to live fully alive. And so anyway, it kind of touched me pretty deeply. And it's still something that I'm considering which is why I want to read it again so that I can get a little bit deeper into some of these thoughts.

So anyway, those are my two picks. Tom, do you have some picks for us?

**TOM:&nbsp;** I do have a couple of picks. Although they're not as exciting as your ones. I wanted to pick a blog post from earlier, the beginning of May, by Scott Aaronson who I mentioned last time I was on this podcast. But he's written an interesting blog post about a paper he co-authored. His blog post is called 'The 8000<sup>th</sup> Busy Beaver number eludes ZF set theory' which I know doesn't sound very compelling for Ruby developers. But it's really interesting. I recommend you read the post. And if you're interested go and read the paper. It's an interesting problem to see what's the smallest Turing machine that can be constructed where we know that we're not able to prove its behavior in a particular axiomatization of mathematics? Which sounds really dry and nerdy but it's actually kind of a fun programming language geek thing.

So, if anyone out there is interested in the theory of computation this is by far the most interesting theory of computation thing that's happened in the last couple of years. So, I really enjoyed reading the paper. It's got some clever ideas in it. They've got a cool way of encoding stuff into a Turing machine that makes encoding a big string literal essentially into a much smaller number of Turing machine states. It's got all kinds of fun engineering problems to Turing machine design issues. And it's just an interesting result. It's a nice little piece of data about the universe. It's like finding a constant about the universe. So, that was interesting and fun.

And I also just wanted to mention a presentation by Martin Klepmann called 'Staying in Sync: from Transactions to Streams'. It's a presentation that he gave InfoQ which is about, and it kind of relates to the stuff we've been talking about. It's about how you can make distributed systems work in a slightly different way. So, rather than trying to have lots of different systems that are all trying to synchronize their state by using things like distributed transactions, if you want to keep your database and your full-text index and your Redis instance all synchronized with the same data, there are all kinds of complicated technical ways of trying to achieve that which aren't very good. But he talks very convincingly and very clearly for someone who doesn't know anything about it, he talks about a different way of approaching that problem by using a totally ordered stream of events, effectively a log. And I just found that very clear and very interesting.

And it's made me once again as his previous talks have done, it's made me rethink the way that I expect to see web applications be architected. And over the next couple of months I want to spend some time playing around with that idea and seeing if I can build an application that works in this way. So, that kind of lit a fire in my brain. So, I hope maybe some of the listeners would enjoy that, too.

**CHUCK:&nbsp;** Great. Well, if people want to follow up with you, find out what you're doing, what are the best places to do that, Tom?

**TOM:&nbsp;** Follow me on Twitter. I'm tomstuart on Twitter. That's the best thing to do. I have no other, there's no other way that you can see what I'm doing. I don't have a newsletter. I very rarely blog. But if you follow me on Twitter on the very unlikely occasion that I do a blog post or I'm speaking at a conference, I will tweet about it. So, that's pretty much the best thing to do.

**CHUCK:&nbsp;** Are you going to be at any conferences in the near future?

**TOM:&nbsp;** No. Last year I decided I was going to go cold turkey on conferences for a bit. And I'm still massively enjoying my cold turkey from conferences. I'm sure at some point in the next year I'm going to miss it so much that I'm going to get back into the conference circuit. But right now I'm enjoying being at home and just hanging out with people in London. So, if you want to see me, come to London and we'll go for a beer.

**CHUCK:&nbsp;** Alright. I'll see what I can do.

[Chuckles]

**CHUCK:&nbsp;** We'll go ahead and wrap this show up then. Thanks for coming, Tom.

**TOM:&nbsp;** Thanks for having me. It's been great.

**CHUCK:&nbsp;** Alright. We'll catch everyone next week.

**SAM:&nbsp;** Happy hacking.

**_[Bandwidth for this segment is provided by CacheFly, the world's fastest CDN. Deliver your content fast with CacheFly. Visit C-A-C-H-E-F-L-Y dot com to learn more.]_**

**_[Would you like to join a conversation with the Rogues and their guests? Want to support the show? We have a forum that allows you to join the conversation and support the show at the same time. You can sign up at RubyRogues.com/Parley.]_**
