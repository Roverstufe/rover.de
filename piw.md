---
layout: page
title: Pfingsten in Westernohe 2025
description: "Pfingsten in Westernohe 2025"
permalink: /piw/
weight: 1
---

<div class="alert alert-warning mb-5" role="alert">
  <p class="lead mb-0">
    Wir laden alle Mitglieder der Roverstufe und ihre Leiter\*innen ins Café am Wespennest ein. 
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
  <button id="resetSearch" type="button" class="reset-button position-absolute" style="top: 50%; right: 25%; transform: translateY(-50%); display: none;" aria-label="Reset">❌</button>
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
      <thead class="d-none d-md-table-header-group">
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
        <tr class="d-block d-md-table-row border">
          <td data-label="Workshop"><strong>{{ w.name }}</strong></td>
          <td data-label="Uhrzeit">{{ w.sa }}</td>
          <td data-label="Dauer">
            {% if w.dauer %}
              <span class="badge bg-primary">{{ w.dauer }}</span>
            {% endif %}
          </td>
          <td data-label="Raum">
            {% if w.raum %}
              <span class="badge bg-secondary">{{ w.raum }}</span>
            {% endif %}
          </td>
          <td class="text-wrap" data-label="Beschreibung">
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
      <thead class="d-none d-md-table-header-group">
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
        <tr class="d-block d-md-table-row border">
          <td data-label="Workshop"><strong>{{ w.name }}</strong></td>
          <td data-label="Uhrzeit">{{ w.so }}</td>
          <td data-label="Dauer">
            {% if w.dauer %}
              <span class="badge bg-primary">{{ w.dauer }}</span>
            {% endif %}
          </td>
          <td data-label="Raum">
            {% if w.raum %}
              <span class="badge bg-secondary">{{ w.raum }}</span>
            {% endif %}
          </td>
          <td class="text-wrap" data-label="Beschreibung">
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
/* Basis */
details summary .chevron-icon {
  transition: transform 0.4s ease;
  display: inline-block;
}
details[open] summary .chevron-icon {
  transform: rotate(90deg) scale(1.2);
}
details summary:hover {
  background-color: #d6eefe;
  cursor: pointer;
}
details[open] > summary {
  background-color: #e9f5ff;
  border-radius: 0.5rem;
  padding: 0.75rem;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}
details[open] > div {
  animation: fadeIn 0.6s ease;
}

.reset-button {
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
  line-height: 1;
}
.reset-button:focus {
  outline: none;
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
.text-wrap .emoji {
  font-size: 1.4em;
  vertical-align: middle;
  margin-right: 0.25em;
}

/* Mobile Ansicht */
@media (max-width: 767.98px) {
  .table-responsive {
    overflow-x: unset;
  }
  td[data-label] {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    margin: 0;
    background: #f8f9fa;
    border-radius: 0.5rem;
    box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    margin-bottom: 0.5rem;
  }
  td[data-label]::before {
    content: attr(data-label);
    font-weight: 600;
    margin-right: 1rem;
    color: #333;
    min-width: 100px;
  }
  tr.d-block.d-md-table-row.border {
    border: none;
    margin-bottom: 1rem;
  }
  .text-wrap .emoji {
    font-size: 1.8em;
    margin-right: 0.5em;
  }
  td[data-label="Workshop"] strong {
    font-size: 1.25rem;
    font-weight: 700;
    color: #212529;
  }
  td[data-label="Raum"] span.badge {
    background-color: #dee2e6;
    color: #212529;
    font-weight: 600;
    padding: 0.6rem 0.8rem;
    border-radius: 0.5rem;
  }
}

/* Animationen */
@keyframes fadeIn {
  0% { opacity: 0; transform: translateY(-10px); }
  100% { opacity: 1; transform: translateY(0); }
}
@keyframes clickPulse {
  0% { transform: scale(1); }
  50% { transform: scale(0.98); }
  100% { transform: scale(1); }
}
tbody tr:active {
  animation: clickPulse 0.3s ease;
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