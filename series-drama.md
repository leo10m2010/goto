---
layout: main3
permalink: /series/Drama
title: "Series de Drama"
---

<main class="home" id="post" role="main" itemprop="mainContentOfPage" itemscope="itemscope" itemtype="http://schema.org/Blog">

 <div cold-md="12">
    <h2 class="top_h3"> Categoría Drama </h2>
  </div>
     
   {% assign post_news2 = site.posts | where:"tags", "Drama" %}
   {% assign post_news = post_news2 | where:"category", "series" %}
    <div id="grid" class="row flex-grid">
       {% for post in post_news %}
        <article data-toggle="tooltip" data-html="true" data-placement="bottom" class="box-item col-xs-4 col-sm-3 col-md-2 col-lg-2" itemscope="itemscope" itemtype="http://schema.org/BlogPosting" itemprop="blogPost">
                                <div class="box">
                                <div class="box-body">
                                    {% if post.image_carousel %}
                                        <div class="cover">
                                            <a onclick="mostrar()" href="{{ post.url | prepend: site.baseurl }}">
                                            <img src="https://res.cloudinary.com/imbriitneysam/image/upload/v1537239672/placeholder-min.png" data-url="{{ post.image_carousel }}" class="preload">
                                            </a>
                                            {% if post.category == 'series' %}
                                                <div class="series"> Serie </div>
                                                {% else %}
                                                <div class="peliculas"> Pelicula </div>
                                                {% endif %}
                                                {% if post.idioma == 'Latino' %}

                                                <div class="latino" title="Audio Latino"></div>


                                        {% else %}
                                                {% if post.idioma == 'Castellano' %}

                                                <div class="castellano" title="Audio Castellano"></div>

                                                {% else %}
                                                <div class="subtitulado" title="Audio Subtitulado"></div>

                                                {% endif %}

										{% endif %}
                                            <div class="titulo"> {{ post.calidad }} </div>
                                        </div>
                                    {% endif %}
                                    <div class="box-info">
                                        <div class="w3l-movie-text">
                                            <h6>
                                                <a onclick="mostrar()" class="post-link" href="{{ post.url | prepend: site.baseurl }}">
                                                        {{ post.title }}
                                                </a>
                                            </h6>
                                        </div>
                                    </div>
                                </div>
                                </div>
                        </article>
            {%endfor%}
    </div>


</main>