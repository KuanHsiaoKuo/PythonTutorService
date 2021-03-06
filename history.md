# Project history

<!--ts-->
* [Project history](#project-history)
   * [start](#start)
   * [v1: interactive online programming tutorials](#v1-interactive-online-programming-tutorials)
   * [v2: the use of pointers](#v2-the-use-of-pointers)
      * [advance](#advance)
   * [v3/](#v3)
      * [The biggest advance of v3 over v2](#the-biggest-advance-of-v3-over-v2)
   * [v4-cokapi: support multiple languages](#v4-cokapi-support-multiple-languages)
      * [v4 was purely a backend advancement;](#v4-was-purely-a-backend-advancement)
   * [v5-unity/](#v5-unity)

<!-- Created by https://github.com/ekalinin/github-markdown-toc -->
<!-- Added by: kuanhsiaokuo, at: Thu Jun 30 16:24:15 CST 2022 -->

<!--te-->
> See [here](http://pgbovine.net/python-tutor-history.htm) for an early history of the first three years:

## start

> Project created in December 2009; I first wanted to make a JavaScript run-time visualizer for education since it could all be in-browser, but then realized that I couldn't easily hook into the JS debugger in the browser to do single-stepping without making the user install plug-ins; then I switched to a server-side solution and **picked Python as the target language**.

> That turned out to be a wise choice in hindsight since Python was poised to really take off as a CS1 language in both traditional courses and MOOCs, starting around 2011.

## v1: interactive online programming tutorials

> Online Python Tutor version 1 - released on January 19, 2010
"Release" email to 15 friends:

> Subject: version 0.0000001alpha of my online Python tutor Body:

  ```text
  hi python fans (and non-fans) ...

  this is what i've been hacking on for the past few days instead of
  doing my research ;)  i'm planning to use it as a platform for
  creating interactive online programming tutorials as part of a
  volunteer project ...

  http://python.pgrind.com/

  it'd be great to get your feedback on what i have so far.  i'd love
  to hear suggestions or complaints.  thanks in advance!

  please don't share this link yet, mostly because my app is still
  buggy and insecure (i definitely don't want random peoples from the
  internet trying to hack it right now!)

  pg
  ```

## v2: the use of pointers

> From Jan 2010 until Aug 2011, v1 was deployed online on my personal and MIT servers, and it barely had any users. From a technical standpoint, it rendered all data structures as HTML tables and had no pointers, so aliased data were duplicated. It was a proof-of-concept side project that I had fun hacking on and showing off to people.

> In Sep-Oct 2011, I majorly brushed up OPT into v2 since a few power users started using it more seriously and making feature requests
(e.g., Brad Miller, Suzanne Rivoire, Peter Wentworth), and Python-based MOOCs were also just starting to take off ...

- Online Python Tutor version 2 - released on October 4, 2011
  "Release" email to 13 friends:

> Subject: Re: version 0.0000001alpha of my online Python tutor Body:

  ```text
  Dear subset of people who cared about my prior email from almost 2
  years ago ...

  I've recently kicked it up a notch with a "2.0" version and am about
  to do a public release soon.  I'd really appreciate any feedback,
  criticism, and especially bug reports on Internet Explorer ;)

  http://people.csail.mit.edu/pgbovine/opt-prerelease/

  Please don't share the link yet since it will be dead soon when I
  move this app to its permanent home.  I just want to get some early
  feedback to eliminate the obviously embarrassing bugs before launch.

  THANKS!

  pg
  ```

> From Oct 2011 until Sep 2012, v2 was deployed online and launched as
www.onlinepythontutor.com.

### advance

The biggest technical advance over v1 was the use of pointers (rather than duplicating objects with identical object
IDs) to better visualize aliasing. However, pointers could point only from names to objects (i.e., from within a frame
to the heap); heap-to-heap pointers weren't implemented yet. During this time period, MOOCs started taking off, and the
usage of Python Tutor grew organically.

## v3/

> In July-Sep 2012, I made a giant push to release v3, working closely with John DeNero and others at Google and beyond ... awesome times!

- Online Python Tutor version 3 - Released on September 18, 2012 to 153,000+ people who followed the official
  Research@Google Google+ account: https://plus.google.com/+ResearchatGoogle/posts/cseo9qi7LWq

> "Release" announcement from the Research @ Google G+ account:

```text
  Online Python Tutor: Web-Based Program Visualization for CS Education

  As part of his CS education work at Google, +Philip Guo has been
  developing an open-source educational tool called Online Python Tutor
  (http://www.pythontutor.com). This tool enables teachers and students
  to write Python programs directly in the web browser and then
  single-step forwards and backwards to visualize what the computer is
  doing as it executes those programs.

  Program visualization for CS education is nothing new -- researchers
  have been developing these sorts of tools for decades. However, most
  of these tools never reach far beyond the confines of the researchers'
  home universities due to the difficulty of installing and configuring
  the visualization software. What makes Online Python Tutor unique and
  effective is that it's the first known tool to adapt time-tested ideas
  from the research literature (e.g., rendering of box-and-pointer
  diagrams) for a web-based environment. Now anyone with a modern
  browser can create, explore, and share their program visualizations by
  simply visiting a web URL.

  This ease of access has been a major contributor to adoption: So far,
  over 100,000 people have used Online Python Tutor to understand and
  debug their programs, often as a supplement to learning from
  textbooks, lecture notes, and online programming tutorials. In
  addition, instructors in over a dozen universities such as MIT, UC
  Berkeley, and the University of Washington have used it for teaching
  introductory computer science courses.

  But this is just the beginning. Philip and his colleagues are now
  building an online authoring environment so that, within the next few
  months, teachers and students will be able to save their code snippets
  and add annotations, discussion threads, lessons, and interactive
  exercises on top of the associated visualizations.

  They are also actively seeking partnerships with educators at all
  grade levels to deploy and improve Online Python Tutor. Please contact
  Philip directly or re-share this post with educators who might be
  interested in working with this tool in any capacity.

  Visit www.pythontutor.com to learn more and to start visualizing your
  Python programs now!
  ```

> This official publicity provided a big initial PUSH that spurred worldwide usage of the tool, and it kept growing organically from there thanks to momentum and also MOOCs and other online learning resources quickly rising in popularity around 2012-2013.

### The biggest advance of v3 over v2

- The biggest advance of v3 over v2 was more sophisticated pointer visualizations and layout, including heap-to-heap
  pointers.
- Another major advance is that each visualizer instance is now encapsulated into a self-contained JavaScript object;
  thus, multiple visualizers can now be embedded within a single web page.
- in v1 and v2, only a single visualizer could be displayed on a given page, since there was no encapsulation; all state
  was global, eek!
- Also, all state is encapsulated in a simple URL, so that it's easily sharable or iframe-embeddable, which is very
  useful!
- v3 also marked the launch of the crisper pythontutor.com domain rather than the older and more
  clunky www.onlinepythontutor.com domain used for v2.
- In mid-2014, the "shared sessions" feature (a.k.a. Codechella) was launched onto the site, which enables multiple
  users to simultaneously join a shared session.
- During the period of v3, this tool experienced a significant growth in user numbers to well beyond 1 million users and
  10 million visualized pieces of code!

> 2014-06-16 - launched the shared sessions feature on Python Tutor:
http://pgbovine.net/python-tutor-live.htm

## v4-cokapi: support multiple languages

> 2015-01-24 - started a new version (based on v3 code base) to expand Online Python Tutor to support multiple languages such as JavaScript and Java. Note that this contains only backend code, so we still rely on v3/ for the frontend (and the original Python backend)

### v4 was purely a backend advancement;

The v3 code is still used for the frontend. By the end of 2015, six new languages had been added:

- Java (from David Pritchard's backend)
- JavaScript
- TypeScript
- Ruby
- C
- C++.

> In short, 2015 was the year of adding new languages to expand this tool's scope beyond just Python and hopefully making it into a more generally-useful tool in the coming years.

- Jan 2010 - launched Python 2 for OPT v1
- Oct 2011 - launched Python 2 for OPT v2
- Sep 2012 - launched Python 2 and 3 for OPT v3 on new pythontutor.com domain
- Jan 2015 - launched Java and JavaScript backends
- March 2015 - launched TypeScript backend
- July 2015 - launched Ruby backend
- May 2016 - launched C/C++ backends


- June 2016 - launched a live programming mode for Python/JavaScript at:
  http://pythontutor.com/live.html

## v5-unity/

- 2016-07-27 - deployed v5-unity/ onto pythontutor.com to replace v3/, which was deployed in September 2012.

> From now on, active development will take place in v5-unity/ and *not* v3/.

- 2017-10-20 - launched "Get live help!" feature on Python Tutor, where anyone on the site can volunteer to help others
  who are requesting help on the site.

> This is a natural extension of Codechella. See here for details: http://pgbovine.net/PG-Vlog-74-python-tutor-live-help.htm

- 2017-12-06 - (finally!) set Python 3 as the default in visualize.html and live.html since most courses have been
  taught in Python 3 for years, yet Python 2 has been the default due to inertia.

> Note that for a few years, preferences have already been "sticky", which means that when a user chooses, say, Python 3, then the next time they revisit the site, it will stay on Python 3. But now Python 3 is the default, which should eliminate a bunch of confusion for first-time users expecting Python 3 but actually getting Python 2 and seeing mysterious errors.

- 2018-03-17 - lots of minor unglamorous 'elbow grease' tweaks to get the tool more usable in general:

1. greatly simplified the home page of http://pythontutor.com/ to focus solely on visualization and live help features.
   lots of other minor UI clean-ups throughout the app as well.
2. added a second backup execution server for non-Python languages to vastly improve reliability for those languages,
   since they're now getting popular and my sole server wasn't faring so well under load
3. did lots of behind-the-scenes sysadmin/DevOps stuff to monitor errors, produce better and more consistent error
   messages, and improve reliability; this sort of stuff will become more important as traffic grows
4. started keeping a list of unsupported features and linking to it when the user encounters errors, so they will know
   its limitations:
   https://github.com/pgbovine/OnlinePythonTutor/blob/master/unsupported-features.md

- 2018-08 - added some more backup servers to try to improve responsiveness for non-Python language execution

- 2019-04 (around this time) - Put up more warnings throughout the site that there won't be technical support or major
  new features coming, since I don't have time to maintain its code or server load as well anymore. Disabled "Get live
  help!" from live.html experimental live programming mode due to too much load on server.

- 2019-10 - simplified the UI by removing excess text and also removed the inline Eureka survey (v5-unity/js/surveys.ts)
  , nudged people to read this doc more by adding a link to more error/warning messages:
  https://github.com/pgbovine/OnlinePythonTutor/blob/master/unsupported-features.md
