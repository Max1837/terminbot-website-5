<!--
  terminbot-landing.html
  Fertige Single-File Landingpage für deinen TerminBot.
  Anleitung:
  1) Dein echter Calendly-Link ist bereits eingebaut: https://calendly.com/geislermax999
  2) Push die Datei zu GitHub (z.B. repository root). Auf GitHub Pages als Branch gh-pages oder main deployen.
  3) Optional: Passe Farben/Logo/Copy an.

  Technologien:
  - Tailwind CSS via CDN (schnelles Prototyping)
  - Calendly Inline-Widget + Popup
  - Responsives Layout, FAQ-Accordion
-->

<!doctype html>
<html lang="de">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>TerminBot — KI-Telefonassistent für Unternehmen</title>
  <meta name="description" content="TerminBot — Ihr virtueller Telefonassistent, 24/7. Automatische Terminvergabe per Anruf, Calendly-Integration, DSGVO-freundlich." />

  <!-- Tailwind CDN (Play) -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Calendly widget -->
  <link href="https://assets.calendly.com/assets/external/widget.css" rel="stylesheet">
  <script src="https://assets.calendly.com/assets/external/widget.js" type="text/javascript"></script>

  <style>
    /* Kleine, gezielte Ergänzungen zu Tailwind */
    .hero-bg{
      background-image: linear-gradient(120deg, rgba(99,102,241,0.12), rgba(99,102,241,0.04));
    }
    .glass{
      background: rgba(255,255,255,0.6);
      backdrop-filter: blur(6px);
    }
  </style>
