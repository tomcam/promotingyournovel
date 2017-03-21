# Using Scrivener with MultiMarkdown (MMD) files

This is a pretty specialized article for people who wrote, or plan to write, their novel using 
[Scrivener](https://www.literatureandlatte.com/scrivener.php) and MultiMarkdown files (which end in `.mmd`) and who want to export them to .mobi format for Kindle. Expect this to get technical, right down to running programs from your computer's command line. If this all sounds like gobbledegook, now's a good time to read another section.

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

Scrivener doesn't yet create eBooks from MultiMarkdown files. You have to export to MultiMarkdown format. Then you need a third-party converter from the command line such as [pandoc](http://pandoc.org) to translate from the MultiMarkdown files to ePub format, which is used by most eBook publishers other than Amazon. Finally, you use Amazon's Kindlegen to convert from ePub format to .mobi, which is the finished version used by Amazon's Kindle readers. The workflow then becomes something like this:

* Install [Fletcher Penny's MultiMarkdown](http://fletcherpenney.net/multimarkdown/) (details follow)
* Install [pandoc](http://pandoc.org/installing.html) (details follow)
* From the `File` menu, choose `Compile`
* From the `Format as` dropdown, choose `Custom`
* From the `Compile for` dropdown, choose `MultiMarkdown`. This option only exists if you've already installed MultiMarkdown. You may wish to give it a name ending with with .mmd, such as `mynovel.mmd`
* Run the resultant MMD file through pandoc to create the the ePub file
* Run the ePub file through KindleGen to convert from the ePub format to .mobi, which is what Kindle readers use.
* You can see how it will look when published using the [Kindle Previewer](https://kdp.amazon.com/help?topicId=A3IWA2TQYMZ5J6#kindlepreviewer)


## Extra requirements for MultiMarkdown

## Further reading

Here are some of the sources I used to write this section:

[Jeremy Lee James: Scrivener - How To Compile With Style](http://jeremyleejames.com/scrivener-how-to-compile-with-style-tutorial/) By far the most useful, complete, and technically oriented blog post on this subject. This page does complements but does not replace it. However, it only goes so far as conversion to HTML. Jeremy James does not address conversion of the HTML output to an eBook format.

[Coverting a book to MultiMarkdown](http://support.fletcherpenney.net/discussions/problems/690-how-can-i-convert-my-book-to-multimarkdown-mmd) has a bit of useful information on exporting to MultiMarkdown.

[Kindle Previewer at Kindle Tools and Resources](https://kdp.amazon.com/help?topicId=A3IWA2TQYMZ5J6#kindlepreviewer) Download Kindle Previewer and find all of Amazon's apps used to create eBooks on this page. There's some pretty amazing stuff here and it's all free.


