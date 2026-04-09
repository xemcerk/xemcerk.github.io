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

{% if preprints.size > 0 %}
## Preprints
<div class="pub-list">
{% for post in preprints %}
  {% include publication-card.html %}
{% endfor %}
</div>
{% endif %}

## Publications
<div class="pub-list">
{% for year_group in pubs_by_year %}
  <h2 class="pub-year">{{ year_group.name }}</h2>
  {% for post in year_group.items %}
    {% include publication-card.html %}
  {% endfor %}
{% endfor %}
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  // Expand/collapse abstracts
  document.querySelectorAll('.abs-toggle').forEach(function (btn) {
    btn.addEventListener('click', function (e) {
      e.preventDefault();
      var target = document.getElementById(this.getAttribute('data-target'));
      if (target) target.classList.toggle('active');
      this.classList.toggle('active');
    });
  });

  // Bold author name
  var selfName = 'Shi Li';
  document.querySelectorAll('.pub-authors').forEach(function (el) {
    el.innerHTML = el.innerHTML.replace(
      new RegExp('(' + selfName.replace(/[.*+?^${}()|[\]\\]/g, '\\$&') + ')', 'g'),
      '<strong>$1</strong>'
    );
  });
});
</script>
