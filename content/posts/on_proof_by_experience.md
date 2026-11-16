+++
title = 'On proof by experience'
date = 2026-11-12T09:25:01+08:00
draft = false
+++

I am a terrible reader. I have so many books, and then due to my ADHD, I read one, for some time, then another, and another.

The negative in this is that I may have been reading a lot of books but a tiny percentage of each. But the positive is that now my knowledge is wide-scoped, and I know a lot about all the things I don't yet know.

There's also a practical reason. Some books are so deep that once I am stuck in a deep point, I don't progress unless I let my subconscious figure it out. One such is Mawlawi's Mathnavi (Ask your AI about it for more; Gemini says: "25,000 rhyming couplets across six books, it is widely regarded as one of the greatest works of mystical poetry and Islamic literature.").


I am still stuck in the first 20%th percent of book I. Specifically, there was a couplet that I'd been thinking about for years. It goes like this:

> آفتاب آمد دلیل آفتاب،
> گر دلیلت باید از وی رو متاب

AI translates this purely literally: “The sun itself is the proof of the sun. If you want proof, don’t turn your face away from it.” Claude and Gemini also both added certain extra's, such as the sun being a double-meaning on Shams (which means the sun in Arabic; Shams was a mysterious mystic who had visited Mawlawi).

But these are false. I had thought the same for years, before AI slapshed itself into the world, yet I would also feel a certain unease that my understanding was incomplete.

This couplet was in the back of my head for a long time, and I'd given it to my subconscious as a 'zadacha', Russian term for a task to be finished. I like the Russian word because it means so much more than just a mere task. (Задача comes from задать (за- + дать, “to give/set”), so something set before you, and interestingly this 'something' is at once all of the three: a problem, an objective, and also an assignment. It carries both solvability and obligation [hence you'd be obligated to solve it]).

And several years after I set this zadacha for myself, it occurred to me when I was writing an [answer](https://qr.ae/pF328g) on Logo programming, on my Quora page. Just as I finished writing the code to generate a sun.

For the benefit of readers not familiar with programming, I'll briefly give the steps so that they too experience how my interpretation dawned on me only after I wrote the code for a Logo sun.

It is elementary to realize that we can draw a circle if we move by, say, one pixel, then turn right (or left) one degree, then again move one pixel, then turn right, and onward like this 360 times. We write this as:

```prolog
to circle
  repeat 360 [forward 1 right 1]
end
```
(Feel free to run these in the online Logo interpretor on my Logo [tutorial site](https://jansavagelogo.surge.sh/).)

Where the `to...end` block is called a procedure (or a function) and `repeat` loops over n times (here 360 times) over a list `[ ]` which contains the `forward 1 right 1` code block.

Now we want to be able to create a circle of any size. So we need a function that takes an input (an argument, in the jargon) that stands for an arbitrary size. Arguments in Logo are written with a colon:

```prolog
:arg
```

Consequently, our second function becomes:

```prolog
to circle :size
  repeat 360 [fd :size rt 1]
end
```

Logo has shortcuts so you can guess what fd and rt stand for. This is ok, but we could also use a radius formula, instead:

```prolog
to circle :radius
  repeat 360 [fd (:radius * 0.01745) rt 1]
end
```

By the same formula, we can also draw a part of a circle, that is, an arc. Since arcs can turn right or left, we can name them so:

```prolog
to arcR :degrees :radius
  repeat :degrees [fd (:radius * 0.01745) rt 1]
end
```

Let's also make one for the left:

```prolog
to arcL :degrees :radius
  repeat :degrees [fd (:radius * 0.01745) lt 1]
end
```


It's essentially the same as our procedure for circles. Now, the fun part. We will need to be creating rays, like so:

```prolog
to ray :size
  arcR 90 :size
  arcL 90 :size
  arcR 90 :size
  arcL 90 :size
end
```

And ray 50 would give us:

<img src="/essays/images/ray50.png" alt="Ray 50"
     style="display: block; margin: 0 auto; width: 50%; min-width: 150px; max-width: 100%; height: auto;">

Two more steps. One to see what would repeating the rays would look like. Let's repeat them 4 times (while the ray size is now 25), and on each time, the turtle/robot turns right 90 degrees:

<img src="/essays/images/ray25.png" alt="Ray 25"
     style="display: block; margin: 0 auto; width: 50%; min-width: 150px; max-width: 100%; height: auto;">

The angle being 90, it's so inside and outside. But the outside is what counts here, since the turtle makes the turn on the outside. Now let's draw a sun. For this, the angle should be 160, and let's specify about 9 rays:

```prolog
to sun :size
    repeat 9 [
        ray :size
        rt 160
    ]
end
```
Now we draw a sun of size 45:

<img src="/essays/images/sun45.png" alt="Sun 45"
     style="display: block; margin: 0 auto; width: 50%; min-width: 150px; max-width: 100%; height: auto;">

Now, as soon as I wrote this, an idea descended unto my mind: the "it" in Mawlawi's couplet does not refer to the sun, though it has been translated so. In the Dari Persian, the pronoun is /wai/ which could also refer to all entities, regardless of their gender or lack thereof.

The first part of course is similar what Descartes had said with his cogito (I think therefore I am); So it appears that Mawlawi is saying: "if you want proof that the sun exists, just look at the sun, that is proof enough for you."

But this was too simplistic for the kind of poetry Mawlawi writes. There had to be a deeper meaning. The key point is in the phrase: "don't turn away from /wai/" if you want proof."

This second proof (that you want) is not about the existence of the sun! The first sentence already dealt with the sun: "the sun came as proof of the sun". Here, too, there are several layers of meaning. One could be Shams, his spiritual guide. Because all our light comes from the sun, thus light is what enables us to see. So, Shams arrived to let Mawlawi truly see.

But the second part is more important: it refers to the philosophasters looking for proofs for the existence of God Almighty (SWA). Mawlawi seems to be saying: if you want real proof that your Creator (ج) exists, don't turn away from Him (/wai).

This is repeated elsewhere in Mathnavi, as well. The key idea in these repeats is that the only sure way to know that you're on the right path, is through experience. If you don't turn away from your Creator and clear your chest of all rust and dirt (sin, and evil thoughts), it becomes a mirror that can reflect the light of Allah (SWA). So, if you want to know for sure, the only way is through experience.

This accords well with Mawlawi's disdain for philosophers (esp the ones trying to prove (or disprove) God Almighty's existence through theorems and mere speech).

Hence, matters exist in our world for which no proof is enough or even suitable. Just imagine your own self: can you explain the feeling of motherhood or fatherhood to someone who hasn't experienced it--in words? Sure, you can try but the words are never the same as the experience itself. The proof for how it feels being a parent is achieved only through experience.

Hence, some evidences are empirical-only. Only when you experience them, do you get to realize their reality. Descartes also meant this in _cogito, ergo sum_ but from the other direction. He was trying to say he could prove an empirical-only truth by the fact that we all know it is empirical: that we exist, is empirically given.

Mawlawi's couplet is the other way round: some truths are empirical-only, and no amount of proof is adequate or correct unless you experience it.