# patrick14-cmd.github.io
Eine Testseite um den den Versorgungskompass zu testen


<!doctype html>
<html lang="de">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Versorgungskompass – Webformular</title>
  <style>
    :root{--blue:#00549f;--blue2:#0b74c9;--dark:#1f2937;--muted:#667085;--bg:#f3f7fb;--line:#d8e3ef;--soft:#f8fbff;--green:#0f766e;--red:#b42318;--yellow:#fffbeb}
    *{box-sizing:border-box} body{margin:0;font-family:Arial,Helvetica,sans-serif;background:var(--bg);color:var(--dark);line-height:1.45}
    header{background:linear-gradient(135deg,var(--blue),var(--blue2));color:#fff;padding:34px 18px;text-align:center}
    header h1{margin:0 0 10px;font-size:30px} header p{margin:0 auto;max-width:760px;font-size:18px}
    .intro{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin:20px auto 0;max-width:980px}.intro div{background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.28);border-radius:16px;padding:13px;text-align:left}.intro b{display:block;margin-bottom:4px}
    .wrap{max-width:980px;margin:24px auto;padding:0 14px 40px}.card{background:#fff;border-radius:20px;box-shadow:0 12px 34px rgba(16,24,40,.10);padding:24px;margin-bottom:18px}
    h2{font-size:22px;margin:0 0 6px;color:var(--blue)}.hint{margin:0 0 18px;color:var(--muted)}.section{border-top:1px solid var(--line);padding-top:22px;margin-top:22px}.section:first-child{border-top:0;padding-top:0;margin-top:0}
    .grid{display:grid;grid-template-columns:1fr 1fr;gap:15px}.full{grid-column:1/-1} label{display:block;font-weight:700;font-size:14px;margin-bottom:7px}
    input,select,textarea{width:100%;border:1px solid var(--line);border-radius:13px;padding:13px 14px;font-size:16px;background:#fff;color:var(--dark)} textarea{min-height:105px;resize:vertical}
    .checks{display:grid;grid-template-columns:1fr 1fr;gap:10px}.check{display:flex;gap:9px;align-items:flex-start;background:var(--soft);border:1px solid var(--line);border-radius:13px;padding:11px;font-weight:400}.check input{width:auto;margin-top:3px}
    .actions{display:flex;gap:12px;justify-content:flex-end;flex-wrap:wrap;margin-top:24px}button{border:0;border-radius:999px;padding:14px 22px;font-size:16px;font-weight:700;cursor:pointer}.primary{background:var(--blue);color:#fff}.secondary{background:#e9f0f8;color:var(--dark)}.success{background:var(--green);color:#fff}
    .preview{white-space:pre-wrap;background:#f8fafc;border:1px solid var(--line);border-radius:16px;padding:14px;margin-top:16px;display:none;font-size:14px}.required{color:var(--red)}.small{font-size:13px;color:var(--muted);margin-top:8px}.ok{display:none;background:#ecfdf5;color:#065f46;border-radius:14px;padding:13px;margin-top:14px}.notice{background:var(--yellow);border:1px solid #fde68a;border-radius:16px;padding:14px;margin-top:18px;color:#7c4a03}.error{display:none;background:#fef3f2;color:#7a271a;border:1px solid #fecdca;border-radius:14px;padding:13px;margin-top:14px}
    @media(max-width:740px){header h1{font-size:25px}.intro,.grid,.checks{grid-template-columns:1fr}.card{padding:18px}.actions{justify-content:stretch}.actions button{width:100%;text-align:center}}
  </style>
</head>
<body>
<header>
  <h1>Versorgungskompass</h1>
  <p>Einfach Daten eingeben, Anfrage abschicken und Termin zur Erprobung erhalten.</p>
  <div class="intro">
    <div><b>1. Anfrage starten</b>Kontaktdaten und Ausgangssituation eintragen.</div>
    <div><b>2. Bedarf beschreiben</b>Mobilität, Ziele und besondere Anforderungen erfassen.</div>
    <div><b>3. Termin erhalten</b>Das zuständige Team kann die Erprobung gezielt vorbereiten.</div>
  </div>
</header>
<main class="wrap">
<section class="card" id="kompass">
  <div class="section">
    <h2>Kontaktdaten</h2><p class="hint">Damit wir die Anfrage zuordnen und einen passenden Erprobungstermin abstimmen können.</p>
    <div class="grid">
      <div><label for="name">Name <span class="required">*</span></label><input id="name" autocomplete="name" placeholder="Max Mustermann"></div>
      <div><label for="email">E-Mail <span class="required">*</span></label><input id="email" type="email" autocomplete="email" placeholder="max@example.de"></div>
      <div><label for="phone">Telefon</label><input id="phone" type="tel" autocomplete="tel" placeholder="Telefonnummer"></div>
      <div><label for="city">PLZ / Ort</label><input id="city" placeholder="z. B. 28870 Ottersberg"></div>
      <div class="full"><label for="role">Ich frage an als</label><select id="role"><option>Privatperson / Angehörige*r</option><option>Sanitätshaus</option><option>Therapie / Pflege / Klinik</option><option>Sonstiges</option></select></div>
    </div>
  </div>
  <div class="section">
    <h2>Ausgangssituation</h2><p class="hint">Beschreiben Sie kurz, welche Mobilität aktuell möglich ist und wobei Unterstützung benötigt wird.</p>
    <div class="grid">
      <div><label for="person">Wer benötigt die Versorgung?</label><select id="person"><option>Ich selbst</option><option>Angehörige/r</option><option>Kundin/Kunde</option><option>Patientin/Patient</option></select></div>
      <div><label for="mobility">Aktuelle Mobilität</label><select id="mobility"><option>Bitte auswählen</option><option>Gehen eingeschränkt möglich</option><option>Rollstuhl vorhanden</option><option>Elektrorollstuhl vorhanden</option><option>Nicht gehfähig</option><option>Noch unklar</option></select></div>
      <div><label for="height">Körpergröße</label><input id="height" placeholder="z. B. 178 cm"></div>
      <div><label for="weight">Körpergewicht</label><input id="weight" placeholder="z. B. 100 kg"></div>
      <div class="full"><label for="diagnosis">Diagnosen / Einschränkungen</label><textarea id="diagnosis" placeholder="z. B. MS, Schlaganfall, Adipositas, Amputation, Schmerzen, eingeschränkte Armfunktion …"></textarea></div>
      <div class="full"><label for="situation">Kurze Beschreibung der Situation</label><textarea id="situation" placeholder="Was funktioniert aktuell nicht gut? Welche Wege, Tätigkeiten oder Alltagssituationen sind schwierig?"></textarea></div>
    </div>
  </div>
  <div class="section">
    <h2>Versorgungsziel</h2><p class="hint">Was soll durch die Versorgung konkret verbessert oder ermöglicht werden?</p>
    <div class="checks">
      <label class="check"><input type="checkbox" name="ziel" value="Selbstständige Mobilität in der Wohnung">Selbstständige Mobilität in der Wohnung</label>
      <label class="check"><input type="checkbox" name="ziel" value="Selbstständige Mobilität im Außenbereich">Selbstständige Mobilität im Außenbereich</label>
      <label class="check"><input type="checkbox" name="ziel" value="Positionswechsel / Sitzposition verbessern">Positionswechsel / Sitzposition verbessern</label>
      <label class="check"><input type="checkbox" name="ziel" value="Erreichbarkeit im Alltag verbessern">Erreichbarkeit im Alltag verbessern</label>
      <label class="check"><input type="checkbox" name="ziel" value="Teilhabe am sozialen Leben ermöglichen">Teilhabe am sozialen Leben ermöglichen</label>
      <label class="check"><input type="checkbox" name="ziel" value="Pflege / Transfer erleichtern">Pflege / Transfer erleichtern</label>
    </div>
    <div class="grid" style="margin-top:15px"><div class="full"><label for="goalText">Weitere Ziele / wichtige Hinweise</label><textarea id="goalText" placeholder="z. B. eigenständig an den Esstisch fahren, höhere Schränke erreichen, Termine außerhalb der Wohnung wahrnehmen …"></textarea></div></div>
  </div>
  <div class="section">
    <h2>Hilfsmittel & Erprobung</h2><p class="hint">Diese Angaben helfen bei der Vorbereitung des passenden Termins.</p>
    <div class="grid">
      <div><label for="product">Gewünschte Produktgruppe</label><select id="product"><option>Bitte auswählen</option><option>Elektrorollstuhl</option><option>Aktivrollstuhl</option><option>Schwerlastversorgung</option><option>Rollator / Gehhilfe</option><option>Noch unklar</option></select></div>
      <div><label for="payer">Krankenkasse / Kostenträger</label><input id="payer" placeholder="z. B. AOK, TK, Barmer"></div>
      <div><label for="location">Ort der Erprobung</label><input id="location" placeholder="z. B. Zuhause, Pflegeeinrichtung, Sanitätshaus"></div>
      <div><label for="timewindow">Wunschtermin / Zeitraum</label><input id="timewindow" placeholder="z. B. vormittags, KW 25, flexibel"></div>
      <div class="full"><label for="requirements">Besondere Anforderungen</label><textarea id="requirements" placeholder="z. B. Sitzlift, Sitzkantelung, elektrische Rückenlehne, zentrale Beinstütze, Adipositas, enge Wohnumgebung, Transport, Pflegeeinrichtung …"></textarea></div>
    </div>
  </div>
  <div class="notice"><b>Hinweis:</b> In diesem Mockup öffnet „Anfrage absenden“ das E-Mail-Programm mit allen Daten. Auf der echten Homepage sollte der Versand direkt über den Webserver bzw. das vorhandene Formularsystem erfolgen.</div>
  <div id="error" class="error"></div><div id="ok" class="ok"></div><div id="preview" class="preview"></div>
  <div class="actions">
    <button type="button" class="secondary" onclick="showSummary()">Zusammenfassung anzeigen</button>
    <button type="button" class="primary" onclick="copySummary()">Zusammenfassung kopieren</button>
    <button type="button" class="success" onclick="sendMail()">Anfrage absenden</button>
  </div>
  <p class="small">Pflichtfelder: Name und E-Mail. Der echte Versand benötigt später eine Server- oder Formularlösung.</p>
</section>
</main>
<script>
function el(id){return document.getElementById(id)}
function value(id){var x=el(id);return x ? x.value.trim() : ''}
function selectedGoals(){return Array.from(document.querySelectorAll('input[name="ziel"]:checked')).map(function(x){return x.value}).join(', ') || 'Keine Auswahl'}
function buildSummary(){
  return 'Versorgungskompass Anfrage\n\n' +
  'Kontaktdaten\n' +
  'Name: ' + value('name') + '\n' +
  'E-Mail: ' + value('email') + '\n' +
  'Telefon: ' + value('phone') + '\n' +
  'PLZ / Ort: ' + value('city') + '\n' +
  'Rolle: ' + value('role') + '\n\n' +
  'Ausgangssituation\n' +
  'Versorgung für: ' + value('person') + '\n' +
  'Aktuelle Mobilität: ' + value('mobility') + '\n' +
  'Körpergröße: ' + value('height') + '\n' +
  'Körpergewicht: ' + value('weight') + '\n' +
  'Diagnosen / Einschränkungen: ' + value('diagnosis') + '\n' +
  'Beschreibung: ' + value('situation') + '\n\n' +
  'Versorgungsziel\n' +
  'Ausgewählte Ziele: ' + selectedGoals() + '\n' +
  'Weitere Ziele: ' + value('goalText') + '\n\n' +
  'Hilfsmittel & Erprobung\n' +
  'Produktgruppe: ' + value('product') + '\n' +
  'Kostenträger: ' + value('payer') + '\n' +
  'Ort der Erprobung: ' + value('location') + '\n' +
  'Wunschtermin / Zeitraum: ' + value('timewindow') + '\n' +
  'Besondere Anforderungen: ' + value('requirements');
}
function clearMessages(){el('error').style.display='none';el('ok').style.display='none'}
function showError(msg){var box=el('error');box.textContent=msg;box.style.display='block';box.scrollIntoView({behavior:'smooth',block:'center'})}
function validateRequired(){clearMessages(); if(!value('name') || !value('email')){showError('Bitte mindestens Name und E-Mail ausfüllen.'); return false;} return true;}
function showSummary(){clearMessages(); var p=el('preview'); p.textContent=buildSummary(); p.style.display='block'; p.scrollIntoView({behavior:'smooth',block:'center'});}
async function copySummary(){clearMessages(); var text=buildSummary(); showSummary(); try{await navigator.clipboard.writeText(text); el('ok').textContent='Zusammenfassung wurde kopiert.'; el('ok').style.display='block';}catch(e){showError('Kopieren wurde vom Browser blockiert. Die Zusammenfassung kann markiert und manuell kopiert werden.');}}
function sendMail(){
  if(!validateRequired()) return;
  var text=buildSummary(); showSummary();
  el('ok').textContent='Das E-Mail-Programm wird geöffnet. Falls nichts passiert, ist auf diesem Gerät vermutlich keine Mail-App für mailto-Links eingerichtet oder der Browser blockiert den Aufruf.';
  el('ok').style.display='block';
  var subject=encodeURIComponent('Versorgungskompass Anfrage');
  var body=encodeURIComponent(text);
  window.location.href='mailto:?subject='+subject+'&body='+body;
}
</script>
</body>
</html>
