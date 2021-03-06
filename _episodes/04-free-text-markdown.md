---
title: "Free text formats"
teaching: 25
exercises: 30
questions:
- "Key question"
objectives:
- "First objective."
keypoints:
- "First key point."
---

## Plain Text Formats

### Why
* **Plain text is always compatible**
    * Every OS has a text editor
* Easy to maintain
    * Since plain text, you can view in diff. interfaces (cmd line)
    * Easier to version since the plain text is not binary
* Easy to break apart and reuse
    * If the markup or structure visible and not nested, can programmatically process
    * CSV - every programming language has CSV library
    * Simplicity is your friend when you want to automate stuff, opacity not
* Lightweight
    *  Word file can be heavy or dense compared to txt
    *  Xls file can be compressed or dense compared to csv
* Always forward compatible - Doesn't matter what changes occur in IT
    * Think about the number of word processor you have used? name them? are they compatible now? Would you know how to use?
* Easier to process with computers

---

## Markdown

### What is Markdown?

- `Markdown` is a particular type of markup language. Markup languages are designed to produce documents from plain text.
- You may be familiar with `LaTeX`, another (though less human friendly) text markup language.
- Tools render markdown to different formats (for example, HTML/pdf/Word).
  - The main tool for rendering Markdown is [pandoc](http://pandoc.org/).

Adapted from [Carson Sievert's markdown slides](http://cpsievert.github.io/slides/markdown/#/1)


### Markdown enables fast publication to the web

- **Markdown** Easy to write and read in an editor.
- **HTML** Easy to publish and read on web.

### Markdown versus HTML code

<div class="row">

<div class="col-md-6">

<pre>
This is a Markdown document.

## Medium header <!-- header 2, actually -->

It's easy to do *italics* or __make things bold__.

> All models are wrong, but some are useful. An approximate answer to the right problem is worth a good deal more than an exact answer to an approximate problem.

Code block below. Just affects formatting here.

```
x <- 3 * 4
```

I can haz equations. Inline equations, such as the average is computed as $\frac{1}{n} \sum_{i=1}^{n} x_{i}$. Or display equations like this:


$$
\begin{equation*}
|x|=
\begin{cases} x & \text{if $x\ge 0$,} \\\\
-x &\text{if $x\lt 0$.}
\end{cases}
\end{equation*}
$$
</pre>

<img src="../media/smiley-face-clipart.png"/>

</div> <!-- end column left -->


<div class="col-md-6">

<pre>

&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;head&gt;
&lt;meta http-equiv="Content-Type" content="text/html; charset=utf-8"/&gt;
&lt;title&gt;Title&lt;/title&gt;
&lt;!-- MathJax scripts --&gt;
&lt;script type="text/javascript" src="..."&gt;&lt;/script&gt;
&lt;style type="text/css"&gt;
body {
   font-family: Helvetica, arial, sans-serif;
   font-size: 14px;
...
&lt;/style&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;p&gt;This is a Markdown document.&lt;/p&gt;

&lt;h2&gt;Medium header&lt;/h2&gt;

&lt;p&gt;It's easy to do &lt;em&gt;italics&lt;/em&gt; or &lt;strong&gt;make things bold&lt;/strong&gt;.&lt;/p&gt;

&lt;blockquote&gt;&lt;p&gt;All models are wrong, but some are...&lt;/p&gt;&lt;/blockquote&gt;

&lt;p&gt;Code block below. Just affects formatting here.&lt;/p&gt;

&lt;pre&gt;&lt;code&gt;x &lt;- 3 * 4&lt;/code&gt;&lt;/pre&gt;

</pre>
 <img src="../media/frowny-face-clipart.png"/>
</div> <!-- end column right -->
</div> <!-- end 2-column row -->

### Markdown versus rendered HTML

<div class="row">
<div class="col-md-6">
<pre>

This is a Markdown document.

## Medium header <!-- header 2, actually -->

It's easy to do *italics* or __make things bold__.

> All models are wrong, but some are useful. An approximate answer to the right problem is worth a good deal more than an exact answer to an approximate problem.

Code block below. Just affects formatting here.


```r
x <- 3 * 4
```

I can haz equations. Inline equations, such as the average is computed as $\frac{1}{n} \sum_{i=1}^{n} x_{i}$. Or display equations like this:

$$
\begin{equation*}
|x|=
\begin{cases} x & \text{if $x\ge 0$,} \\
-x &\text{if $x\lt 0$.}
\end{cases}
\end{equation*}
$$

</pre>

<img src="../media/smiley-face-clipart.png"/>

</div>

<div class="col-md-6">

<p>This is a Markdown document.</p>

<h2>Medium header</h2>

<p>It&#39;s easy to do <em>italics</em> or <strong>make things bold</strong>.</p>

<blockquote>
<p>All models are wrong, but some are useful. An approximate answer to the right problem is worth a good deal more than an exact answer to an approximate problem.</p>
</blockquote>

<p>Code block below. Just affects formatting here.</p>

<p><code>x &lt;- 3 * 4</code></p>

<p>I can haz equations. Inline equations, such as the average is computed as \(\frac{1}{n} \sum_{i=1}^{n} x_{i}\).</p>

<p>Or display equations like this:</p>

<p>\[
  \begin{equation*}
    |x|=
         \begin{cases}
      x & \text{if $x\ge 0$,} \
      -x & \text{if $x\lt 0$.}
        \end{cases}
   \end{equation*}
   \]</p>
<img src="../media/smiley-face-clipart.png"/>
</div>
</div>


## Markdown can be rendered to multiple formats

- `pandoc` is a Swiss-army knife tool for conversion`

![](http://www.datacarpentry.org/rr-literate-programming/media/pandoc-diagram.jpg)

### Demo

![](https://i.redd.it/wy2fj69in3oz.jpg)

> ## Your Info in Markdown
>
>1. Go to <https://hackmd.io> and create a guest note (This is an online markdown editin service)
>2. Make a top header (H1) using markdown with your name
>3. On the next line, make a bullet point and add your email as a link
>4. Add another bullet point and rovide a link to your workplace
>5. Create a H3 titled `My Favorite Things`
>6. Add a numbered list of your favorite things
{: .challenge}

---
This should look something like:
# Tim Dennis
* <tdennis@library.ucla.edu>
* <https://www.library.ucla.edu/>
## My favorite things:
1. Audiobooks
2. Hiking
3. Data

---

## YAML Headers

Markdown supports metadata elements that can be added at the top of the document separated by `---` before and after the YAML. They are put on single lines and expressed as `key: values` with a colon separating the key from the value. Supported YAML metadata in hackmd.io are: `title`, `description` and `tags`. These are often reused in the rendering as the `title` tag in HTML or a subsitution variables in Jekyll.

> ## Use YAML headers
>
> YAML headers are set at the top of
> 1. Go back to your document above
> 2. Add a `title`, `description` and `description` YAML metadata (it should look like the below, but wiht your data)
{: .challenge}

~~~
title: Tim's Information
description:  A short document containg some of Tim's info.
tags: bio, url, email
~~~
{: .source}

> ## Download your document in different formats
> 1. Publish your document by pressing the `Publish` link on top right
> 2. Go back to the edit view and export as:
>    * Markdown
>    * ODF (will open in word)
> 3. What do you notice?
{: .challenge}

> ## Copy your markdown text into a class document
> 1. Go to <hackmd.io>
> 2. Copy and paste your file after your name
> 3. We'll reuse this tomorrow
{: .discussion}

## Markdown is used in many contexts.

* All the lessons in Software, Data and Library Carpentry are written in markdown.
* GitHub uses markdown for issues, renders markdown documents to HTML by default
* Tools like Jupyter and RMarkdown Notebooks let you interleave markdown and Python and R code
* Most of these use Pandoc to convert markdown to other formats.

Show how to set up blog in github

> ## Get a GitHub Account
> 1. Regeister for a GitHub Account
> 2. Go to <https://github.com/join>
{: .challenge}

> ## Getting a markdown blog in GitHub
> 1. After you have logged into GitHub with your account above, navigate to <https://github.com/barryclark/jekyll-now>
> 2. Click `Fork` on top right and select your repository
> 3. Reame the repository to `yourgithubusername.gith.io`
>    ![](https://github.com/barryclark/jekyll-now/raw/master/images/step1.gif)
> 4. Your blog will be available at <https://yourgithubusername.github.io/>
> 4. To customize your blog edit `_config.yml` (yes that's YAML) - replace `Barry Clark` with your name, add a description, etc.
> 5. Publish your first blog post by edition `/_posts/2014-3-3-Hello-World.md` to publish your first blog post.
> 1. Go back to <https://yourgithubusername.github.io/> and marvel at your work.
> 1. Review <https://github.com/barryclark/jekyll-now> for more that you can do with the blog.
