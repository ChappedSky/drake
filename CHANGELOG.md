## 0.1.0

 * Initial release!

## 0.1.1

 * Drake now works with [Drip](https://github.com/Factual/drake/wiki/Faster-startup:-Drake-with-Drip) which allows to bring down startup time essentially to zero in most cases.
 * Added support for R ("R" protocol). See [resources/regtest/regtest_interpreters.d](https://github.com/Factual/drake/blob/develop/resources/regtest/regtest_interpreters.d) for usage example.
 * Added ```--preview``` command-line option, which prints the same report of targets predicted to be built, but immediately exits afterwards instead of asking for user confirmation.
 * You can now [use Drake from Clojure REPL](https://github.com/Factual/drake/wiki/Drake-on-the-REPL) by calling ```run-workflow``` function.

## 0.1.2

 * ```=``` are now allowed in filenames
 * ```:``` are now allowed in filenames (Drake will default to local file system instead of issuing "invalid filesystem" error, i.e. ```bad:name``` -> ```file:bad:name```)
 * CLI changes:
  * CLI is now getopt-compliant (i.e. one could do ```drake -aw my-workflow.d```)
  * -d doesn't work any more for debugging info: only --debug (-d reserved for future use)
  * --debug prints much less info now, --trace added for more verbose output
  * Added checking for conflicting options (i.e. --preview vs --print).
  * Help is now printed nicely
 * Added --step-delay to specify the amount of time, in milliseconds, to wait after each step. Should help with [desynchronized filesystems](https://github.com/Factual/drake/issues/15).
 * bugfixes: [34](https://github.com/Factual/drake/issues/34)
