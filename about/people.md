---
layout: page
title: "People"
date: 2016-01-06 12:20
navbar: About
subnavbar: People
---

<p class="lead">
  This is a list of people participating in the JLESC program.
  In case you are part of JLESC and not yet listed here, feel free to add yourself through a
  <a href="https://github.com/JLESC/jlesc.github.io/wiki/Editing-Data#editing-people"
     target="_blank">
    pull request on GitHub
  </a>.
</p>

<p>
  There are {% stats_for_position permanent %} people with a permanent position,
  {% stats_for_position post_doc %} post doctorates and {% stats_for_position phd %} PhD students
  among the total of {{ site.data.people | size }} listed individuals within JLESC.
</p>

<div class="table-responsive">
  <table id="people-db" class="table table-striped">
    <thead class="thead-default">
      <tr>
        <th class="col-name">Name</th>
        <th class="col-affiliation">Affiliation</th>
        <th class="col-position">Position</th>
        <th class="col-projects">
          <i class="fa fa-fw fa-cubes" title="participating in # projects"
             data-toggle="tooltip"></i>
        </th>
        <th class="col-leading">
          <i class="fa fa-fw fa-graduation-cap" title="leading # projects"
             data-toggle="tooltip"></i>
        </th>
        <th class="col-topics">Topics</th>
      </tr>
    </thead>
    <tbody>
    {% for person_hash in site.data.people %}
      {% assign person_id = person_hash[0] %}
      {% assign person = person_hash[1] %}
      <tr>
        <td class="col-name">
          {% person_noaffi_inverse {{ person_id }} %}
          <div class="btn-group btn-group-sm pull-right" role="group">
            {% if person.email %}
              {% assign email = person.email | obfuscate_email %}
              <a target="_blank"
                 class="btn btn-link btn-sm email-obfuscated"
                 title="write an email to {{ person.given_name }} {{ person.sur_name }}"
                 data-email="{{ email }}"
                 role="button"
                 data-toggle="tooltip">
                <i class="fa fa-envelope fa-fw"></i>
              </a>
            {% endif %}
            {% if person.homepage %}
              <a href="{{ person.homepage }}"
                 target="_blank"
                 title="Homepage of {{ person.given_name }} {{ person.sur_name }}"
                 class="btn btn-link btn-sm"
                 role="button"
                 data-toggle="tooltip">
                <i class="fa fa-home fa-fw"></i>
              </a>
            {% endif %}
          </div>
        </td>
        <td class="col-affiliation">
          {% for affi in person.affiliation %}
            {% institute_short {{ affi }} %}
            {% unless forloop.last %}
              ,
            {% endunless %}
          {% endfor %}
        </td>
        <td class="col-position">{% person_position {{ person.position }} %}</td>
        <td class="col-projects">{% projects_for_person {{ person_id }} %}</td>
        <td class="col-leading">{% leading_for_person {{ person_id }} %}</td>
        <td class="col-topics">{{ person.topics }}</td>
      </tr>
    {% endfor %}
    </tbody>
  </table>
</div>