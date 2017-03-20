# Using Scrivener with MultiMarkdown (MMD) files

This is a pretty specialized article for people who wrote, or plan to write, their novel using 
[Scrivener](https://www.literatureandlatte.com/scrivener.php) and MultiMarkdown files (which end in `.mmd`). 
What follows is a tiny, inadequate overview of how MultiMarkdown works and why you might wish to use it. If you already know why you're here, feel free to skip ahead to [Scrivener's workflow is different with MultiMarkdown][ScrivenerMMDWorkflow].

MultiMarkdown files are nothing but plain, slightly ugly-looking text files that look something like this:

```
# Chapter 1

She was not where she expected to be. That much was clear.

```

When "compiled" (which is the way Scrivener converts your files to ebook form) the `#` character
on its own line, followed by a space, followed by text, gets converted to an HTML `<h1>` header tag,
two `##` characters using the same convention get converted to an HTML `<h2>` header tag, and so on.

## Why use MultiMarkdown?

If you've ever had the problem of pasting from your email program into your word processing document (or vice versa) and seeing how the formatting got screwed up, you've seen why a simple formatting style like MultiMarkdown helps with big projects. 

MultiMarkdown is a plain text format. It uses simple formatting rules that are easy to view when typing in any text editor. It is stored in standard text files, which makes it easy for other programs to translate. This makes MultiMarkdown ideal for larger projects, say, more than 10 pages.

Large projects usually require a firm grip on formatting that's consistent, predictable, and easy to change in bulk. MultiMarkdown was built for that purpose.

[ScrivenerMMDWorkflow]:

## Scrivener's Compile workflow is different with MultiMarkdown

When you create an eBook using Scrivener, you're probably used to steps that look like this:

* From the `File` menu, choose `Compile`.
* From the `Format as` dropdown, choose `E-book`.
* From the `Compile for` dropdown, choose `Kindle eBook (.mobi)`

Click the `Compile` button, and a few moments later you have a single eBook file ready to submit to Amazon (in this example).

### Scrivener can't compile eBooks from MultiMarkdown so there are extra requirements

Scrivener doesn't yet create eBooks from MultiMarkdown files. You have to compile to an intermediate format such as HTML, RTF, or the OpenOffice/LibreOffice word processor file format, which is .ODT. Then you need a third-party converter such as [pandoc](http://pandoc.org) to translate from the intermediate format to an eBook format such as .mobi or ePub. The workflow then becomes something like this:

* Install [Fletcher Penny's MultiMarkdown](http://fletcherpenney.net/multimarkdown/) (details follow)
* Install [pandoc](http://pandoc.org/installing.html) (details follow)
* From the `File` menu, choose `Compile`.
* From the `Format as` dropdown, choose `Custom`.
* From the `Compile for` dropdown, choose `MultiMarkdown -> Web Page (.html)` -- you won't see this unless you've already installed MultiMarkdown
* Run the resultant HTML file through pandoc to create the actual ebook--a .mobi or ePub file
* You can see how it will look when published using the [Kindle Previewer](https://kdp.amazon.com/help?topicId=A3IWA2TQYMZ5J6#kindlepreviewer)


## Extra requirements for MultiMarkdown

## Further reading

Here are some of the sources I used to write this section:

[Jeremy Lee James: Scrivener - How To Compile With Style](http://jeremyleejames.com/scrivener-how-to-compile-with-style-tutorial/)




