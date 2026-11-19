
---
layout: default
title: Blog
permalink: /blog/
---

<section class="blog-page">

  <p class="section-label">// KNOWLEDGE BASE</p>

  <h1>Cybersecurity Blog<span class="green">_</span></h1>

  <p class="blog-description">
    Write-ups, technical research, tutorials, and notes
    from my cybersecurity journey.
  </p>

  <div class="blog-list">

    {% assign sorted_posts = site.posts | sort: "date" | reverse %}

    {% for post in sorted_posts %}

      <article class="blog-card">

        <p class="blog-meta">
          {{ post.date | date: "%d %B %Y" }}
          {% for category in post.categories %}
            <span class="green"> / </span>{{ category }}
          {% endfor %}
        </p>

        <h2>
          <a href="{{ post.url | relative_url }}">
            {{ post.title }}
          </a>
        </h2>

        <p class="blog-excerpt">
          {{ post.excerpt | strip_html | truncate: 180 }}
        </p>

        <a class="text-link" href="{{ post.url | relative_url }}">
          Read article →
        </a>

      </article>

    {% endfor %}

    {% unless site.posts.size > 0 %}
      <p>No articles published yet. Check back soon!</p>
    {% endunless %}

  </div>

</section>
