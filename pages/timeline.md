---
layout: default
title: "Timeline"
permalink: /timeline/
---
Hopefully there will be a nice timeline here soon!

## Timeline of Events 
<div class="timeline-container">
  <div class="timeline">
 {% for event in site.data.timeline %}
      {% assign side = forloop.index | modulo: 2 %}
      <div class="timeline-item {% if side == 0 %}left{% else %}right{% endif %}">
        <div class="content">
          <h3>{{ event.title }}</h3>
          <p>
            <a class="collapse-toggle" data-toggle="collapse" href="#collapse{{ forloop.index }}" role="button" aria-expanded="false" aria-controls="collapse{{ forloop.index }}">
              <i class="fas fa-chevron-down rotate-icon"></i>
            </a>
          </p>
          <div class="collapse" id="collapse{{ forloop.index }}">
            <p>{{ event.details }}</p>
          </div>
        </div>
      </div>
    {% endfor %}
  </div>
</div>

[Back to Home]({{ site.baseurl }}/)