# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

<!-- 2-3 lines. Who is talking when you comment on an issue: your
experience level stated plainly, what you are doing in this repo, what
readers can expect from you. This is the register your rules protect. -->

I am currently a beginner when it comes to contributing to open source and coding projects, but I have a strong CS theory education and business anlaysis background. So readers can expect that I am able to articulate my thought process and understanding of the high level problem. Furthermore, I'm currently focused on improving my technical fluency, so I would want them to expect accurate terminology and specific examples, files, etc. to ensure that my technical understanding is tractable.

## Rules I write by

<!-- 3-5 rules, drafted from the lecture's slide-12 moment. Each rule
needs a wrong/right pair from your own hand: one line you might
actually have written that breaks the rule, and the line you would
post instead. The pair is what makes a rule executable; a rule without
one is a wish.

Format each rule like this:

### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->

### Rule: No promised timelines

- Wrong: "By tomorrow..."
- Right: "Repro report on the way"

### Rule: Name the version and the behavior

- Wrong: "This bug"
- Right: "v1.20.0 ignores --style"

### Rule: Say it like you would out loud

- Wrong: "Amazing project!"
- Right: "Hi! I'd like to take on this issue."

## Things I never post

<!-- A short list. Promises you cannot keep, tones you refuse,
shortcuts you know you reach for when tired. The skill quotes this
list back at you when a draft crosses it. -->

- Promises I cannot keep
- Desperate sounding and over people pleasing tone.
- Reproducible steps that don't logically track like things that may be implied or underspecified.
- Overly long prose that contains redundant content or information that can be explained better and more concise

## Upstream: how I talk to maintainers

### Claims I post

<!-- 1-2 rules. What your claim promises and how it sounds: intent,
a concrete first step, a realistic timeframe, in your register. Think
about what you refuse to do too: claiming over a stranger, squatting
silently, promising dates you cannot keep.

#### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->

#### Rule: Realistic timelines with a specific deliverable

Wrong: I’ll take this and should have a fix up in a day
or two.
Right: I’d like to take this. First step: reproducing on
macOS against main; I’ll report what I find by Thursday.

### Questions I ask

<!-- 1-2 rules. What a question of yours must carry before it goes
up: answerable from the maintainer's chair, what you already tried,
one question rather than five. -->

#### Rule: Specific questions addressing what you've already tried

- Wrong: "It doesn’t work on my machine, can you help? Also how do the tests run, and is this the right file?"
- Right: "Following CONTRIBUTING.md I ran make, then go test ./...; the suite fails in pkg/cmdutil before my change (output below). Is a failing trunk expected right now, or is my setup wrong?"

### Pings I send

<!-- 1 rule is enough. When you nudge and how it sounds: measured
against the repo's own reply rhythm, never your clock, and never
pressure dressed as politeness. -->

#### Rule: Specific questions addressing what you've already tried

- Wrong: "Hi, you haven't followed up at all. Can you please just provide an update?"
- Right: "Hi, just following up to see if there's any feedback with the plan I proposed."

<!--
NO UNIT 2 GUIDE? The frame carries you. Write ALL the sections fresh
in your canonical guide, today: first the three unit 2 sections
listed below, then the Upstream section above. Write every rule as
plain text, outside these comment blocks. It is more writing, and it is
entirely doable; ask a TF if you want a second pair of eyes on your
first rules.

The unit-2 frame, so you do not need the old materials open:

  ## Who I am in threads
    2-3 lines. Who is talking when you comment: your experience level
    stated plainly, what you are doing in this repo, what readers can
    expect from you.

  ## Rules I write by
    3-5 rules, wrong/right pair each, same format as above.

  ## Things I never post
    A short list. Promises you cannot keep, tones you refuse,
    shortcuts you know you reach for when tired.
-->
