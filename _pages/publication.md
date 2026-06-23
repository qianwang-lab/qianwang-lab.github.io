---
title: ""
permalink: /publication/
layout: page
---

<!-- Tab Navigation -->
<div class="miil-tabs">
  <button class="miil-tab active" onclick="miilTab(event, 'journal')">Journal Papers</button>
  <button class="miil-tab" onclick="miilTab(event, 'conference')">Conference Papers</button>
  <button class="miil-tab" onclick="miilTab(event, 'misc')">Misc</button>
</div>

<!-- Journal Tab -->
<div id="journal" class="miil-tab-content active">
{% for pub in site.data.publications_journal %}
<div class="miil-pub-item">
  <span class="pub-title"><a href="{{ pub.url }}">{{ pub.title }}</a></span><br>
  {{ pub.authors }}<br>
  <span class="pub-journal">{{ pub.journal }}</span>{% if pub.volume %}, vol. {{ pub.volume }}{% endif %}{% if pub.number %}, no. {{ pub.number }}{% endif %}{% if pub.pages %}, pp. {{ pub.pages }}{% endif %}{% if pub.month %}, {{ pub.month }}{% endif %} {% if pub.year %}{{ pub.year }}{% endif %}{% if pub.note %} — <em>{{ pub.note }}</em>{% endif %}
</div>
{% endfor %}
</div>

<!-- Conference Tab -->
<div id="conference" class="miil-tab-content">
{% for pub in site.data.publications_conference %}
<div class="miil-pub-item">
  <span class="pub-title"><a href="{{ pub.url }}">{{ pub.title }}</a></span><br>
  {{ pub.authors }}<br>
  <span class="pub-journal">{{ pub.venue }}</span>{% if pub.location %}, {{ pub.location }}{% endif %}{% if pub.year %}, {{ pub.year }}{% endif %}{% if pub.note %} — <em>{{ pub.note }}</em>{% endif %}
</div>
{% endfor %}
</div>

<!-- Misc Tab -->
<div id="misc" class="miil-tab-content">
{% for pub in site.data.publications_misc %}
<div class="miil-pub-item">
  <span class="pub-title"><a href="{{ pub.url }}">{{ pub.title }}</a></span><br>
  {{ pub.authors }}<br>
  <span class="pub-journal">{{ pub.journal }}</span>, {{ pub.year }}
</div>
{% else %}
<p>Coming soon.</p>
{% endfor %}
</div>

<script>
function miilTab(evt, tabId) {
  var i, tabcontent, tablinks;
  tabcontent = document.getElementsByClassName("miil-tab-content");
  for (i = 0; i < tabcontent.length; i++) {
    tabcontent[i].classList.remove("active");
  }
  tablinks = document.getElementsByClassName("miil-tab");
  for (i = 0; i < tablinks.length; i++) {
    tablinks[i].classList.remove("active");
  }
  document.getElementById(tabId).classList.add("active");
  evt.currentTarget.classList.add("active");
}
</script>
