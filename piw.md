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

<h2 class="text-center mb-4">Programmübersicht</h2>
<p class="lead text-center">
  Stand {{ site.time | date: "%d.%m.%Y" }} &nbsp;–&nbsp;
  klicke auf einen Tag oder nutze die Suche unten.
</p>

<!-- Suchfeld + Reset-Button -->
<div class="my-4 text-center position-relative">
  <input id="workshopSearch" type="text" class="form-control w-50 mx-auto" placeholder="Workshop suchen...">
  <button id="resetSearch" type="button" class="reset-button position-absolute" style="top: 50%; right: 25%; transform: translateY(-50%); display: none;" aria-label="Reset">❌</button>
</div>
<div id="searchResults" class="list-group my-4" style="display: none;"></div>

{% assign alle_workshops = site.data.programmpiw %}

<!-- Freitag -->
{% assign freitag = alle_workshops | where_exp: "item", "item.fr and item.fr != '-' and item.fr != ''" | sort: "sortzeit_fr" %}
<details class="mb-4" open>
  <summary class="h4 fw-bold cursor-pointer py-2 d-flex justify-content-between align-items-center">
    <span>Freitag</span>
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
      {% for w in freitag %}
        <tr class="d-block d-md-table-row border" data-tag="Freitag" data-sortzeit="{{ w.sortzeit_fr }}">
          <td data-label="Workshop"><strong>{{ w.name }}</strong></td>
          <td data-label="Uhrzeit">{{ w.fr }}</td>
          <td data-label="Dauer">{% if w.dauer %}<span class="badge bg-primary">{{ w.dauer }}</span>{% endif %}</td>
          <td data-label="Raum">{% if w.raum %}<span class="badge bg-secondary">{{ w.raum }}</span>{% endif %}</td>
          <td class="text-wrap" data-label="Beschreibung">
            {% if w.name contains "Zumba" or w.name contains "Yoga" or w.name contains "ROVERROX" %}🏃‍♂️
            {% elsif w.name contains "Naturkosmetik" or w.name contains "Müsliriegel" or w.name contains "Wetbag" %}🛠️
            {% elsif w.name contains "Traumreisen" or w.name contains "Entspannung" %}🌙
            {% elsif w.name contains "Psychische Gesundheit" %}🧠
            {% elsif w.name contains "Stammtisch" %}☕
            {% else %}✨{% endif %}
            {{ w.besch }}
          </td>
        </tr>
      {% endfor %}
      </tbody>
    </table>
  </div>
</details>

<!-- Samstag -->
{% assign samstag = alle_workshops | where_exp: "item", "item.sa and item.sa != '-' and item.sa != ''" | sort: "sortzeit_sa" %}
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
      {% for w in samstag %}
        <tr class="d-block d-md-table-row border" data-tag="Samstag" data-sortzeit="{{ w.sortzeit_sa }}">
          <td data-label="Workshop"><strong>{{ w.name }}</strong></td>
          <td data-label="Uhrzeit">{{ w.sa }}</td>
          <td data-label="Dauer">{% if w.dauer %}<span class="badge bg-primary">{{ w.dauer }}</span>{% endif %}</td>
          <td data-label="Raum">{% if w.raum %}<span class="badge bg-secondary">{{ w.raum }}</span>{% endif %}</td>
          <td class="text-wrap" data-label="Beschreibung">
            {% if w.name contains "Zumba" or w.name contains "Yoga" or w.name contains "ROVERROX" %}🏃‍♂️
            {% elsif w.name contains "Naturkosmetik" or w.name contains "Müsliriegel" or w.name contains "Wetbag" %}🛠️
            {% elsif w.name contains "Traumreisen" or w.name contains "Entspannung" %}🌙
            {% elsif w.name contains "Psychische Gesundheit" %}🧠
            {% elsif w.name contains "Stammtisch" %}☕
            {% else %}✨{% endif %}
            {{ w.besch }}
          </td>
        </tr>
      {% endfor %}
      </tbody>
    </table>
  </div>
