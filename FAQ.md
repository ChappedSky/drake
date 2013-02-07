# FAQ

**Q:** How is Drake different than my favorite tool, X?
**A:** We may not know X, but if you're using it we bet it's a great tool! What we
can share with you is that we put a lot of thought and work into building
features in Drake that are specialized for today's modern data workflow
processing problems. In our experience these features are generally hard
to achieve, or downright lacking, in many popular tools:

* multiple outputs
* no-input and no-output steps
* HDFS support
* forced execution of any subbranch, up or down the tree or any individual targets (crucial for debugging and development)
* target exclusions
* protocol abstraction - e.g., inline Python, R, Ruby, Clojure
* tags
* branching
* methods

Please see [the full Drake specification](https://docs.google.com/document/d/1bF-OKNLIG10v_lMes_m4yyaJtAaJKtdK0Jizvi_MNsg/edit) for a better understanding of the
feature's we've chosen to focus on.

All that said, if you've found a tool that is more ideal for your purposes,
far be it from us to try to make you use Drake. Keep on rockin'!

**Q:** How is Drake different than Make?
**A:** Drake has some basic similarities to Make, since Drake's design was largely
inspired by Make's basic approach to dependency resolution. However,
Drake is targeted squarely at the domain of data workflow management,
as opposed to software project build management. Drake has specific features
related to today's data processing challenges that you won't find in Make:

* HDFS support
* Easy handling of multiple outputs from a single step
* Mulitple language support inline, e.g. Ruby, Python, Clojure
* Integration with common data analysis tools, e.g. R

Of course, if you find Make to be the best solution for your problem, that's
great! As always, YMMV.

**Q:** Doesn't the slow JVM startup time drive Drake users crazy?
**A:** It did, before we [learned to use Drip](https://github.com/Factual/drake/wiki/Faster-startup:-Drake-with-Drip)!

**Q:** Is there a way to pass parameters to a Drake workflow?
**A:** Yes, Drake lets you define workflow variables which can be used just about
anywhere in your workflow, e.g. to dynamically define target names, etc.

Default values can be dfined in your workflow, and you can override them on the
command line when you call Drake. See TODO for more details.

**Q:** How can I use Drake as a library, or from my Clojure REPL?
**A:** Check out the [Drake on the REPL wiki page](https://github.com/Factual/drake/wiki/Drake-on-the-REPL),
and have fun in Clojure-land!

**Q:** Why do I get an `ERROR java.io.IOException` when I try using Drake with HDFS?
**A:** It could be that your build of Drake is not using a Hadoop client library that
is compatible with your cluster. Please see [the wiki entry on HDFS compatibility](https://github.com/Factual/drake/wiki/HDFS-Compatibility).

**Q:** Why doesn't Drake recognize I have up-to-date targets in HDFS?
**A:** Drake looks for Hadoop configuration in `/etc/hadoop/conf/core-site.xml`. It
may be that in your environment, you keep your Hadoop configuration elsewhere.
Try copying or symlinking your Hadoop configuration to `/etc/hadoop/conf/core-site.xml`.

**Q:** Why is Drake written in Clojure?
**A:** We love Clojure at Factual. Lisp is an extremely powerful language, and
Clojure brings all this to the practical JVM world. And Lisp is quite good
in operating on lists and graphs, which is a big part of Drake.

Clojure has a very good syntax for Java interop, so all Java libraries are
available to us. But, of course, Clojure community also spits out libraries
like crazy, for example, take a look at [fnparse](https://github.com/joshua-choi/fnparse),
which we use in Drake for parsing.

Of course, we don't expect **you** to love Clojure, or Lisp, or want to
work in it. Drake will happily support any language you can dream of, as long
your scripts can be called via the shell. And Drake includes inline support
for a variety of languages besides Clojure, including Ruby and Python.

**Q:**  How can I contribute to the Drake project?
**A:** Thanks for asking! We are actively interested in accepting code submissions, but reports, and
any kind of help whatsoever. Please feel free to send us pull requests or file
a ticket through the main github repo.
