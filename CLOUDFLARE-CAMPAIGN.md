# Campanie EU AI ACT READY™ — 2026-11-01

Două pagini HTML statice, fără dependențe, în `campaign/`. Site-ul vechi din rădăcina repository-ului este păstrat.

## Cloudflare Pages — Git integration

Creați un proiect Pages separat pentru campanie; nu modificați proiectul vechi dacă deservește deja alt site.

- Repository: `aipath512/eu-ai-act-ready`
- Production branch: `main`
- Framework preset: `None`
- Root directory: rădăcina repository-ului (necompletat)
- Build command: `exit 0`
- Build output directory: `campaign`
- Environment variables: niciuna

Workers & Pages → Create application → Pages → Connect to Git → selectați repository-ul. Nu selectați un proiect Worker cu comandă de deploy Wrangler. După prima publicare, push-urile pe `main` declanșează publicarea prin integrarea Git a Cloudflare. URL-ul efectiv este cel returnat de Cloudflare; nu este predefinit aici.

Documentație oficială:
https://developers.cloudflare.com/pages/get-started/git-integration/
https://developers.cloudflare.com/pages/framework-guides/deploy-anything/

## Parcurs

- `/`: hook → poveste → formular CTA. Trei date, selecție limbă, confirmare modele.
- Formular valid → `/thank-you/`, cu date în sessionStorage, niciodată în URL.
- `/thank-you/`: descărcare dosar + prezentare RRVI + descărcare configurație și manual.
- Datele sunt acceptate pentru maximum 30 de minute în aceeași filă. Ștergere explicită disponibilă. SessionStorage nu este criptat; utilizați dispozitive de încredere. Browserele cu restaurarea sesiunii pot păstra fizic stocarea după închidere; codul refuză datele expirate la acces.
- Accesul direct la Thank-You Page fără date nu creează o confirmare falsă; afișează revenirea la formular și păstrează manualul accesibil.

## Ce funcționează

70 fișe structurale HTML, 10 × 7, ZIP fără librării externe, câmpuri/instrucțiuni în 24 de limbi oficiale UE, index, manual RRVI RO și configurație JSON. Funcționează fără API sau chei.

## Limite explicite

Nu este corpusul celor 70 de documente juridice integrale. Titlurile catalogului sunt RO; manualul este RO. Fișele necesită completare, evaluarea aplicabilității și verificare. Editările contenteditable nu sunt salvate automat; folosiți editor sau Print to PDF. Nu există email, colectare de leaduri pe server, AI generativ, verificare automată RRVI, cron, alerte, certificare ori activare comercială. Butoanele RRVI descarcă fișiere, nu pretind activarea unui serviciu.

Pentru funcționalitatea integrală sunt necesare corpusul validat, adaptarea la sistemele firmei, traducerea integrală și un backend separat pentru generare, consimțământ, stocare, email și monitorizare. Nu introduceți secrete în frontend sau repository.

## Publicare

Adăugarea fișierelor în GitHub nu confirmă existența integrării Cloudflare. Verificați primul deployment și URL-ul din dashboard. Nicio integrare Cloudflare nu este creată de aceste fișiere.
