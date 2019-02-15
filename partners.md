---
title: Our Partners
layout: default
---
{% assign rows = site.partners.size | divided_by: 2.0 | ceil %}
{% for i in (1..rows) %}
  {% assign offset = forloop.index0 | times: 2 %}
  <div class="row">
    {% for author in site.partners limit:2 offset:offset %}
     <div class="col-md-6 mt-3">
          <div class="card h-100">
              <div class="card-body">
              <img class="align-self-center mr-3  float-right thumb-post" src="{{ site.baseurl}}{{author.image}}"
                             alt="{{page.title}}'s profile image" height="150" width="150">


                <p class="card-text">{{ author.content | strip_html | truncatewords: 50}}</p>


                <a href="{{ author.url }}" class="btn btn-dark">Read more about {{author.title}}</a>
              </div>
          </div>
    </div>
    {% endfor %}
  </div>
{% endfor %}
