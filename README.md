# lein-fore-prob

[![Build Status](https://travis-ci.org/bfontaine/lein-fore-prob.png?branch=master)](https://travis-ci.org/bfontaine/lein-fore-prob)

A leiningen plugin which given a problem from 4clojure will populate the
current project's tests with the problem's tests. This is based on
[`lein-foreclojure-plugin`][lfp] code updated for Leiningen 2.

[lfp]: https://github.com/broquaint/lein-foreclojure-plugin

The roadmap to 0.1.0 is:

* fix TODO/FIXME/XXXs
* write tests

A lot of breaking changes might happen before 0.1.0, so don’t rely on a
specific version until this one.

## Usage

Add the plugin in your `~/.lein/profiles`:

```clj
{:user {:plugins [ ; ... other plugins ...
                  [lein-fore-prob "0.0.4"]]}}
```

Create a project to store 4clojure problems:

```
lein new probs-from-4clj
cd probs-from-4clj
```

Then use the plugin:

```
lein fore-prob <problem id>
```

## What's added

Given a new project like this:

	.
    ├── ...
    ├── project.clj
    ├── src
    │   └── probs_from_4clj
    │       └── core.clj
    └── test
        └── probs_from_4clj
            └── core_test.clj

A stub function will be added to `src/probs_from_4clj/core.clj` e.g for
[problem 98][98] an `equivalence-classes-solution` function is defined. Then in
`test/probs_from_4clj/core_test.clj` the tests for that problem will be added
e.g. again for [problem 98][98] the test would be `can-equivalence-classes`. At
that point you can flesh out the function until the test passes then copy
it over to http://4clojure.org when you’re happy with it.

[98]: http://www.4clojure.com/problem/98 "98. Equivalence Classes"

## License

Copyright © 2014 Baptiste Fontaine

Original code:

Copyright © 2011 Dan Brook

Distributed under the Eclipse Public License, the same as Clojure.
