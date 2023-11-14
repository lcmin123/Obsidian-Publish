
# Welcome! 🌱

안녕하세요! 이창민의 <b>디지털 정원(Digital Garden)</b> 입니다.

<p style="padding: 3em 1em; background: #f5f7ff; border-radius: 4px;">
  Take a look at 이창민의 <span style="font-weight: bold">[[Digital Garden]]</span> to get started on your exploration.
</p>
- [[섹션 3, 4, 5, 6 - HTML]]
- [[섹션 14, 15 - JS Primary]]
- [[섹션 16]]

This digital garden template is free, open-source, and [available on GitHub here](https://github.com/maximevaillancourt/digital-garden-jekyll-template).

The easiest way to get started is to read this [step-by-step guide explaining how to set this up from scratch](https://maximevaillancourt.com/blog/setting-up-your-own-digital-garden-with-jekyll).

<strong>Recently updated notes</strong>

<ul>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_notes limit: 5 %}
    <li>
      {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ site.baseurl }}{{ note.url }}">{{ note.title }}</a>
    </li>
  {% endfor %}
</ul>

<style>
  .wrapper {
    max-width: 46em;
  }
</style>
