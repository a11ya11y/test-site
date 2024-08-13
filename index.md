---
layout: default
title: 'Web Accessibility Guidance project'
summary: 'Guidance that makes it easier to learn how to make web content accessible and meet the New Zealand Web Accessibility Standard.'
homepage: true
---

<h2 id="page-title">Guidance</h2>

<div class="status" role="note">
	<p><strong>Note:</strong> This guidance is in continual development. It is safe to use, but updates to improve it are ongoing.</p>
	<p>If you would like to contribute by writing new guidance, or if you have any feedback, please email <a href="mailto:web.standards@dia.govt.nz">web.standards@dia.govt.nz</a>.</p>
</div>

<div class="callout-note recent" role="note">
	<p>See a list of the <a href="recent.html">most recently added guidance</a>.</p>
</div>

<div class="guidance">

{%- assign dirs = site.data.dirs.dirs -%}

{%- assign colls = site.collections | sort: "order" -%}
{%- for item in colls -%}
	{%- if item.label != "posts" -%}
<div>
<h3>{{ dirs[item.label].title }}</h3>
{%- assign pages = site[item.label] | sort: "order" -%}
{%- if item.label != "ka" -%}
<ul>
		{%- for p in pages -%}
			{%- if p.group == item.label -%}
	<li><a href="{{ site.baseurl }}{{ p.url | remove: 'index.html' }}">{{ p.title }}</a></li>
			{%- endif -%}
		{%- endfor -%}  
</ul>
{%- elsif item.label == "ka" -%}
		{%- for p in pages -%}
			{%- if p.group == item.label -%}
	<h4>{{ p.title }}</h4>
				{%- if p.is_subhub -%}
					{%- assign pages = pages | sort: "order" -%}
	<ul>
						{%- for sp in pages -%} 
			    			{%- if sp.subhub == p.is_subhub  -%}
			 <li><a href="{{ site.baseurl }}{{ sp.url | remove: 'index.html' }}">{{ sp.short_title | default: sp.title }}</a></li>
			 					{%- endif -%}
			 			{%- endfor -%}
	</ul>
				{%- endif -%}
			{%- endif -%}
		{%- endfor -%}  

{%- endif -%}
</div>
	{%- endif -%}
{%- endfor -%}
</div>

<div class="about">
	<h2>About the project</h2>
	<p>See the following pages:</p>
	<ul>
		<li><a href="/web-a11y-guidance/about.html">About the Web Accessibility Guidance project</a></li>
		<li><a href="/web-a11y-guidance/background.html">Background to the Web Accessibility Guidance project</a></li>
	</ul>
</div>