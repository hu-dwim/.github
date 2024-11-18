# dwim.hu

# What

The hu.dwim.* universe of Common Lisp projects was built when we decided to do some enterprise development in Common Lisp.

# Who

We are a small group of friends (3-5) from Hungary who used to work together as a team in various contexts for a couple of decades. Two of us were even shooting together in [QuakeWorld](https://quake.fandom.com/wiki/QuakeWorld), all the way back at the university.

Notably, prior to our Lisp gig we were part of the core team of Charles Simonyi's [IntentSoft](https://en.wikipedia.org/wiki/Intentional_Software) startup, working on an editor that edits structures (as opposed to a string of characters). Several years later [Levy](https://github.com/levy) wrote an interesting experiment in Common Lisp: [ProjecturEd](https://github.com/projectured/projectured/).

The core lispers, in alphabetical order:
- Tamás Borbély
- [Attila Lendvai](https://github.com/attila-lendvai/)
- [Levente Mészáros](https://github.com/levy)

# Why

After we left IntentSoft we were chopping wood at a random software shop. It was not satisfying intellectually, so we decided to try ourselves in the same enterprise bullshit, but using Common Lisp.

# When

Our Common Lisp endeavor lasted from around 2006, for about a decade. Since then everyone has moved on, and we are merely fighting off the bitrot -- with varying success.

# Status

None of us are working actively in Common Lisp anymore. Throughout those years we developed a few projects that helped us pay the bills, but sadly, there is much more potential lying wasted in the dwim.hu universe. All in all, we made about the same money as we would have as employees, but it was much more fun!

We loved darcs, but gave in eventually and converted the majority of our projects to git. Some projects that had non-trivial forks are yet to be converted to git (notably hu.dwim.perec, hu.dwim.rdbms, hu.dwim.web-server, hu.dwim.presentation).

# Where

The git repos are at https://github.com/hu-dwim/.

There's also http://dwim.hu/, still. It used to run an instance of [hu.dwim.home](https://github.com/hu-dwim/hu.dwim.home), which was kinda like an example project that demonstrated our codebase by documenting itself in the form of a webapp. It has succumbed to bitrot. Today dwim.hu is only serving the darcs repos, most of them already obsoleted by the git conversion.

The darcs repos are also mirrored at [hub.darcs.net](https://hub.darcs.net/hu.dwim).

# Notable projects, experiments, contributions

- hu.dwim.perec is an ORM that fully integrates with CLOS. You may read some blog posts from [David Lichteblau](https://lichteblau.blogspot.com/2009/08/cl-perec-blog-series-by-pinterface.html), and [pinterface](https://pinterface.livejournal.com/tag/cl-perec). It has a query engine that is a Lisp DSL with much more freedom than SQL, and yet it partially or fully compiles down to SQL queries, depending in how much magic you employ, and how much attention you pay for compilability. When compilation to SQL fails, then parts or all of the query is transparently executed in the lisp vm.
- hu.dwim.rdbms is an abstraction layer for various SQL databases. It also contains a lispy DSL for writing quasi-quoted SQL.
- Business Process Modelling: we used [hu.dwim.delico](https://github.com/hu-dwim/hu.dwim.delico) to [CPS transform](https://en.wikipedia.org/wiki/Continuation-passing_style) plain lisp code and [serialize](https://github.com/hu-dwim/hu.dwim.serializer) the continuation into the database whenever it wanted to wait for an event (e.g. display some UI to a user, sleep until some date, etc). When users logged in they had a list of TODO's that contained the serialized processes that were waiting for their feedback. When a process was continued, it typically displayed the GUI element for the user whose absence initially triggered its suspension. Processes could be written in plain Common Lisp code, with only a few additional primitives and constraints. All of this is going through database transactions.
- [hu.dwim.computed-class](https://github.com/hu-dwim/hu.dwim.computed-class) is a constraint based change propagation lib, fully integrated with CLOS.
- We were really battle-testing SBCL in our projects that were deployed for customers. This led to a lot of bug reports and reproducers, and sometimes even some patches from us. We channeled some of our (East-European) income into financing SBCL development. Threading and stability improved a lot while we were active. This is not to say that we were an important part of SBCL's development! All the credit belongs to its fine contributors and maintainers. But we did make *some* difference.
- We had major contributions to [Slime](https://github.com/slime/slime/), but we also had major clashes with the rather conservative maintainer at that time. Due to this some of our work is bitrotting away in [our fork](https://github.com/attila-lendvai-patches/slime).
- [hu.dwim.reiterate](https://github.com/hu-dwim/hu.dwim.reiterate) is a rewrite of [Iterate](https://gitlab.common-lisp.net/iterate/iterate), but done properly. Sadly, it's stuck at around 80%, and the Iterate compatibility layer is not done either. It could be a drop-in replacement for Iterate, but it's not.
- [hu.dwim.quasi-quote](https://github.com/hu-dwim/hu.dwim.quasi-quote) is a library to quasi-quote any structure. It's like the standard `` `(foo ,bar) `` list quasi-quotation syntax, but generalized to SQL, Strings, JavaScript, PDF, XML, CSS, etc. It is used in our web framework to inline HTML (XML) into lisp code. HTML emission is optimized at compile time into calls to `write-sequence` with literal vectors holding the merged constant parts.
- hu.dwim.presentation is a component based web ui, with transparent partial page refresh through AJAX requests. It was something back then.
- TODO to be continued
