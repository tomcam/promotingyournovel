# Promoting Your Novel: How to Get Started

You've written your novel. 
You're going to self-publish ([why self-publish?](faq#why-self-publish)),
probably using [Kindle Direct Publishing](https://kdp.amazon.com), [CreateSpace](https://www.createspace.com), or [SmashWords](https://www.smashwords.com).

Now what? This site's purpose is to help make your book famous, spending as little time and money as possible. The order you do some things is important, so remember to visit the [Timeline](./timeline.md).


This is a guide to promoting your novel online with the least expenditure of time, money, and trouble. 
It's an opinionated guide, meaning it makes a lot of decisions for you. I assume you'd rather be
writing than reinventing the wheel by revisiting whether SmashWords is better than Kobo or whatever.


## Broken things

### /checklist directory is broken, but the /check directory works fine???

### /checklist directory fails:

Unable to nest URLs in /checklist. **Look at browser status line for each one**. Examples:

* [Create a twitter account](/checklist/create-twitter-account) Markup is `[Create a twitter account](/checklist/create-twitter-account)` **Best but still fails**
* [Create a twitter account](/checklist/create-twitter-account.md) Markup is `[Create a twitter account](/checklist/create-twitter-account.md)`
* [Create a twitter account](#/checklist/create-twitter-account.md) Markup is `[Create a twitter account](#/checklist/create-twitter-account.md)`
* **Yet this nested-er one works!** * [Create a twitter account copied to deeper directory](/checklist/checklist/create-twitter-account) Markup is `[Create a twitter account](/checklist/checklist/create-twitter-account)`
* [Why topic 1](/why/why1) What happens here?

### /check directory works!

* [Create a twitter account](/check/create-twitter-account) Markup is `[Create a twitter account](/check/create-twitter-account)` **Works like a charm**
* [Create a twitter account](/check/create-twitter-account.md) Markup is `[Create a twitter account](/check/create-twitter-account.md)`
* Bonus: Linking to just the [check](/check) directory properly lands on /check/index.md Markup is `[check](/check/)`


{% comment %} 

These fail because of relative directories
* [Create a twitter account](checklist/create-twitter-account) Markup is `[Create a twitter account](checklist/create-twitter-account)`
* [Create a twitter account](checklist/create-twitter-account.html) Markup is `[Create a twitter account](checklist/create-twitter-account.html)`
* [Create a twitter account](#/checklist/create-twitter-account.html) Markup is `[Create a twitter account](#checklist/create-twitter-account.html)`

{% endcomment %}

## Created using

* [PureCSS](http://purecss.io), [source](https://cdnjs.cloudflare.com/ajax/libs/pure/0.6.1/pure.css)
* Timeline: [vis.js](http://visjs.org/docs/timeline/)
* Pingdom [Website speed test](https://tools.pingdom.com/)

### Kramdown
* [Quick Reference](https://kramdown.gettalong.org/quickref.html)
* [Syntax](https://kramdown.gettalong.org/syntax.html)

### GitHub pages
* [Basics](https://help.github.com/categories/github-pages-basics/)
* [Pages](https://jekyllrb.com/docs/pages/) 
* [Templates](https://jekyllrb.com/docs/templates/) 
* [Variables](https://jekyllrb.com/docs/variables/)
* [Customizing GitHub Pages](https://help.github.com/categories/customizing-github-pages/)
* [Jekyll Pages](https://jekyllrb.com/docs/pages/) describes clean URL requirements
* [Minimal configuration](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) 
* [How I'm Using Jekyll in 2016](https://mademistakes.com/articles/using-jekyll-2016/)
