---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

{% include base_path %}

{% assign all_pubs = site.publications | sort: "date" | reverse %}
{% assign preprints = all_pubs | where: "category", "preprint" %}
{% assign pub_papers = all_pubs | where_exp: "item", "item.category != 'preprint'" %}
{% assign pubs_by_year = pub_papers | group_by_exp: "item", "item.date | date: '%Y'" %}

<div class="page-description">
Check out my <a href="https://scholar.google.com/citations?user=YOUR_ID" target="_blank" rel="noopener noreferrer">Google Scholar</a> for more information.
</div>

<div class="pub-list">

{% if preprints.size > 0 %}
<h2 class="pub-year">Preprints</h2>
<ol class="bibliography">
{% for post in preprints %}
  {% include publication-card.html %}
{% endfor %}
</ol>
{% endif %}

{% for year_group in pubs_by_year %}
<h2 class="pub-year">{{ year_group.name }}</h2>
<ol class="bibliography">
{% for post in year_group.items %}
  {% include publication-card.html %}
{% endfor %}
</ol>
{% endfor %}

</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  document.querySelectorAll('.pub-btn.abs').forEach(function (btn) {
    btn.addEventListener('click', function (e) {
      e.preventDefault();
      var target = document.getElementById(this.getAttribute('data-target'));
      if (target) target.classList.toggle('active');
      this.classList.toggle('active');
    });
  });

  var selfName = 'Shi Li';
  document.querySelectorAll('.pub-author').forEach(function (el) {
    el.innerHTML = el.innerHTML.replace(
      new RegExp('(' + selfName.replace(/[.*+?^${}()|[\]\\]/g, '\\$&') + ')', 'g'),
      '<em>$1</em>'
    );
  });
});
</script>
