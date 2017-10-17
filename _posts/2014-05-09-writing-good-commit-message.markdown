---
layout: post
categories: [tech]
title: Writing good commit message
---

The purpose of a commit message should be to explain to another developer (it can be
the future myself) what this particular modification is about.
I'm always surprised by how much succinct are commit messages.

With some well-known exception like the Linux kernel, most open-source project doesn't
specify what they want to see in their commit message. I think, it's a bummer because it's
a very useful source of information.

Here's the format we use in my team:
```
One-line description of your change (fewer than 72 characters)

Problem
Explain here the context, and why you're making that change.
What is the problem you're trying to solve.

Solution
Describe the modifications you've done.

Result
After your change, what will change.
Explain how the modifications you just described will solve
the initial problem.
```

This creates a very readable `git log`, and a `git blame` on any line of code will
immediately explain the context (maybe things have changed since) and how this particular
line fits into the solution described in the commit. I let you see by yourself on
[the Github page for finagle](https://github.com/twitter/finagle/commits/master "the Github page for finagle"){:target="_blank"}

### Motivation of this process

When creating a review, you should do everything in your power to ease the work of the
reviewer. In order to review your change, readers will have to gain context on the
motivations behind it. As the author of the change, you have the opportunity to lessen
this burden by clearly describing the relevant history and key implementation details
of your code. Summarizing the review entails explaining why and how you made the change.

Likewise, reviewers should try to catch any possible bugs or design flaws in the code.
If a bug is found after the change is merged, then the reviewers are almost as responsible
as the author.

### Exceptions

Obviously for very very simple change, like typo fixing, you don't need to follow this
convention. Use your common sense to know when you have to use this process.
