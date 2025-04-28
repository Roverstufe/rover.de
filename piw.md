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
<div id="searchResults" class="list-group my-4" style="display: none;"></div>

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
<details open>
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

<!-- Suche -->
<script>
document.addEventListener('DOMContentLoaded', function () {
  const input = document.getElementById('workshopSearch');
  const resetButton = document.getElementById('resetSearch');
  const searchResults = document.getElementById('searchResults');
  const allDetails = document.querySelectorAll('details');

  input.addEventListener('input', function () {
    const filter = input.value.toLowerCase();
    let matchCount = 0;

    // Trefferliste leeren
    searchResults.innerHTML = '';

    if (filter !== '') {
      resetButton.style.display = 'block';

      allDetails.forEach(detail => {
        detail.style.display = 'none'; // Tagesstruktur ausblenden

        const rows = detail.querySelectorAll('tbody tr');

        rows.forEach(row => {
          const textContent = row.innerText.toLowerCase();

          if (textContent.includes(filter)) {
            matchCount++;

            const workshopName = row.querySelector('[data-label="Workshop"] strong')?.innerText || 'Workshop';
            const time = row.querySelector('[data-label="Uhrzeit"]')?.innerText || '';
            const description = row.querySelector('[data-label="Beschreibung"]')?.innerText || '';

            // Icon und Farbe basierend auf Workshop-Namen bestimmen
            let emoji = '✨';
            let colorClass = 'card-default';

            if (workshopName.toLowerCase().includes('zumba') || workshopName.toLowerCase().includes('yoga') || workshopName.toLowerCase().includes('roverrox')) {
              emoji = '🏃‍♂️';
              colorClass = 'card-sport';
            } else if (workshopName.toLowerCase().includes('naturkosmetik') || workshopName.toLowerCase().includes('müsliriegel') || workshopName.toLowerCase().includes('wetbag')) {
              emoji = '🛠️';
              colorClass = 'card-creative';
            } else if (workshopName.toLowerCase().includes('traumreisen') || workshopName.toLowerCase().includes('entspannung')) {
              emoji = '🌙';
              colorClass = 'card-relax';
            } else if (workshopName.toLowerCase().includes('psychische gesundheit')) {
              emoji = '🧠';
              colorClass = 'card-health';
            } else if (workshopName.toLowerCase().includes('stammtisch')) {
              emoji = '☕';
              colorClass = 'card-coffee';
            }

            const resultItem = document.createElement('div');
            resultItem.className = `list-group-item ${colorClass}`;
            resultItem.innerHTML = `<div><span style="font-size: 1.5rem;">${emoji}</span> <strong>${workshopName}</strong></div><small>${time}</small><div>${description}</div>`;

            searchResults.appendChild(resultItem);
          }
        });
      });

      if (matchCount > 0) {
        searchResults.style.display = 'block';
      } else {
        searchResults.innerHTML = '<div class="list-group-item">Keine Treffer gefunden.</div>';
        searchResults.style.display = 'block';
      }
    } else {
      // Kein Filter eingegeben: alles wieder normal
      resetButton.style.display = 'none';
      searchResults.style.display = 'none';
      allDetails.forEach(detail => {
        detail.style.display = '';
        detail.open = true;
      });
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