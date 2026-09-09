---
layout: about
title: 
permalink: /
subtitle: Ganztagsschule in Angebotsform

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: true
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts

images:
  compare: true
  slider: true
---


<style>
  .post-swiper {
    width: 100%;
    position: relative;
    padding-bottom: 3.5rem;
  }

  .post-swiper swiper-slide {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    position: relative;
  }

  .post-swiper .swiper-post-link {
    display: block;
    width: 100%;
    text-decoration: none;
  }

  .post-swiper .swiper-image-wrapper {
    width: 100%;
    aspect-ratio: 3 / 2;
    overflow: hidden;
    position: relative;
    border-radius: 0.25rem;
  }

  .post-swiper .swiper-image-wrapper img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    display: block;
  }

  /* Bildunterschrift garantiert unterhalb des Bildes */
  .post-swiper .swiper-post-title {
    position: relative;
    z-index: 2;
    width: 100%;
    margin-top: 1rem;
    text-align: center;
    font-size: 1.1rem;
    font-weight: 500;
    line-height: 1.4;
    color: inherit;
  }

  /* Punkte am unteren Rand des Bildes */
  .post-swiper::part(pagination) {
    bottom: 3.25rem;
  }
</style>

<swiper-container
  class="post-swiper"
  keyboard="true"
  navigation="true"
  pagination="true"
  pagination-clickable="true"
  pagination-dynamic-bullets="true"
  rewind="true"
>
  {% for post in site.posts limit:3 %}
    <swiper-slide>
      <a href="{{ post.url | relative_url }}" class="swiper-post-link">
        <div class="swiper-image-wrapper">
          {% if post.thumbnail %}
            <img
              src="{{ post.thumbnail | relative_url }}"
              alt="{{ post.title }}"
              loading="lazy"
            >
          {% endif %}
        </div>
      </a>

      <div class="swiper-post-title">
        {{ post.title }}
      </div>
    </swiper-slide>
  {% endfor %}
</swiper-container>
