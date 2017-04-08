# inda-project-guidelines

Project guidelines for the INDA project, based on the great https://github.com/macaullyjames/inda-project-guidelines with permission from @macaullyjames with minor modifications.

## [Palinda instructions](https://www.kth.se/social/course/DD1349/subgroup/vt-2017-255/page/project-process-2/)

## [Add projects here](https://github.com/mictab/g5-projects)

# Table of Contents
1. [Picking a project](#picking-a-project)
2. [Choosing a stack](#choosing-a-stack)
3. [Github all the things!](#github-all-the-things)
4. [First steps](#first-steps)
5. [Development guidelines](#development-guidelines)
6. [Setup help](#setup-help)
7. [Licensing](#licensing)
8. [FAQ](#faq)

## Picking a project
Picking a project is really easy: Think of a project you'd like to do and pick it. Just keep in mind that
- You must work in pairs (preferrably within the same övning group).
- You must present a working demo at the final övning.
- You must use Git/Github to drive the development process (more on this further down).
- This is a programming project. You can't spend four weeks in a WYSIWYG editor making an elaborate PowerPoint.

That said, you can choose any language/framework you want, and target any hardware you want too. Want to make a simple Tower Defence style game for iOS? Great! Want to hook up a water gun to an Arduino, a camera and an object recognition library? Fantastic. Want to make yet another queue system for the labs? That's... actually, please don't do that. You get the point though. Bring out your inner Master Builder: everything is awesome.

## Choosing a stack
Now that you've picked what you'd like to work on, it's time to start thinking about how you're actually going to pull it off. Some facts that can help you make informed decisions:

- The course is worth 3.0 hp, which translates to about 80 hours of work in total. You work in pairs so you have a total of 160 hours to devote to the project. However...
- [The Mythical Man-Month](https://en.wikipedia.org/wiki/The_Mythical_Man-Month) is a thing.
- Have _either_ of you led a team before? Probably not.
- Have _both_ of you worked in the target environment before? Probably not.
- Have _both_ of you used Git/Github for collaboration? Probably not.

So basically you're about to undertake a project that might not be technically possible, in a stack that you're probably not familiar with, with someone you probably haven't worked with before and that may or may not be technically capable. Oh, and there's a hard deadline you need to hit if you want to pass the course. Let's be clear: **This is practically the definition of a bad project**, and you're fooling yourself if you think that 160 hours is a lot of time to work with. As such, your number one priority from the very beginning is **risk mitigation**. Remember, we just want you to present a working demo of _something_ resembling a project on demo day. Nobody has ever failed because they didn't make enough DLC to go with their game. You will fail, however, if your game is actually just a bunch of half-finished maps that you can't play because you ran out of time. Sure, Ubisoft might hire you, but you will not pass this course. The notion of "the smallest product you can produce and still get by" is called a [minimum viable product](https://en.wikipedia.org/wiki/Minimum_viable_product) (MVP) and is also a thing.

**The decisions you make before you start writing code will have much more impact on the project than the code you write.** Yes, it's entirely possible to use Java Swing for your game and write a simple physics engine from scratch, but will it help you build your MVP faster? Probably not. Spend a couple of hours researching viable options. If you're making a mobile app it might be better to use an HTML5-based solution such as [Cordova](https://cordova.apache.org) rather than the native stack. On the other hand, you're already familiar with Java so the opposite might be true if you're targetting Android specifically. Define the target platforms in terms of devices, OS, screen sizes etc. and make sure you can test on those platforms. Don't target "Android" if you've never worked with relative layouts before, instead let the target platform of your MVP be "Nexus 7 phones running Android Marshmallow" (if you have a Nexus 7 running Android Marshmallow, of course).

Get your development/testing environments of _both_ team members up and running as soon as possible. **Do not underestimate how much time this can take.** That library you want to use won't work in Ubuntu, the emulator you need won't render properly in Android Studio and the device you're testing on won't be recognised by the IDE. Seriously. Trust me. Don't believe the marketing on the framework's web page; download it, install it and make sure it works on both your machines. Do not invest in your chosen stack before you've done this.

## Github all the things!
In the good old days of INDA you'd have to write a formal project specification document at the start of the project and hand in a report at the end of the project. Not anymore! All you have to do is use Github like it's supposed to be used. Really, that's all we ask.

You should interpret this to mean that all project-related communication between you and your partner should be done in the issue tracker. Yes, I mean _all_ communication (with the possible exception of things like "When should we meet tommorow?"). **Every decision you make in the project should be brought up, discussed, and resolved in the issue tracker.** Your assistant should be able to ask "Why is there only one level in this game?" and you should be able to point them to the issue where you discussed why having one only level was the right thing to do.

Have an idea for a cool feature? Open an issue and label it as an `enhancement`. Found a bug that needs addressing? Open a `bug` issue. Having all communication done on the issue tracker not only makes it easier for outsiders to assess the state of the project, it also makes it easier for them to _participate_ in the project. Which is kind of what Open Source is all about. Now, you might be thinking "But who else would care about my first-year project?". Well, **you** care about it, and it's in **your** best interest to make it as accessible as possible. For starters, your assistant is much more likely to weigh in if they can participate in a discussion on the issue tracker rather than you sending them a zip file with the note "HELP!!1! doesnt compile :(". The same goes with your classmates. Not to mention how much easier it will be when you have testers; not only will they be able to report bugs directly in the bug tracker, they'll be able to see what others have reported (avoids duplicates) and even help each other resolving any setup problems. Basically, if you want help then you should make giving help as easy as possible. Again, it's kind of what Open Source is all about. If nothing else it's just common courtesy.

## First steps
OK, so you've chosen a project and stack and everything seems to be working as expected. If you haven't done so yet, create a repo for your project. I **strongly** recommend using `github.com` instead of `gits` because this is a really nice opportunity to fill out your CV (also you get free access to CI servers etc.), but the choice is yours. Remember to add your partner as a collaborator either way.

**Now, the very first thing you should do is to spec out your MVP.** Open an issue and discuss what it should contain. Upload pretty pictures depicting how it will look (you can upload images in the comments). Don't get carried away here: Every time you feel like you should add something, ask "will we still pass if we don't do this?" and if the answer is "yes" then leave it out. These ideas are worth keeping for later on, of course, and you should open a seperate issue for each of them for further discussion.

By the end of this discussion you should have a very concrete idea of what your MVP will look like. Now you need to figure out how to build it. This is hard. **Don't try and make an elaborate plan** at the beginning of the project describing how you'll spend each of your 160 hours; [it won't work](http://www.infoq.com/resource/articles/scaling-software-agility/en/resources/ch02.pdf). The best you can do is to continuously improve your project in small iterations. Again, the issue tracker is important here; if you've just finished implementing a feature you're probably the most knowledgable about what needs to be done next. It's tempting just to leave your partner out of the loop and avoid all the overhead of communication in the name of Getting Stuff Done. Don't do this. It's _very_ easy to get left behind in small projects like this and you'll quickly end up with a useless partner.

**When you're done implementing a feature, open an issue decribing what you think needs to be done next.** It's important knowledge for everyone involved in the project and makes it a lot easier for your partner to take over where you left off. Even if you plan to do the work yourself, it gives your partner the chance to chip in with ideas. If you feel like this is a waste of time, like all you're doing is opening issues, then try making the issues a bit larger in scope.

With that said, all that's left to do now is open a few issues describing your first steps towards the MVP **and get the assistants approval** 🤓

## Development guidelines
When you're writing code on your own you can pretty much do whatever you like. Bad commit? Eh, `git push -f`. In a rush? You know what you've changed, `lolololol` is a perfectly adequate commit message. Nobody knows and nobody cares.

This kind of anarchy doesn't scale well to teams with more than one member though. You'll be much more productive if you lay down some ground rules based around *respect* and *trust*, like _"Let's make sure we peer review each other's code before pushing to_ `master`_"_ or _"Let's stick to Google's coding conventions so our programming style is consistent"_. You should write these rules down, preferably in a file called CONTRIBUTING.md in the repo.

It's up to you and your team how comprehensive these guidelines are. For example, the CoffeeScript development [guidelines](https://github.com/jashkenas/coffeescript/blob/master/CONTRIBUTING.md) are a four point list. The Auctionet dev team have an entire [handbook](https://github.com/barsoom/devbook) detailing everything from [deploying without downtime](https://github.com/barsoom/devbook/tree/master/deploy_without_downtime) to [how many pizzas to order for a meetup](https://github.com/barsoom/devbook/blob/ddc8c44c045d4c150435b8333b8a213a446e0402/arranging_a_meetup/README.md#order).
For small projects it's enough to make clear:

- How should I contribute code? Send a PR or push to a branch? Do I base off of `master` or some other branch? Should I rebase or merge?
- Is there a style guide I should follow? (No is an OK answer!)

## Setup help
As you probably know by now, having access to a piece of code and being able to build/test/run that code are two different things. You want to make it as simple as possible to get a working dev environment up and running which means clear, unambiguous documentation:

- What OS are you running on? Not just _"Windows/Mac/Linux"_ but an actual description of what I should download, like _"Fedora 23 x64"_.
- What packages/programs are needed? Again, don't say _"Python"_, say _"the_ `dnf` _package_ `python 2.7.10-8.fc23`_"_.
- What libraries do you use? How do I install them? Again, version numbers are important. If at all possible, use a package manager for this (`npm`, `pip`, `CocoaPods` etc.) and store the config files in the repo.
- Finally, how can I build/test/run your code? If you use Eclipse, commit the project files to the repo. If you've written a Bash script, commit that. If you normally just `javac` your way to glory, state that explicitly too.

If possible you should run through your instructions on a clean machine to make sure you haven't missed anything. This doesn't just make life easier for outside contributors, it makes life easier for you too! If you can't reproduce your dev environment, what will you do if your laptop catches fire and/or you spill coffee on it and/or it gets stolen? I'll tell you what: Spend a week crying at the keyboard trying to figure out why Java says `Error: Could not find or load main class Main`. Not fun 🙈

Apart from good documentation, there's a couple of general tips to keep in mind when developing that can save you a lot of headaches later on:

- Simple is good: Do you _really_ have to run a hardened Gentoo installation with a manually patched compiler? Could you not just use Ubuntu 16.04 and `apt-get` a few packages?
- Stick to the language's development conventions. For example, use `npm` instead of Bash scripts if you're writing server-side JavaScript. You're much more likely to find help online if you follow the beaten path.

## Licensing
_Disclaimer: I am not a lawyer_

**Pretty much any original creative work you author is automatically protected under copyright law.** By default, this means that you have exclusive rights to the use and distribution of the work; you get to decide who uses your work, how they use it and their means of obtaining it. **No-one can use your work unless you explicitly allow them too.** It's illegal.

Your source code is an original creative work and as such is protected under copyright law. **Hosting it on GitHub does not change this**, in the same way that posting an article on a blog does not grant readers the permission to re-post the article as their own. This means that **you need to explicitly grant others the rights to use and distribute your code** if you want it to be used in other projects (which you do). **You need a software license**.

Of course, you could write your own software license, but licensing is hard and I'm guessing that you're not a lawyer either. Instead you should choose one of the industry standard licenses such as the MIT, Apache or GPL licenses, depending on how you want your code to be used. If you don't know which license to pick, [choosealicense.com](http://choosealicense.com) is a good place to start. Jeff Atwood's article [Pick a License, Any License](http://blog.codinghorror.com/pick-a-license-any-license/) over on the Coding Horror blog is a good read if you're still not sure.

In summary: It's illegal for others to use your code without a license. Pick a license. Github makes this easy for you upon creating of a repository.

## FAQ

- Do we need to get a project approval from you? 

Yes, this is because I need to determine if the project is extensive enough for the course. When opening the PR to https://github.com/mictab/g5-projects, please state what the project is about. I’ll then approve the PR and merge it when I’m satisfied that the project is enough work for this course.

- Will the school provide us with software I need for the project if it costs?

Probably not. Most stuff should be free to use though.

- Can I work with someone outside of group 5?

Yes *but* please try to find someone in your own group first. Otherwise everything just becomes logistically harder. Please see section “Team” here https://www.kth.se/social/course/DD1349/subgroup/vt-2016-projinda16-2/page/project-process/. You will need the approval of both me and the other student's assistant and then you'll be assigned either one of the palinda groups.

- Will you help us with our project?

Most likely, no. Maybe with some basic guidance and links, sure. I’ll try to if I can but I suspect you’ll all do very different things which I don’t know about.

- What programming languages can I use?

Any language that’s sane (no Brainfuck, LOLCODE etc.)

- When will I know if I passed the course? 

At the last exercise session. Not before that.

- Can I extend something I’ve already built?

If you clearly mark out a new component you wish to develop and integrate into the existing codebase, and if I deem it extensive enough, then yes.

- If I want to build an iOS or Android application, will KTH provide me with a phone for the dev process?

Not likely. Not likely at all.
