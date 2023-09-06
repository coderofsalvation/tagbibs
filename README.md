<!DOCTYPE html>
<html>
<head>
  
  <meta name="GENERATOR" content="github.com/mmarkdown/mmark Mmark Markdown Processor - mmark.miek.nl">
  <meta charset="utf-8">
</head>
<body>

<!-- for annotated version see: https://raw.githubusercontent.com/ietf-tools/rfcxml-templates-and-schemas/main/draft-rfcxml-general-template-annotated-00.xml -->

<h1 class="special" id="abstract">Abstract</h1>

<p>Tagbibs are tiny paperfriendly tags, which expand into multiple <a href="https://en.wikipedia.org/wiki/BibTeX">BibTags</a>.<br>
Using OCR, they&rsquo;re great for connecting scanned paper with online graphs.<br>
The goal of this spec is three-fold:</p>

<ul>
<li>specify tagbibs: a terse tagdescription which expands into a reversed BibTag</li>
<li>specify tagbibs URI fragments: a way to hint browsers to jump to (bib)tagged content</li>
<li>specify bibrulers: dumb line-based separators for bibtags</li>
</ul>
<section data-matter="main">
<h1 id="definitions">Definitions</h1>

<table>
<thead>
<tr>
<th>term</th>
<th>explanation</th>
</tr>
</thead>

<tbody>
<tr>
<td>linear LUT</td>
<td>array lookup table</td>
</tr>
</tbody>
</table>

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

<p>Bibrulers are linebased separators, used by <a href="https://visual-meta.info">visual-meta</a> as a means of organizing BibTags:</p>

<pre><code>@{visual-meta-start}
@{visual-meta-header-start}
@visual-meta{
 version = {1.1},
 generator = {Author 7.6.2 (1064)},
}
@{visual-meta-header-end}
@{visual-meta-bibtex-self-citation-start}
@book{2021-12-08T10:57:03Z/TheFutureo,
author = {Frode Alexander Hegland},
editor = {Frode Alexander Hegland},
title = {The Future of Text ||},
...
</code></pre>

<p>This snippet would get decoded to this unnested array:</p>

<pre><code>[
  { ruler: `@{visual-meta-start}` },
  { ruler: `@{visual-meta-header-start}` },
  { tag: &quot;@visual-meta&quot;, props: { version: &quot;1.1&quot;, generator: &quot;Author 7.6.2 1064)&quot; } }
  { ruler: `@{visual-meta-bibgtex-self-citation-start}` },
  { tag: &quot;@book{2021-12-08T10:56:03Z/TheFutureo&quot;, ..... }
  ...
]
</code></pre>

<p>Why not a nested tree-structure? This kneejerk reaction should always be considered &lsquo;a last option&rsquo;.</p>

<blockquote>
<p>Bibrulers don&rsquo;t try to re-invent XML, they are rather promoting dumb, unnested lists, which are much faster/simpler to traverse &amp; implement in all languages.</p>
</blockquote>

<h1 id="what-are-tagbibs-fragments">What are tagbibs fragments</h1>

<p>Just like regular <a href="https://en.wikipedia.org/wiki/URI_fragment">URI Fragments</a> they hint the browser to focus anything (Bib)Tagged:</p>

<ul>
<li><code>https://website.com#@chores@todo</code></li>
<li><code>https://mastodon.io/myprofile/#@chores@todo</code></li>
<li><code>://3dworld.gltf#@chores@todo</code></li>
</ul>

<blockquote>
<p>Format: <code>#@&lt;bibtag&gt;[ + @&lt;bibtag&gt; + [ ... ] ]</code></p>
</blockquote>

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
