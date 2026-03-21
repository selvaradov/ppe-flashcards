# PPE Anki flashcards
These are the flashcards I made while studying for Prelims and Finals PPE at Oxford.

I made all these flashcards manually, but with substantial LLM assistance, and I can't guarantee that
they're entirely error-free. If you spot any mistakes or unclarities, please let me know and I'll do my best 
to correct them. I describe the process I used to make these flashcards in more detail [below](#flashcard-making-pipeline).

For my notes and problem sheet solutions, see [PPE notes](https://github.com/selvaradov/ppe-notes).
For tutorial essays, see [my website](https://selvaradov.net/academic).

## Contents
### Prelims
Contains flashcards for each first-year module in PPE at Oxford which I learned for Prelims:
- Philosophy
  - Moral (just definitions)
  - General (personal identity and problem of evil)
  - Logic
- Politics
  - Theory (Mill's *On Liberty* only)
  - Practice (presidential, parliamentary, and semi-presidential systems; consensus and majoritarian systems; democracy and dictatorship; state formation & state strength; party systems; voter behaviour)
- Economics (fairly comprehensive across the board, includes some proofs etc.)
  - Micro
  - Macro
  - Probability & statistics

### Finals
Currently contains flashcards for:
- Economics
  - Core micro
  - Quantitative economics
  - Econometrics
  - Game theory
  - Micro analysis

Note that many of the decks contain cards with proofs or derivations for completeness;
you might want to filter these out before studying. I've used tags so it should be easy
to select specific weeks of content to learn. 

To be added:
- Philosophy
  - Ethics
  - Nicomachean Ethics
  - Logic

## Flashcard-making pipeline

Even if LLMs aren't allowed into the exams, that doesn't mean they can't make revising considerably
easier! Compared to when I was doing my Prelims revision, a lot of the process can now be automated,
especially for writing technical flashcards (where a large amount of time is spent on tedious
MathJax typesetting).

Here's the process I followed for each econ subject:
1. Download all past papers and examiners reports for previous years.
  - I should've done this with examiners reports too, but it didn't occur to me at the time.
2. Get Gemini to transcribe them all, along with all problem sheets.
3. Copy the transcriptions into Claude, along with the rubric / list of lecture topics for the course,
  and ask it to analyse what topics come up _in practice_, plus the ways in which they're usually tested.
  You could use a prompt like this:
  ```
  Can you go through these exam papers and help me get a better sense of what from the course to actually revise?
  e.g., for the week we do on repetition there's a lot about folk theorem proofs, but I'm not sure if this is actually necessary for the exams.
  I'd rather save the exam papers for later when I take them timed, so for now I only have psets to practise with but they're generally trickier than exams I think. 
  I was thinking that you could go through all the exam papers carefully and synthesise what the main types of questions are, then next I'll upload all my psets, and you can draw your conclusions.
  ```
4. Copy that summary into a new chat, then upload one week's slides and ask Claude to review the material
  and suggest what to cover within the flashcards. If relevant, get Gemini to transcribe handwritten
  notes from the lectures/tutorials, and add these too.
  - Usually I will draft my own rough list of desired flashcards first, because it seems like a good
    first step to just skim over the slides and remind myself of what was covered. Plus I don't want to be
    totally out of the loop of making my own revision flashcards.
  - Example prompt:
    ```
    Can you go through this set of slides and help me find the main important things to do flashcards on? Cross reference with the attached transcript analysing past exams. I think some important things to cover are the following, but I might've missed stuff:
    - ...
    Also attached are some notes I made to myself, trying to understand this all better (because the slides felt quite confusing).
    I will spend a while practising questions for this topic so it's not necessary or useful to memorise lots of derivations -- but probably what _is_ useful is some rough notes on general procedures, what to expect about the conclusions, the key equations to recall. 
    
    I found this topic tricky and will probably rely on mechanically following steps to the answer more than usual, vs deriving from first principles.

    Don't start making the flashcards yet, just suggest what they should be & sketch out the content in a pedagogically-informed way.
    ```

5. Review the proposed topics, use judgement to decide whether any need to be reframed / dropped / added in.
6. Move the chat into my "Economics flashcards" Project, where there are [further instructions](flashcard_instructions.md) for Claude about how to format the output, as well as [more high-level guidance](flashcard_principles.md) about my flashcard design principles.  
7. Go through each proposed card, copying it over to Anki and editing as I go. 
  - The most common change I need to make is splitting up a card containing several concepts into separate ones.
  - Sometimes I won't fully recall the intuition behind why a result is as it is; often I'll then try to properly
    understand it in the moment but not bother to add this into the flashcard, since it pays to be a bit of a
    ruthless prioritiser for what to actually memorise for exams vs know you understood once (for the satisfaction).

Ideally you'd just give everything (raw exam PDFs, examiners reports, slides, and exports of my handwritten lecture & tutorial notes) to Claude all in one go, but this really doesn't work with current context limits.

I was doing this in web chat, and possibly Opus 1M would handle it in Claude Code / via API, but that seemed like
more hassle to set up the pipeline for (and risk a fun-but-time-wasting distraction getting it to work).
