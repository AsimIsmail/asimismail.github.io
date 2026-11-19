---
layout: default
title: Write-ups
permalink: /writeups/
---

<section class="writeups-page">

  <p class="section-label">// KNOWLEDGE BASE</p>

  <h1>Write-ups<span class="green">_</span></h1>

  <p class="blog-description">
    Technical walkthroughs, penetration testing experiences,
    and cybersecurity research.
  </p>

  <div class="blog-list">

    {% assign sorted_posts = site.posts | sort: "date" | reverse %}

    {% for post in sorted_posts %}

      <article class="blog-card">

        <p class="blog-meta">
          {{ post.date | date: "%d %B %Y" }}
        </p>

        <h2>
          <a href="{{ post.url | relative_url }}">
            {{ post.title }}
          </a>
        </h2>

        {% if post.excerpt %}
          <p class="blog-excerpt">
            {{ post.excerpt | strip_html | truncate: 180 }}
          </p>
        {% endif %}

        <div class="post-tags">
          {% for category in post.categories %}
            <span class="post-tag">{{ category }}</span>
          {% endfor %}

          {% for tag in post.tags %}
            <span class="post-tag">{{ tag }}</span>
          {% endfor %}
        </div>

        <a class="text-link" href="{{ post.url | relative_url }}">
          Read write-up →
        </a>

      </article>

    {% endfor %}

    {% unless site.posts.size > 0 %}
      <p>No write-ups published yet.</p>
    {% endunless %}

  </div>

</section>
