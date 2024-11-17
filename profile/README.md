# dwim.hu

# What

The hu.dwim universe of Common Lisp projects was built when we decided to do some enterprise development in Common Lisp.

# Who

We are a small group of friends (3-5) who used to work together as a team in various contexts for a couple of decades.

Two of us were even shooting together in [QuakeWorld](https://quake.fandom.com/wiki/QuakeWorld), all the way back at the university.

Notably, prior to our Lisp gig we were part of the core team of Charles Simonyi's [IntentSoft](https://en.wikipedia.org/wiki/Intentional_Software) startup, working on an editor that edits structures (as opposed to a string of characters). Several years later [Levy](https://github.com/levy) wrote an interesting experiment in Common Lisp: [ProjecturEd](https://github.com/projectured/projectured/).

# Why

After we left IntentSoft we were chopping wood at a random software shop. It was not satisfying intellectually, so we decided to try ourselves in the same enterprise bullshit, but using Common Lisp.

# When

Our Common Lisp endeavor lasted from around 2006, for about a decade. Since then everyone has moved on, and we are merely fighting off the bitrot -- with varying success.

# Status

None of us are working actively in Common Lisp anymore. Throughout those years we developed a few projects that helped pay the bills, but there was/is much more potential lying wasted in the dwim.hu universe.

# Notable projects and experiments

- hu.dwim.perec is an ORM that fully integrates with CLOS. You may read some blog posts from [David Lichteblau](https://lichteblau.blogspot.com/2009/08/cl-perec-blog-series-by-pinterface.html), and [pinterface](https://pinterface.livejournal.com/tag/cl-perec). It has a query engine that is a Lisp DSL with much more freedom than SQL, and it partially or fully compiles down to SQL queries, depending in how much magic you employ, and how much attention you pay for compilability. When compilation to SQL fails, then parts or all of the query is transparently executed in the lisp vm.
- Business Process Modelling: we used [hu.dwim.delico](https://github.com/hu-dwim/hu.dwim.delico) to [CPS transform](https://en.wikipedia.org/wiki/Continuation-passing_style) lisp code and serialize the continuation into the database whenever user interaction was needed. Logged in users had a list of TODO's that contained the serialized processes that were waiting for their feedback. When a process was continued, it typically displayed the GUI element for the user that initially triggered its suspension. Processes could be written in 100% Common Lisp code, with a few special primitives.
- TODO to be continued
