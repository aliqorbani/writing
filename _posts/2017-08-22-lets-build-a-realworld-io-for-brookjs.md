---
ID: 5348
post_title: 'Let&#8217;s build a realworld.io for brookjs!'
author: James DiGioia
post_excerpt: ""
layout: post
permalink: >
  https://jamesdigioia.com/lets-build-a-realworld-io-for-brookjs/
published: true
post_date: 2017-08-22 09:53:40
---
I've been working on [`brookjs`][brookjs] for the better part of a year, and it's maturing into a solid framework. In order to help make `brookjs` real for people, I started building a [realworld.io][rw.io] app with it. The intention is to make this a testbed for `brookjs`, hammering on all the features and hitting as many weird corner cases as possible. [WP-Gistpen][wpgp] has been doing that for me up to this point; implementing a syntax highlighting text editor on top of `brookjs` has been an interesting challenge, one still pretty fraught with problems, but it's allowed me to abuse every layer of the stack, sussing out bugs and designing patterns.

In order for the framework to really progress, it has to be stable, and there are areas of it that aren't tested enough to really be considered production-ready. [brookjs-realworld.io][bjs-rw.io] can test some of those areas--specifically, animations and the rendering cycle API--and bring them the "real world" (cwidt?) implementations they need to iron out their warts. I also need to see what the development experience looks like to those outside the bubble.

To assist with that, I've also started a [cli for brookjs][brookjs-cli], which can also be informed by [realworld.io][bjs-rw.io] development. `beaver` will be able to scaffold new reducers/deltas/etc., manage and run the build and test scripts, and provide a opinionated means of building `brookjs` applications. I'm basically stealing the best ideas from [create-react-app][cra] and [ember-cli](https://ember-cli.com/) and implementing them for `brookjs`.

Even if we're stable now, we've got a number of improvements we can make to `brookjs`, the first of which is precompiling the Handlebars templates to vdom-returning functions, rather than parsing the string output of a Handlebars function. We currently recommend using `handlebars-loader`, but if the cli manages the build process, when the time is right, we can swap `handlebars-loader` for a `brookjs-loader` (or similar) without breaking anyone's app (🙏).

Anyone can contribute to the [realworld.io app][bjs-rw.io], and I'm working on a Vagrant setup so we can provide the entire environment without needing to install anything on your development machine (besides Vagrant and Virtualbox). It doesn't do anything yet but provide scaffolding for the front-end and back-end bootstrapping.

If you're interested in getting to know [`brookjs`][brookjs] and seeing how it works in a real app, or want to help define best practices for `brookjs` applications, check out the [realworld.io app on GitHub][bjs-rw.io]. This is a great opportunity to find something you're interested in learning (API, caching, offline apps, cli apps, observables...) and work on it collaboratively with other people. If you want something to work on, [comment in or open an issue on GitHub][issues].

Looking forward to working with you!

  [brookjs]: https://valtech-nyc.github.io/brookjs/
  [rw.io]: https://github.com/gothinkster/realworld
  [wpgp]: https://github.com/mAAdhaTTah/wp-gistpen/
  [bjs-rw.io]: https://github.com/valtech-nyc/brookjs-realworld.io
  [brookjs-cli]: https://github.com/valtech-nyc/brookjs-cli
  [cra]: https://github.com/facebookincubator/create-react-app
  [issues]: https://github.com/valtech-nyc/brookjs-realworld.io/issues