</details>

<!-- Sonntag -->
{% assign sonntag = alle_workshops | where_exp: "item", "item.so and item.so != '-' and item.so != ''" | sort: "sortzeit_so" %}
<details open>
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
      {% for w in sonntag %}
        <tr class="d-block d-md-table-row border" data-tag="Sonntag" data-sortzeit="{{ w.sortzeit_so }}">
          <td data-label="Workshop"><strong>{{ w.name }}</strong></td>
          <td data-label="Uhrzeit">{{ w.so }}</td>
          <td data-label="Dauer">{% if w.dauer %}<span class="badge bg-primary">{{ w.dauer }}</span>{% endif %}</td>
          <td data-label="Raum">{% if w.raum %}<span class="badge bg-secondary">{{ w.raum }}</span>{% endif %}</td>
          <td class="text-wrap" data-label="Beschreibung">
            {% if w.name contains "Zumba" or w.name contains "Yoga" or w.name contains "ROVERROX" %}🏃‍♂️
            {% elsif w.name contains "Naturkosmetik" or w.name contains "Müsliriegel" or w.name contains "Wetbag" %}🛠️
            {% elsif w.name contains "Traumreisen" or w.name contains "Entspannung" %}🌙
            {% elsif w.name contains "Psychische Gesundheit" %}🧠
            {% elsif w.name contains "Stammtisch" %}☕
            {% else %}✨{% endif %}
            {{ w.besch }}
          </td>
        </tr>
      {% endfor %}
      </tbody>
    </table>
  </div>
</details>

</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  const input = document.getElementById('workshopSearch');
  const resetButton = document.getElementById('resetSearch');
  const searchResults = document.getElementById('searchResults');
  const allRows = document.querySelectorAll('tbody tr');

  input.addEventListener('input', function () {
    const filter = input.value.toLowerCase();
    searchResults.innerHTML = '';

    if (filter !== '') {
      resetButton.style.display = 'block';
      const matches = [];

      allRows.forEach(row => {
        const text = row.innerText.toLowerCase();
        if (text.includes(filter)) {
          const name = row.querySelector('[data-label="Workshop"] strong')?.innerText || '';
          const time = row.querySelector('[data-label="Uhrzeit"]')?.innerText || '';
          const desc = row.querySelector('[data-label="Beschreibung"]')?.innerText || '';
          const tag = row.getAttribute('data-tag') || 'Unbekannt';
          const sortzeit = parseInt(row.getAttribute('data-sortzeit')) || 9999;

          matches.push({ tag, sortzeit, html: `
            <div class="list-group-item">
              <div><strong>${name}</strong></div>
              <small><strong>${tag}</strong> – ${time}</small>
              <div>${desc}</div>
            </div>
          ` });
        }
      });

      matches.sort((a, b) => {
        const dayOrder = ['Freitag', 'Samstag', 'Sonntag'];
        const dayA = dayOrder.indexOf(a.tag);
        const dayB = dayOrder.indexOf(b.tag);
        if (dayA !== dayB) return dayA - dayB;
        return a.sortzeit - b.sortzeit;
      });

      if (matches.length > 0) {
        matches.forEach(m => {
          const div = document.createElement('div');
          div.innerHTML = m.html;
          searchResults.appendChild(div.firstElementChild);
        });
        searchResults.style.display = 'block';
      } else {
        searchResults.innerHTML = '<div class="list-group-item">Keine Treffer gefunden.</div>';
        searchResults.style.display = 'block';
      }
    } else {
      resetButton.style.display = 'none';
      searchResults.style.display = 'none';
    }
  });

  resetButton.addEventListener('click', function () {
    input.value = '';
    input.dispatchEvent(new Event('input'));
    resetButton.classList.add('reset-glow');
    setTimeout(() => resetButton.classList.remove('reset-glow'), 500);
  });
});
</script>