</head>
<body class="antialiased text-gray-800 bg-gray-50">

  <!-- NAV -->
  <nav class="max-w-6xl mx-auto px-6 py-5 flex items-center justify-between">
    <div class="flex items-center gap-3">
      <div class="w-10 h-10 rounded-lg bg-indigo-600 flex items-center justify-center text-white font-bold">TB</div>
      <div>
        <a href="#" class="font-semibold text-xl">TerminBot</a>
        <div class="text-xs text-gray-500">KI-Anrufassistent für Unternehmen</div>
      </div>
    </div>
    <div class="hidden md:flex items-center gap-4">
      <a href="#features" class="hover:underline">Funktionen</a>
      <a href="#preise" class="hover:underline">Preise</a>
      <a href="#faq" class="hover:underline">FAQ</a>
      <button onclick="Calendly.initPopupWidget({url: 'https://calendly.com/geislermax999'});return false;" class="ml-2 px-4 py-2 bg-indigo-600 text-white rounded-lg shadow">Demo buchen</button>
    </div>
    <div class="md:hidden">
      <button id="mobile-menu-btn" class="px-3 py-2 border rounded">Menu</button>
    </div>
  </nav>

  <!-- HERO -->
  <header class="hero-bg">
    <div class="max-w-6xl mx-auto px-6 py-14">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-10 items-center">
        <div>
          <h1 class="text-4xl md:text-5xl font-extrabold leading-tight">Nie wieder verpasste Anrufe — <span class="text-indigo-600">TerminBot</span> übernimmt.</h1>
          <p class="mt-4 text-lg text-gray-600">Automatischer Telefonassistent mit direkter Calendly-Integration. Reduziere Personalkosten und erhöhe die Terminkonversion — 24/7.</p>

          <div class="mt-6 flex gap-3">
            <button onclick="Calendly.initPopupWidget({url: 'https://calendly.com/geislermax999'});return false;" class="px-6 py-3 bg-indigo-600 text-white rounded-lg shadow-lg">Jetzt Demo buchen</button>
            <a href="#features" class="px-6 py-3 border rounded-lg">Mehr erfahren</a>
          </div>

          <ul class="mt-6 grid grid-cols-1 sm:grid-cols-2 gap-3 text-sm text-gray-700">
            <li class="flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-indigo-500" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 00-1.414 0L8 12.586 4.707 9.293a1 1 0 10-1.414 1.414l4 4a1 1 0 001.414 0l8-8a1 1 0 000-1.414z" clip-rule="evenodd"/></svg>24/7 Erreichbarkeit</li>
            <li class="flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-indigo-500" viewBox="0 0 20 20" fill="currentColor"><path d="M6 2a1 1 0 00-1 1v14a1 1 0 001 1h8a1 1 0 001-1V3a1 1 0 00-1-1H6z"/></svg>Direkte Calendly-Anbindung</li>
            <li class="flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-indigo-500" viewBox="0 0 20 20" fill="currentColor"><path d="M2 5a2 2 0 012-2h4l2 2h6a2 2 0 012 2v6a2 2 0 01-2 2H6l-2-2H4a2 2 0 01-2-2V5z"/></svg>Individuelle Begrüßungen</li>
            <li class="flex items-center gap-2"><svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-indigo-500" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm1-11H9v4h2V7zm0 6H9v2h2v-2z" clip-rule="evenodd"/></svg>DSGVO-konform (EU-Hosting möglich)</li>
          </ul>

        </div>

        <!-- Embed Calendly inline as live demo on the right -->
        <div class="bg-white rounded-2xl shadow p-4 glass">
          <div class="text-sm text-gray-500 mb-2">Live Demo-Kalender</div>
          <div class="rounded overflow-hidden border" style="min-height:540px">
            <div class="calendly-inline-widget" data-url="https://calendly.com/geislermax999" style="min-width:320px;height:540px;"></div>
          </div>
          <div class="mt-4 text-xs text-gray-500">Hinweis: Dein persönlicher <code>Calendly</code>-Kalender ist hier eingebunden.</div>
        </div>

      </div>
    </div>
  </header>

  <!-- FEATURES -->
  <section id="features" class="max-w-6xl mx-auto px-6 py-12">
    <h2 class="text-2xl font-bold">Funktionen & Vorteile</h2>
    <p class="mt-2 text-gray-600">Alles, was Unternehmen brauchen, um Telefonanfragen automatisch zu Terminbuchungen zu machen.</p>

    <div class="mt-6 grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="p-6 bg-white rounded-lg shadow">
        <h3 class="font-semibold">Automatische Anrufbearbeitung</h3>
        <p class="mt-2 text-sm text-gray-600">Skript-basierte Anruflogik, persönliche Begrüßungen und intelligente Weiterleitungen.</p>
      </div>
      <div class="p-6 bg-white rounded-lg shadow">
        <h3 class="font-semibold">Echtzeit-Kalender</h3>
        <p class="mt-2 text-sm text-gray-600">Volle Synchronisation mit Calendly — Verfügbarkeiten werden live übernommen.</p>
      </div>
      <div class="p-6 bg-white rounded-lg shadow">
        <h3 class="font-semibold">Einfache Integration</h3>
        <p class="mt-2 text-sm text-gray-600">Schnelle Einrichtung via Dashboard, Webhooks und API für Enterprise-Workflows.</p>
      </div>
    </div>
  </section>

  <!-- PRICING -->
  <section id="preise" class="max-w-6xl mx-auto px-6 py-10">
    <h2 class="text-2xl font-bold">Preise</h2>
    <p class="mt-2 text-gray-600">Transparent & skalierbar — keine versteckten Kosten.</p>

    <div class="mt-6 grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="p-6 bg-white rounded-lg shadow flex flex-col">
        <div class="text-sm text-gray-500">Basic</div>
        <div class="mt-4 text-3xl font-extrabold">€49<span class="text-base font-medium">/Monat</span></div>
        <ul class="mt-4 text-sm text-gray-600 flex-1">
          <li>Bis zu 300 Anrufe/Monat</li>
          <li>Calendly-Integration</li>
          <li>E-Mail Support</li>
        </ul>
        <button onclick="Calendly.initPopupWidget({url: 'https://calendly.com/geislermax999'});return false;" class="mt-4 px-4 py-2 bg-indigo-600 text-white rounded">Jetzt testen</button>
      </div>

      <div class="p-6 bg-white rounded-lg shadow border-2 border-indigo-100 flex flex-col">
        <div class="text-sm text-gray-500">Pro</div>
        <div class="mt-4 text-3xl font-extrabold">€99<span class="text-base font-medium">/Monat</span></div>
        <ul class="mt-4 text-sm text-gray-600 flex-1">
          <li>Bis zu 1.500 Anrufe/Monat</li>
          <li>Individualisierte Skripte</li>
          <li>Priorisierter Support</li>
        </ul>
        <button onclick="Calendly.initPopupWidget({url: 'https://calendly.com/geislermax999'});return false;" class="mt-4 px-4 py-2 bg-indigo-600 text-white rounded">Pro buchen</button>
      </div>

      <div class="p-6 bg-white rounded-lg shadow flex flex-col">
        <div class="text-sm text-gray-500">Enterprise</div>
        <div class="mt-4 text-3xl font-extrabold">Auf Anfrage</div>
        <ul class="mt-4 text-sm text-gray-600 flex-1">
          <li>Unbegrenzte Anrufe</li>
          <li>Onboarding & Integration</li>
          <li>Service Level Agreement</li>
        </ul>
        <a href="#contact" class="mt-4 px-4 py-2 border rounded">Kontakt</a>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section id="faq" class="max-w-6xl mx-auto px-6 py-10">
    <h2 class="text-2xl font-bold">Häufige Fragen</h2>
    <div class="mt-6 space-y-3">
      <div class="bg-white p-4 rounded shadow">
        <button class="w-full text-left faq-toggle font-medium">Wie funktioniert die Calendly-Integration?</button>
        <div class="faq-content mt-2 text-sm text-gray-600 hidden">TerminBot verwendet Calendly-Links und Webhooks. Verfügbarkeiten werden in Echtzeit synchronisiert; Buchungen erscheinen sofort in deinem Calendly-Kalender.</div>
      </div>
      <div class="bg-white p-4 rounded shadow">
        <button class="w-full text-left faq-toggle font-medium">Ist das DSGVO-konform?</button>
        <div class="faq-content mt-2 text-sm text-gray-600 hidden">Ja — Datenverarbeitung kann in der EU gehostet werden. Wir empfehlen einen Auftragsverarbeitungs-Vertrag (AVV) für Enterprise-Kunden.</div>
      </div>
      <div class="bg-white p-4 rounded shadow">
        <button class="w-full text-left faq-toggle font-medium">Brauche ich spezielle Hardware?</button>
        <div class="faq-content mt-2 text-sm text-gray-600 hidden">Nein. TerminBot läuft in der Cloud; nur Telefonnummer und Calendly-Konto sind erforderlich.</div>
      </div>
    </div>
  </section>

  <!-- CONTACT / FOOTER -->
  <footer id="contact" class="border-t mt-10 bg-white">
    <div class="max-w-6xl mx-auto px-6 py-10 grid grid-cols-1 md:grid-cols-3 gap-6">
      <div>
        <h3 class="font-bold text-lg">TerminBot</h3>
        <p class="text-sm text-gray-600 mt-2">Ihr Telefonassistent — automatisiert, zuverlässig und skalierbar.</p>
      </div>

      <div>
        <h4 class="font-semibold">Kontakt</h4>
        <p class="text-sm text-gray-600 mt-2">Email: <a href="mailto:geislermax999@gmail.com" class="text-indigo-600 hover:underline">geislermax999@gmail.com</a><br>Telefon: <a href="tel:01635315433" class="text-indigo-600 hover:underline">0163 5315433</a></p>
      </div>

      <div>
        <h4 class="font-semibold">Schnellzugriff</h4>
        <ul class="mt-2 text-sm text-gray-600">
          <li><a href="#preise" class="hover:underline">Preise</a></li>
          <li><a href="#faq" class="hover:underline">FAQ</a></li>
          <li><button onclick="Calendly.initPopupWidget({url: 'https://calendly.com/geislermax999'});return false;" class="mt-2 px-3 py-2 bg-indigo-600 text-white rounded">Demo buchen</button></li>
        </ul>
      </div>
    </div>

    <div class="bg-gray-50 border-t py-4">
      <div class="max-w-6xl mx-auto px-6 text-xs text-gray-500 flex flex-col md:flex-row justify-between">
        <div>© "TerminBot" — Alle Rechte vorbehalten.</div>
        <div class="mt-2 md:mt-0">Impressum | Datenschutz</div>
      </div>
    </div>
  </footer>

  <!-- Small mobile menu script -->
  <script>
    document.getElementById('mobile-menu-btn').addEventListener('click', function(){
      const nav = document.querySelector('nav div.hidden.md\\:flex');
      if(!nav) return;
      nav.classList.toggle('hidden');
    });

    // FAQ accordion
    document.querySelectorAll('.faq-toggle').forEach(btn => {
      btn.addEventListener('click', () => {
        const content = btn.nextElementSibling;
        content.classList.toggle('hidden');
      });
    });

    // Small safeguard: if Calendly isn't loaded, show friendly warning in console
    if(!window.Calendly){
      console.warn('Calendly widget lädt nicht. Stelle sicher, dass die Internetverbindung aktiv ist und die Calendly-Skripte erreichbar sind.');
    }
  </script>

</body>
</html>
