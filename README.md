<!doctype html>
<html lang="de">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Versorgungskompass</title>

<style>
:root{
  --blue:#00549f;--blue2:#0b74c9;--dark:#1f2937;--muted:#667085;
  --bg:#f3f7fb;--line:#d8e3ef;--soft:#f8fbff;
  --green:#0f766e;--red:#b42318;
}
*{box-sizing:border-box}
body{margin:0;font-family:Arial,Helvetica,sans-serif;background:var(--bg);color:var(--dark);line-height:1.45}
header{background:linear-gradient(135deg,var(--blue),var(--blue2));color:#fff;padding:34px 18px;text-align:center}
header h1{margin:0 0 10px;font-size:32px}
header p{margin:0 auto;max-width:780px;font-size:18px}
.intro{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin:22px auto 0;max-width:980px}
.intro div{background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.28);border-radius:16px;padding:14px;text-align:left}
.intro b{display:block;margin-bottom:5px}
.wrap{max-width:980px;margin:24px auto;padding:0 14px 40px}
.card{background:#fff;border-radius:20px;box-shadow:0 12px 34px rgba(16,24,40,.10);padding:24px}
.section{border-top:1px solid var(--line);padding-top:24px;margin-top:24px}
.section:first-child{border-top:0;padding-top:0;margin-top:0}
h2{margin:0 0 6px;color:var(--blue);font-size:24px}
.hint{margin:0 0 18px;color:var(--muted)}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:15px}
.full{grid-column:1/-1}
label{display:block;font-weight:700;margin-bottom:7px;font-size:14px}
input,select,textarea{width:100%;border:1px solid var(--line);border-radius:13px;padding:13px 14px;font-size:16px;background:#fff;color:var(--dark)}
textarea{min-height:105px;resize:vertical}
.checks{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.check{display:flex;gap:9px;align-items:flex-start;background:var(--soft);border:1px solid var(--line);border-radius:13px;padding:11px;font-weight:400}
.check input{width:auto;margin-top:3px}
.actions{display:flex;gap:12px;justify-content:flex-end;flex-wrap:wrap;margin-top:24px}
button{border:0;border-radius:999px;padding:14px 22px;font-size:16px;font-weight:700;cursor:pointer}
.primary{background:var(--blue);color:#fff}
.secondary{background:#e9f0f8;color:var(--dark)}
.success{background:var(--green);color:#fff}
.preview{white-space:pre-wrap;background:#f8fafc;border:1px solid var(--line);border-radius:16px;padding:14px;margin-top:16px;display:none;font-size:14px}
.required{color:var(--red)}
.small{font-size:13px;color:var(--muted);margin-top:10px}
.ok{display:none;background:#ecfdf5;color:#065f46;border-radius:14px;padding:13px;margin-top:14px}
.error{display:none;background:#fef3f2;color:#7a271a;border:1px solid #fecdca;border-radius:14px;padding:13px;margin-top:14px}

@media(max-width:740px){
  .intro,.grid,.checks{grid-template-columns:1fr}
  .actions button{width:100%}
  header h1{font-size:26px}
}
</style>
</head>

<body>

<header>
  <h1>Versorgungskompass</h1>
  <p>Einfach Daten eingeben, Anfrage abschicken und Termin zur Erprobung erhalten.</p>

  <div class="intro">
    <div><b>1. Anfrage starten</b>Kontaktdaten und Ausgangssituation eintragen.</div>
    <div><b>2. Bedarf beschreiben</b>Mobilität, Ziele und Anforderungen erfassen.</div>
    <div><b>3. Termin erhalten</b>Das zuständige Team kann die Erprobung gezielt vorbereiten.</div>
  </div>
</header>

<main class="wrap">
<section class="card">

<div class="section">
  <h2>Kontaktdaten</h2>
  <p class="hint">Damit wir die Anfrage zuordnen und einen passenden Erprobungstermin abstimmen können.</p>

  <div class="grid">
    <div>
      <label>Name <span class="required">*</span></label>
      <input id="name" placeholder="Max Mustermann">
    </div>

    <div>
      <label>E-Mail <span class="required">*</span></label>
      <input id="email" type="email" placeholder="max@example.de">
    </div>

    <div>
      <label>Telefon</label>
      <input id="phone" placeholder="Telefonnummer">
    </div>

    <div>
      <label>PLZ / Ort</label>
      <input id="city" placeholder="z. B. 28870 Ottersberg">
    </div>

    <div>
      <label>Sanitätshaus</label>
      <input id="sanitaetshaus" placeholder="Name des Sanitätshauses">
    </div>

    <div>
      <label>Ich frage an als</label>
      <select id="role">
        <option>Privatperson / Angehörige*r</option>
        <option>Sanitätshaus</option>
        <option>Therapie / Pflege / Klinik</option>
        <option>Sonstiges</option>
      </select>
    </div>
  </div>
</div>

<div class="section">
  <h2>Ausgangssituation</h2>
  <p class="hint">Bitte beschreiben Sie die aktuelle Versorgungssituation möglichst konkret.</p>

  <div class="grid">
    <div>
      <label>Wer benötigt die Versorgung?</label>
      <select id="person">
        <option>Ich selbst</option>
        <option>Angehörige/r</option>
        <option>Kundin/Kunde</option>
        <option>Patientin/Patient</option>
      </select>
    </div>

    <div>
      <label>Aktuelle Mobilität</label>
      <select id="mobility">
        <option>Bitte auswählen</option>
        <option>Gehen eingeschränkt möglich</option>
        <option>Rollstuhl vorhanden</option>
        <option>Elektrorollstuhl vorhanden</option>
        <option>Nicht gehfähig</option>
        <option>Noch unklar</option>
      </select>
    </div>

    <div>
      <label>Körpergröße</label>
      <input id="height" placeholder="z. B. 178 cm">
    </div>

    <div>
      <label>Körpergewicht</label>
      <input id="weight" placeholder="z. B. 100 kg">
    </div>

    <div class="full">
      <label>Diagnosen / Einschränkungen</label>
      <textarea id="diagnosis" placeholder="z. B. MS, Schlaganfall, Adipositas, Amputation, Schmerzen, eingeschränkte Armfunktion …"></textarea>
    </div>

    <div class="full">
      <label>Was funktioniert aktuell nicht gut?</label>
      <textarea id="problem" placeholder="Welche Wege, Transfers, Tätigkeiten oder Alltagssituationen sind schwierig oder nicht möglich?"></textarea>
    </div>
  </div>
</div>

<div class="section">
  <h2>Funktionelle Einschränkungen</h2>
  <p class="hint">Welche Einschränkungen beeinflussen die Mobilität und Versorgung?</p>

  <div class="checks">
    <label class="check"><input type="checkbox" name="einschraenkung" value="Eingeschränkte Gehfähigkeit">Eingeschränkte Gehfähigkeit</label>
    <label class="check"><input type="checkbox" name="einschraenkung" value="Nicht gehfähig">Nicht gehfähig</label>
    <label class="check"><input type="checkbox" name="einschraenkung" value="Eingeschränkte Arm- / Handfunktion">Eingeschränkte Arm- / Handfunktion</label>
    <label class="check"><input type="checkbox" name="einschraenkung" value="Eingeschränkte Rumpfstabilität">Eingeschränkte Rumpfstabilität</label>
    <label class="check"><input type="checkbox" name="einschraenkung" value="Schmerzen">Schmerzen</label>
    <label class="check"><input type="checkbox" name="einschraenkung" value="Spastik / Tonuserhöhung">Spastik / Tonuserhöhung</label>
    <label class="check"><input type="checkbox" name="einschraenkung" value="Dekubitusrisiko / Sitzprobleme">Dekubitusrisiko / Sitzprobleme</label>
    <label class="check"><input type="checkbox" name="einschraenkung" value="Erschöpfung / geringe Belastbarkeit">Erschöpfung / geringe Belastbarkeit</label>
  </div>
</div>

<div class="section">
  <h2>Aktivitäten & Teilhabe</h2>
  <p class="hint">Welche Alltagssituationen sollen durch die Versorgung verbessert werden?</p>

  <div class="checks">
    <label class="check"><input type="checkbox" name="teilhabe" value="Mobilität in der Wohnung">Mobilität in der Wohnung</label>
    <label class="check"><input type="checkbox" name="teilhabe" value="Mobilität außerhalb der Wohnung">Mobilität außerhalb der Wohnung</label>
    <label class="check"><input type="checkbox" name="teilhabe" value="Erreichen von Tisch, Küche oder Schränken">Erreichen von Tisch, Küche oder Schränken</label>
    <label class="check"><input type="checkbox" name="teilhabe" value="Soziale Teilhabe">Soziale Teilhabe</label>
    <label class="check"><input type="checkbox" name="teilhabe" value="Arztbesuche / Therapien / Termine">Arztbesuche / Therapien / Termine</label>
    <label class="check"><input type="checkbox" name="teilhabe" value="Einkaufen / Besorgungen">Einkaufen / Besorgungen</label>
    <label class="check"><input type="checkbox" name="teilhabe" value="Pflege und Transfers erleichtern">Pflege und Transfers erleichtern</label>
    <label class="check"><input type="checkbox" name="teilhabe" value="Selbstständige Positionierung">Selbstständige Positionierung</label>
  </div>

  <div class="grid" style="margin-top:15px">
    <div class="full">
      <label>Weitere Angaben zu Alltag und Teilhabe</label>
      <textarea id="participationText" placeholder="z. B. Wege innerhalb der Wohnung, Teilnahme am Familienleben, Termine, Einkaufen, soziale Kontakte …"></textarea>
    </div>
  </div>
</div>

<div class="section">
  <h2>Wohn- und Umweltfaktoren</h2>
  <p class="hint">Die Umgebung ist wichtig, damit die Erprobung sinnvoll vorbereitet werden kann.</p>

  <div class="grid">
    <div>
      <label>Wohnsituation</label>
      <select id="living">
        <option>Bitte auswählen</option>
        <option>Eigene Wohnung / Haus</option>
        <option>Pflegeeinrichtung</option>
        <option>Betreutes Wohnen</option>
        <option>Sonstiges</option>
      </select>
    </div>

    <div>
      <label>Umgebung</label>
      <select id="environment">
        <option>Bitte auswählen</option>
        <option>Ebene Umgebung</option>
        <option>Ländliche Umgebung</option>
        <option>Steigungen / anspruchsvolle Topografie</option>
        <option>Enge Wohnumgebung</option>
        <option>Noch unklar</option>
      </select>
    </div>

    <div class="full">
      <label>Besonderheiten der Umgebung</label>
      <textarea id="environmentText" placeholder="z. B. Türbreiten, Aufzug, Rampen, Schwellen, Außenwege, Untergrund, Steigungen, Transportmöglichkeit …"></textarea>
    </div>
  </div>
</div>

<div class="section">
  <h2>Versorgungsziel</h2>
  <p class="hint">Was soll durch die Versorgung konkret verbessert oder ermöglicht werden?</p>

  <div class="checks">
    <label class="check"><input type="checkbox" name="ziel" value="Selbstständige Mobilität in der Wohnung">Selbstständige Mobilität in der Wohnung</label>
    <label class="check"><input type="checkbox" name="ziel" value="Selbstständige Mobilität im Außenbereich">Selbstständige Mobilität im Außenbereich</label>
    <label class="check"><input type="checkbox" name="ziel" value="Positionswechsel / Sitzposition verbessern">Positionswechsel / Sitzposition verbessern</label>
    <label class="check"><input type="checkbox" name="ziel" value="Erreichbarkeit im Alltag verbessern">Erreichbarkeit im Alltag verbessern</label>
    <label class="check"><input type="checkbox" name="ziel" value="Teilhabe am sozialen Leben ermöglichen">Teilhabe am sozialen Leben ermöglichen</label>
    <label class="check"><input type="checkbox" name="ziel" value="Pflege / Transfer erleichtern">Pflege / Transfer erleichtern</label>
  </div>

  <div class="grid" style="margin-top:15px">
    <div class="full">
      <label>Konkretes Versorgungsziel</label>
      <textarea id="goalText" placeholder="z. B. eigenständig an den Esstisch fahren, höhere Schränke erreichen, Termine außerhalb der Wohnung wahrnehmen …"></textarea>
    </div>
  </div>
</div>

<div class="section">
  <h2>Hilfsmittel & Erprobung</h2>
  <p class="hint">Diese Angaben helfen bei der Vorbereitung des passenden Termins.</p>

  <div class="grid">
    <div>
      <label>Gewünschte Produktgruppe</label>
      <select id="product">
        <option>Bitte auswählen</option>
        <option>Elektrorollstuhl</option>
        <option>Aktivrollstuhl</option>
        <option>Schwerlastversorgung</option>
        <option>Rollator / Gehhilfe</option>
        <option>Noch unklar</option>
      </select>
    </div>

    <div>
      <label>Krankenkasse / Kostenträger</label>
      <input id="payer" placeholder="z. B. AOK, TK, Barmer">
    </div>

    <div>
      <label>Ort der Erprobung</label>
      <input id="location" placeholder="z. B. Zuhause, Pflegeeinrichtung, Sanitätshaus">
    </div>

    <div>
      <label>Wunschtermin / Zeitraum</label>
      <input id="timewindow" placeholder="z. B. vormittags, KW 25, flexibel">
    </div>

    <div class="full">
      <label>Besondere Anforderungen an das Hilfsmittel</label>
      <textarea id="requirements" placeholder="z. B. Sitzlift, Sitzkantelung, elektrische Rückenlehne, zentrale Beinstütze, Adipositasversorgung, enge Wohnumgebung, Transport …"></textarea>
    </div>
  </div>
</div>

<div id="error" class="error"></div>
<div id="ok" class="ok"></div>
<div id="preview" class="preview"></div>

<div class="actions">
  <button type="button" class="secondary" onclick="showSummary()">Zusammenfassung anzeigen</button>
  <button type="button" class="primary" onclick="copySummary()">Zusammenfassung kopieren</button>
  <button type="button" class="success" onclick="sendMail()">Anfrage absenden</button>
</div>

<p class="small">Pflichtfelder: Name und E-Mail.</p>

</section>
</main>

<script>
function el(id){return document.getElementById(id)}
function value(id){var x=el(id);return x ? x.value.trim() : ''}

function checkedValues(name){
  var checked=document.querySelectorAll('input[name="'+name+'"]:checked');
  if(checked.length===0){return 'Keine Auswahl'}
  return Array.from(checked).map(function(x){return x.value}).join(', ');
}

function buildSummary(){
return `Versorgungskompass Anfrage

KONTAKTDATEN
Name: ${value('name')}
E-Mail: ${value('email')}
Telefon: ${value('phone')}
PLZ / Ort: ${value('city')}
Sanitätshaus: ${value('sanitaetshaus')}
Anfrage als: ${value('role')}

AUSGANGSSITUATION
Versorgung für: ${value('person')}
Aktuelle Mobilität: ${value('mobility')}
Körpergröße: ${value('height')}
Körpergewicht: ${value('weight')}
Diagnosen / Einschränkungen:
${value('diagnosis')}

Was funktioniert aktuell nicht gut?
${value('problem')}

FUNKTIONELLE EINSCHRÄNKUNGEN
${checkedValues('einschraenkung')}

AKTIVITÄTEN & TEILHABE
${checkedValues('teilhabe')}

Weitere Angaben:
${value('participationText')}

WOHN- UND UMWELTFAKTOREN
Wohnsituation: ${value('living')}
Umgebung: ${value('environment')}

Besonderheiten:
${value('environmentText')}

VERSORGUNGSZIEL
Ausgewählte Ziele:
${checkedValues('ziel')}

Konkretes Versorgungsziel:
${value('goalText')}

HILFSMITTEL & ERPROBUNG
Produktgruppe: ${value('product')}
Krankenkasse / Kostenträger: ${value('payer')}
Ort der Erprobung: ${value('location')}
Wunschtermin / Zeitraum: ${value('timewindow')}

Besondere Anforderungen:
${value('requirements')}
`;
}

function clearMessages(){
  el('error').style.display='none';
  el('ok').style.display='none';
}

function showError(msg){
  var box=el('error');
  box.textContent=msg;
  box.style.display='block';
}

function validateRequired(){
  clearMessages();
  if(!value('name') || !value('email')){
    showError('Bitte mindestens Name und E-Mail ausfüllen.');
    return false;
  }
  return true;
}

function showSummary(){
  clearMessages();
  var p=el('preview');
  p.textContent=buildSummary();
  p.style.display='block';
  p.scrollIntoView({behavior:'smooth',block:'center'});
}

async function copySummary(){
  clearMessages();
  var text=buildSummary();
  showSummary();
  try{
    await navigator.clipboard.writeText(text);
    el('ok').textContent='Zusammenfassung wurde kopiert.';
    el('ok').style.display='block';
  }catch(e){
    showError('Kopieren wurde vom Browser blockiert. Bitte die Zusammenfassung manuell markieren und kopieren.');
  }
}

function sendMail(){
  if(!validateRequired()) return;
  var text=buildSummary();
  showSummary();
  var subject=encodeURIComponent('Versorgungskompass Anfrage');
  var body=encodeURIComponent(text);
  window.location.href='mailto:?subject='+subject+'&body='+body;
}
</script>

</body>
</html>
