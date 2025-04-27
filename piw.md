---
layout: page
title: Pfingsten in Westernohe 2025
description: "Pfingsten in Westernohe 2025"
permalink: /piw/
weight: 1
---
<div class="alert alert-success mb-5" role="alert">
  <p class="lead mb-0">
    Wir laden alle Mitglieder der Roverstufe und ihre Leiter\*innen ins Café mit(be)Stimmung am Wespennest ein. Wie in den vergangenen Jahren ist unser Café Anlauf- und Treffpunkt für Rover\*innen und ihre Leiter\*innen.
Zusätzlich zu Kaffee, Kaltgetränken und Süßspeisen wird es auch in diesem Jahr wieder verschiedene Spezialangebote geben.
Unsere Inhaltlichen Angebote finden in und um das Wespennest statt.
  </p>
</div>

<div class="container my-5">

<h2 class="text-center mb-4">Programm­übersicht</h2>
<p class="lead text-center">
  Stand {{ site.time | date: "%d.%m.%Y" }} &nbsp;–&nbsp;
  klicke auf einen Tag, um die Workshops anzuzeigen.
</p>

<!-- Samstag ------------------------------------------------------------->
{% assign samstag = site.data.programmpiw | where_exp:"w","w.sa and w.sa != '-' and w.sa != ''" %}

<details class="mb-4" open>
  <summary class="h4 fw-bold cursor-pointer py-2">
    Samstag&nbsp;({{ samstag | size }} Workshops)
  </summary>

  <div class="table-responsive ">
    <table class="table table-striped table-hover table-borderless ">
      <thead class="thead-dark">
        <tr>
            <th class="text-wrap">Workshop</th>
            <th class="text-wrap">Uhrzeit</th>
            <th class="text-wrap">Dauer</th>
            <th class="text-wrap">Raum</th>
            <th class="text-wrap">Beschreibung</th>
        </tr>
      </thead>
        <tbody>
        {% for w in samstag %}
        <tr>
            <td><strong>{{ w.name }}</strong></td>
            <td>{{ w.sa }}</td>
            <td>
            {% if w.dauer and w.dauer != '' %}
                <span class="badge bg-primary">{{ w.dauer }}</span>
            {% endif %}
            </td>
            <td>
            {% if w.raum and w.raum != '' %}
                <span class="badge bg-secondary">{{ w.raum }}</span>
            {% endif %}
            </td>
            <td class="text-wrap">
            {% if w.name contains "Zumba" or w.name contains "Yoga" or w.name contains "ROVERROX" %}
                🏃‍♂️
            {% elsif w.name contains "Naturkosmetik" or w.name contains "Müsliriegel" or w.name contains "Wetbag" %}
                🛠️
            {% elsif w.name contains "Traumreisen" or w.name contains "Entspannung" %}
                🌙
            {% elsif w.name contains "Psychische Gesundheit" %}
                🧠
            {% elsif w.name contains "Stammtisch" %}
                ☕
            {% else %}
                ✨
            {% endif %}
            {{ w.besch }}
            </td>
        </tr>
        {% endfor %}
        </tbody>
    </table>
  </div>
</details>

<!-- Sonntag ------------------------------------------------------------->
{% assign sonntag = site.data.programmpiw | where_exp:"w","w.so and w.so != '-' and w.so != ''" %}

<details>
  <summary class="h4 fw-bold cursor-pointer py-2">
    Sonntag&nbsp;({{ sonntag | size }} Workshops)
  </summary>

  <div class="table-responsive ">
    <table class="table table-striped table-hover table-borderless ">
      <thead class="thead-dark">
        <tr>
            <th class="text-wrap">Workshop</th>
            <th class="text-wrap">Uhrzeit</th>
            <th class="text-wrap">Dauer</th>
            <th class="text-wrap">Raum</th>
            <th class="text-wrap">Beschreibung</th>
        </tr>
      </thead>
        <tbody>
        {% for w in sonntag %}
        <tr>
            <td><strong>{{ w.name }}</strong></td>
            <td>{{ w.sa }}</td>
            <td>
            {% if w.dauer and w.dauer != '' %}
                <span class="badge bg-primary">{{ w.dauer }}</span>
            {% endif %}
            </td>
            <td>
            {% if w.raum and w.raum != '' %}
                <span class="badge bg-secondary">{{ w.raum }}</span>
            {% endif %}
            </td>
            <td class="text-wrap">
            {% if w.name contains "Zumba" or w.name contains "Yoga" or w.name contains "ROVERROX" %}
                🏃‍♂️
            {% elsif w.name contains "Naturkosmetik" or w.name contains "Müsliriegel" or w.name contains "Wetbag" %}
                🛠️
            {% elsif w.name contains "Traumreisen" or w.name contains "Entspannung" %}
                🌙
            {% elsif w.name contains "Psychische Gesundheit" %}
                🧠
            {% elsif w.name contains "Stammtisch" %}
                ☕
            {% else %}
                ✨
            {% endif %}
            {{ w.besch }}
            </td>
        </tr>
        {% endfor %}
        </tbody>
    </table>
  </div>
</details>

</div>