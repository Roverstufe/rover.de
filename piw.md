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

{% assign alle_workshops = site.data.programmpiw %}

<!-- Samstag -->
<details class="mb-4" open>
  <summary class="h4 fw-bold cursor-pointer py-2 d-flex justify-content-between align-items-center">
    <span>Samstag</span>
    <span class="chevron-icon">▶️</span>
  </summary>

  <div class="table-responsive mt-3">
    <table class="table table-striped table-hover table-borderless">
      <thead>
        <tr>
          <th>Workshop</th>
          <th>Uhrzeit</th>
          <th>Dauer</th>
          <th>Raum</th>
          <th>Beschreibung</th>
        </tr>
      </thead>
      <tbody>
      {% for w in alle_workshops %}
        {% if w.sa and w.sa != "-" and w.sa != "" %}
        <tr>
          <td><strong>{{ w.name }}</strong></td>
          <td>{{ w.sa }}</td>
          <td>
            {% if w.dauer %}
              <span class="badge bg-primary">{{ w.dauer }}</span>
            {% endif %}
          </td>
          <td>
            {% if w.raum %}
              <span class="badge bg-secondary">{{ w.raum }}</span>
            {% endif %}
          </td>
          <td class="text-wrap">
            {% if w.name contains "Zumba" or w.name contains "Yoga" or w.name contains "ROVERROX" %}
              <span class="emoji">🏃‍♂️</span>
            {% elsif w.name contains "Naturkosmetik" or w.name contains "Müsliriegel" or w.name contains "Wetbag" %}
              <span class="emoji">🛠️</span>
            {% elsif w.name contains "Traumreisen" or w.name contains "Entspannung" %}
              <span class="emoji">🌙</span>
            {% elsif w.name contains "Psychische Gesundheit" %}
              <span class="emoji">🧠</span>
            {% elsif w.name contains "Stammtisch" %}
              <span class="emoji">☕</span>
            {% else %}
              <span class="emoji">✨</span>
            {% endif %}
            {{ w.besch }}
          </td>
        </tr>
        {% endif %}
      {% endfor %}
      </tbody>
    </table>
  </div>
</details>

<!-- Sonntag -->
<details>
  <summary class="h4 fw-bold cursor-pointer py-2 d-flex justify-content-between align-items-center">
    <span>Sonntag</span>
    <span class="chevron-icon">▶️</span>
  </summary>

  <div class="table-responsive mt-3">
    <table class="table table-striped table-hover table-borderless">
      <thead>
        <tr>
          <th>Workshop</th>
          <th>Uhrzeit</th>
          <th>Dauer</th>
          <th>Raum</th>
          <th>Beschreibung</th>
        </tr>
      </thead>
      <tbody>
      {% for w in alle_workshops %}
        {% if w.so and w.so != "-" and w.so != "" %}
        <tr>
          <td><strong>{{ w.name }}</strong></td>
          <td>{{ w.so }}</td>
          <td>
            {% if w.dauer %}
              <span class="badge bg-primary">{{ w.dauer }}</span>
            {% endif %}
          </td>
          <td>
            {% if w.raum %}
              <span class="badge bg-secondary">{{ w.raum }}</span>
            {% endif %}
          </td>
          <td class="text-wrap">
            {% if w.name contains "Zumba" or w.name contains "Yoga" or w.name contains "ROVERROX" %}
              <span class="emoji">🏃‍♂️</span>
            {% elsif w.name contains "Naturkosmetik" or w.name contains "Müsliriegel" or w.name contains "Wetbag" %}
              <span class="emoji">🛠️</span>
            {% elsif w.name contains "Traumreisen" or w.name contains "Entspannung" %}
              <span class="emoji">🌙</span>
            {% elsif w.name contains "Psychische Gesundheit" %}
              <span class="emoji">🧠</span>
            {% elsif w.name contains "Stammtisch" %}
              <span class="emoji">☕</span>
            {% else %}
              <span class="emoji">✨</span>
            {% endif %}
            {{ w.besch }}
          </td>
        </tr>
        {% endif %}
      {% endfor %}
      </tbody>
    </table>
  </div>
</details>

</div>

<!-- Stil -->
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

.text-wrap .emoji {
  font-size: 1.4em;
  vertical-align: middle;
  margin-right: 0.25em;
}

.highlight {
  background-color: #fff9c4;
  animation: pulse 0.5s ease;
}
.first-match {
  background-color: #c8f7c5;
  animation: flash 0.8s ease;
}
.reset-glow {
  animation: glow 0.5s ease;
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.02); }
  100% { transform: scale(1); }
}

@keyframes flash {
  0% { background-color: #c8f7c5; }
  50% { background-color: #a3e4a5; }
  100% { background-color: #c8f7c5; }
}

@keyframes glow {
  0% { box-shadow: 0 0 5px #00c853; }
  50% { box-shadow: 0 0 15px #00e676; }
  100% { box-shadow: 0 0 5px #00c853; }
}
</style>

<!-- Suche -->
<script>
document.addEventListener('DOMContentLoaded', function () {
  const input = document.getElementById('workshopSearch');
  const resetButton = document.getElementById('resetSearch');

  input.addEventListener('input', function () {
    const filter = input.value.toLowerCase();
    const rows = document.querySelectorAll('tbody tr');

    resetButton.style.display = filter ? 'block' : 'none';

    let firstMatchFound = false;

    rows.forEach(row => {
      const name = row.querySelector('td strong')?.innerText.toLowerCase() || '';
      const beschreibung = row.querySelector('td.text-wrap')?.innerText.toLowerCase() || '';
      const raum = row.querySelector('td span.bg-secondary')?.innerText.toLowerCase() || '';

      const fulltext = name + ' ' + beschreibung + ' ' + raum;

      row.classList.remove('highlight', 'first-match');

      if (fulltext.includes(filter) && filter !== '') {
        row.style.display = '';
        if (!firstMatchFound) {
          row.classList.add('first-match');
          firstMatchFound = true;
        } else {
          row.classList.add('highlight');
        }
      } else if (filter === '') {
        row.style.display = '';
      } else {
        row.style.display = 'none';
      }
    });
  });

  resetButton.addEventListener('click', function () {
    input.value = '';
    input.dispatchEvent(new Event('input'));
    resetButton.classList.add('reset-glow');
    setTimeout(() => resetButton.classList.remove('reset-glow'), 500);
  });
});
</script>
