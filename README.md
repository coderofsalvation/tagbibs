<!DOCTYPE html>
<html>
<head>
  
  <meta name="GENERATOR" content="github.com/mmarkdown/mmark Mmark Markdown Processor - mmark.miek.nl">
  <meta charset="utf-8">
</head>
<body>

<!-- for annotated version see: https://raw.githubusercontent.com/ietf-tools/rfcxml-templates-and-schemas/main/draft-rfcxml-general-template-annotated-00.xml -->

<h1 class="special" id="abstract">Abstract</h1>

<p>Tagbibs is a tiny paperfriendly tags, which expand into multiple BibTags <a href="https://en.wikipedia.org/wiki/BibTeX">BibTex</a>.
Using OCR, they&rsquo;re great for connecting scanned paper with online graphs.
The goal of this document is twofold:</p>

<ul>
<li>specify tagbibs: a terse tagdescription which expands into a reversed BibTag</li>
<li>specify tagbibs URI fragments: a way to hint browsers to jump to (bib)tagged content</li>
<li>specify bibrulers: dumb line-based separators for bibtags</li>
</ul>
<section data-matter="main">
<h1 id="what-are-tagbibs">What are tagbibs</h1>

<p><img src="postit.jpg" style="max-width:400px"/></p>

<p>tagbibs allow non-technical humans to write reversed BibTags in a short-form (on paper):</p>

<pre><code>Please get out the laundry 

@laundry@chores@todo
</code></pre>

<p>These tagbibs basically tag &lsquo;laundry&rsquo; by expanding into the following BibTags:</p>

<pre><code>Please get out the laundry 

@chores{laundry,
  
}
@todo{laundry,

}
</code></pre>

<blockquote>
<p>tagbibs are basically one step up from socialmedia hashtags, allowing mere mortals to tag things with pencil or keyboard.</p>
</blockquote>

<p>There&rsquo;s no precise predicates or properties, which allows citizen annotation (an essential precursor of RDF).</p>

<h1 id="what-are-bibrulers">What are bibrulers</h1>

<h1 id="what-are-tagbibs-fragments">What are tagbibs fragments</h1>

<p>`#@chores@todo</p>

<h1 id="contact">Contact</h1>

<ul>
<li>leonvankammen|gmail.com</li>
</ul>

<h1 id="iana-considerations">IANA Considerations</h1>

<p>This document has no IANA actions.</p>

<h1 id="acknowledgments">Acknowledgments</h1>

<p>TODO acknowledge.</p>
</section>

</body>
</html>

