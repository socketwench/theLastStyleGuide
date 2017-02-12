# Tools and style

Now that we have the basics out of the way, we need to think about larger issues. Where will we store our documentation? How should we write it?

## Avoid single-file formats

Single file formats like PDFs and word processing files are often where documentation goes to die. They are easily distributed, but that's also their biggest problem. Once out in the world, these files are static and unchanging. Users that went to great efforts to find them, will cling to them even as the information within the file decays. Depending on you project and your company's culture, you may face significant push-back in delivering documentation any other way.

## Prefer living documentation

Your documentation should be a living thing. It should grow and change with your project as it grows and changes. The key is to create a single point of publication where you have control. That way, it is up to you when and how old documentation is retired and removed, and how updates are brought to the foreground. Today, this typically means a website of some sort.

## Avoid content management systems

Given the above point, you'd assume that reaching for a dynamic, content management system (CMS) is the way to go. There are many systems like this available, most in the form of a wiki. While these systems are easy to stand up and lower the barrier to entry for your team, they should not be your first choice for the following reasons:

* CMSes create an additional, parallel workflow to the project's software development workflow.
* Revision, reversion, and review of CMS hosted docs has historically been lacking.
* CMSes a difficult for non-developers to run on their personal systems, making it difficult to troubleshoot problems.

## Prefer revision control

At it's core, documentation is just a bunch of text with the occasional image to help things along. This is not unlike software code, where revision control systems (RCS) have been used for decades. RCSes like git can manage text files, images, versioning, co-current edits, and more with widely available tutorials. Ideally, your documentation should share the same git repository as your project's source code. Whenever the software is updated, so is the documentation.

## Prefer static site generators

Since documentation tends to be divided across multiple sections and pages, it's best for technical writers to _not_ write raw HTML. Instead, you should rely on an intermediate format such as [ASCIIdoc](http://asciidoc.org/) or [Markdown](https://guides.github.com/features/mastering-markdown/). Then, this documentation source code can be processed by a static site generator such as [Gitbook](https://www.gitbook.com), [Jekyll](https://jekyllrb.com), [Sculpin](https://sculpin.io/), or any number of options.

These static site generators apply branding, navigation, and visual styles in a consistent and unified fashion. You should never run the generator yourself, but instead rely on the software's build system to run and deploy the results to staging and production web servers on commit.
