---
layout: page
sitemap: false
permalink: /careers/
title: Careers
menu: about
---

<div class="alert alert-info text-center" role="alert">
  <div class="lead"><span style="font-weight: 600">We are hiring!</span> Check the jobs below and send your CV to <a href="mailto:jobs@ingelectus.com">jobs@ingelectus.com</a>.</div>
</div>


<table class="table table-sm table-hover table-responsive">
  <thead>
    <tr>
      <th>Code</th>
      <th>Location</th>
      <th>Job</th>
      <th>Seniority</th>
      <th>Employment</th>
    </tr>
  </thead>
  <tbody>
    {% assign jobs = site.jobs | sort: 'title' %}
    {% for job in jobs %}
      {% if job.active %}
        <tr>
          <td scope="row"><code>{{ job.code }}</code></td>
          <td>{{ job.location }}</td>
          <td><strong><a href="{{ job.url }}">{{ job.title }}</a></strong></td>
          <td>{{ job.seniority }}</td>
          <td>{{ job.temporarily }}</td>
        </tr>
      {% endif %}
    {% endfor %}
  </tbody>
</table>
