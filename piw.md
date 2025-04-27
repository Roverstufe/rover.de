---
layout: page
title: Pfingsten in Westernohe 2025
description: "Pfingsten in Westernohe 2025"
permalink: /piw/
weight: 1
---

<div class="alert alert-success mb-5" role="alert">
  <p class="lead mb-0">
    Wir laden alle Mitglieder der Roverstufe und ihre Leiter\*innen ins Café mit(be)Stimmung am Wespennest ein. 
    Zusätzlich zu Kaffee, Kaltgetränken und Süßspeisen wird es auch in diesem Jahr wieder verschiedene Spezialangebote geben. 
    Unsere inhaltlichen Angebote finden in und um das Wespennest statt.
  </p>
</div>

<div class="container my-5">

<h2 class="text-center mb-4">Programm­übersicht</h2>
<p class="lead text-center">
  Stand {{ site.time | date: "%d.%m.%Y" }} &nbsp;–&nbsp;
  klicke auf einen Tag oder nutze die Suche unten.
</p>

<!-- Suchfeld + Reset-Button -->
<div class="my-4 text-center position-relative">
  <input id="workshopSearch" type="text" class="form-control w-50 mx-auto" placeholder="Workshop suchen...">
  <button id="resetSearch" type="button" class="btn-close position-absolute" style="top: 50%; right: 25%; transform: translateY(-50%); display: none;" aria-label="Reset"></button>
</div>

<!-- Samstag -->
{% assign samstag = site.data.programmpiw | where: "sa", "not -" %}
{{ samstag | size }}


<details class="mb-4" open>
  <summary class="h4 fw-bold cursor-pointer py-2 d-flex justify-content-between align-items-center">
    <span>Samstag&nbsp;({{ samstag | size }} Workshops)</span>
    <span class="chevron-icon">▶️</span>
  </summary>

  <div class="table-responsive mt-3">
    <table class="table table-striped table-hover table-borderless">
      <thead>
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

<!-- Sonntag -->
{% assign sonntag = site.data.programmpiw | where: "so", "not -" %}

<details>
  <summary class="h4 fw-bold cursor-pointer py-2 d-flex justify-content-between align-items-center">
    <span>Sonntag&nbsp;({{ sonntag | size }} Workshops)</span>
    <span class="chevron-icon">▶️</span>
  </summary>

  <div class="table-responsive mt-3">
    <table class="table table-striped table-hover table-borderless">
      <thead>
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
          <td>{{ w.so }}</td>
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

<!-- Stil & Animation -->
<style>
details summary .chevron-icon {
  transition: transform 0.3s ease;
  display: inline-block;
}
details[open] summary .chevron-icon {
  transform: rotate(90deg);
}

.table thead th {
  vertical-align: middle;
  padding-top: 1rem;
  padding-bottom: 1rem;
  font-weight: bold;
  font-size: 1.1rem;
}
.table tbody td {
  padding-top: 0.75rem;
  padding-bottom: 0.75rem;
  line-height: 1.4;
}
.table tbody td:first-child strong {
  font-size: 1.05rem;
}
details {
  margin-bottom: 2rem;
}
@media (max-width: 768px) {
  .table-responsive {
    overflow-x: auto;
  }
}

.highlight {
  background-color: #fff9c4;
  animation: pulse 0.5s ease;
}
@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.02); }
  100% { transform: scale(1); }
}
</style>

<!-- Suche + Reset-Button -->
<script>
document.addEventListener('DOMContentLoaded', function () {
  const input = document.getElementById('workshopSearch');
  const resetButton = document.getElementById('resetSearch');

  input.addEventListener('input', function () {
    const filter = input.value.toLowerCase();
    const rows = document.querySelectorAll('tbody tr');
    resetButton.style.display = filter ? 'block' : 'none';

    rows.forEach(row => {
      const text = row.innerText.toLowerCase();
      if (text.includes(filter) && filter !== '') {
        row.style.display = '';
        row.classList.add('highlight');
      } else if (filter === '') {
        row.style.display = '';
        row.classList.remove('highlight');
      } else {
        row.style.display = 'none';
        row.classList.remove('highlight');
      }
    });
  });

  resetButton.addEventListener('click', function () {
    input.value = '';
    input.dispatchEvent(new Event('input'));
  });
});
</script>
