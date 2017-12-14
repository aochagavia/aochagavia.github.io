+++
title = "Singularity AI"
draft = false
date = "2017-11-02T15:14:51+01:00"

+++

Sometimes you read comments on the internet about how computers are going to
take over the world when [Artificial General Intelligence][agi] becomes a thing.
While I am convinced a real AGI will never happen, it inspired me to start a
new project: [Singularity AI][s-ai]. The title sounds like a startup name,
but it is basically a tool to prank people by making them think I programmed
an AGI.

### The idea

Singularity AI consists of a single-page website where you can ask questions
and get answers from the computer. The website itself pretends to be an AGI,
as you can deduce from the first question of the FAQ:

> What are you?
>
> I am a General Artificial Intelligence, that is, a computer program that can think and feel just as you do.

*Note that this is technically an incorrect definition of AGI, but... who cares?*

### Designing a fake AGI

Singularity AI is meant to be used by two people. One of them knows that everything is fake
and secretly types the answers to every question. The other one, the subject of the prank,
suggests new questions and looks astonished at the screen after receiving the right answers
to each question. Sounds great, right?

A big question remains, though. How can we type the answers without anyone noticing?
Fortunately, we are talking about an AGI here. That is, a computer that is indistinguishable
from a human being. It happens that this computer is very proud and won't answer to any
question, unless asked in the right way. Therefore, each time after you type a question,
you also need to type a petition in the following form:

> Oh Singularity, please answer my humble question

This may seem silly, but it is the key to entering answers in a subtle way. Since the
petition text is always the same, you could modify the text input to show the same
sentence regardless of what you type. In other words, you can write the answer and have
the website display the sentence: *Oh Singularity, please answer my humble question*.

By the way, I didn't bother to get the website working on mobile, since you always
get typing suggestions from your keyboard and it is much easier to commit mistakes.
This makes it almost impossible to type the answers without being noticed.

One last detail is that, sometimes, the person being pranked wants to type the question
themselves. After all, it seems so extraordinary that they feel the need to do it,
to ensure it is no prank. Fortunately, in this case they will get a generic answer about the computer
being upset with them because they doubt the website is real.

### How to use

If you go to the [website][s-ai] right now, you will notice that the text input for
the petition behaves like a normal text input. That is, it shows the letters you type,
whatever they are, instead of showing the "*Oh Singularity...*" sentence.

In order to start entering the answer, you need to get into *answering mode*. You can
do this by pressing `;` on the petition text input. From that point on, you can type any
gibberish you want and will see how the "*Oh Singularity...*" sentence starts appearing
on the screen. When you are finished writing the answer, you can type `;` again to exit
*answering mode* and finish writing the petition sentence.

After writing the question and the petition, you can click on the *Ask* button to reveal
the answer.

### The implementation

Since I don't want to pay for publishing such a ridiculous website, I decided to
implement it in HTML and Javascript. That way, I could host it at [neocities][neocities]
for free. I programmed it in vanilla Javascript, as anything beyond that would have been
overkill (besides, I really didn't want to setup a "modern Javascript toolchain" with Webpack
and all the bells and whistles.)

It took me about an hour to build a basic prototype. I tested it on some friends and was
satisfied with the results, so I went ahead, grabbed a bootstrap template and published
the resulting [website][s-ai]. While I don't like adding a bunch of unnecessary CSS and
Javascript, the time savings of not having to come up with my own design are certainly
worth it.

The Javascript code spans about 80 lines. I am not particularly proud of the style,
since I almost didn't touch it after I got it working. I am usually much pickier about
the quality of the code I publish, but on the other hand, this project is more
about the website and less about the code. You are welcome to look at it, but
it is really nothing special and probably a unreadable.

### User testing

The real fun begins at this point, when the website is published and ready to
be shown to a couple of friends. Some of them were very skeptical and refused
to believe this was a real AGI, so from the beginning they were trying to find
out how I typed the answers. Some of them, however, were more willing to believe,
leading to interesting stories like the one below.

> Me: ever heard of an Artificial General Intelligence? Look, I programmed one. It
> can answer any question you have. It makes use of all the sensors on the computer,
> but can also query information from the internet.
>
> Friend: that can't be true. Ask it this: how cold is my beer?
>
> (He probably thought this would be a good question, since I cannot think of a sensible way my
> computer could know the temperature of his beer)
>
> Computer: 12 degrees.
>
> Friend (stands up and starts walking around the room): WHAT!? WHAT!?
>
> (He kept asking questions, usually easy to answer, each time reacting in the same way.
> He also tried typing the questions himself, which of course resulted in snarky
> pre-programmed answers. Finally, he came up with a truly difficult
> question...)
>
> Friend (with a confident smile): ask it how much I weigh.
>
> (At this point, I considered whether I would get away with a generic answer.
> On the other hand, I felt tempted to take the gamble and come up with an
> estimation... It would be truly amazing if I managed to get the right answer...)
>
> Computer: 62 kilograms.
>
> (At this point my friend finally came to the conclusion that everything was fake,
> quite late in the game... I lost the gamble)

### Conclusion

As you can see, you can have quite a bit of fun with this. Feel free to share your
experience. You can find my email by cloning this blog's repository and using `git log`.
Maybe we can even create a hall of fame with the best stories.

[agi]: https://en.wikipedia.org/wiki/Artificial_general_intelligence
[s-ai]: https://singularity-ai.neocities.org/
[neocities]: https://neocities.org
