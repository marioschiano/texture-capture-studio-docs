# Changelog

## 0.3.128

- Aggiunge **Mirror & Blend** come alternativa a Edge Blend per le fasce seamless orizzontali.
- Usa il metodo scelto sia nell'anteprima prima/dopo sia nella trim definitiva.
- Gestisce la componente orizzontale delle normal map quando il bordo viene specchiato.

## 0.3.127

- Aggiunge fasce orizzontali a larghezza completa nell'intervallo UV U 0–1.
- Permette di scegliere le texture da includere e la larghezza della trim.
- Aggiunge la sfumatura seamless orizzontale e un'anteprima prima/dopo con tre ripetizioni.
- Mantiene le texture originali e allinea le eventuali mappe PBR allo stesso layout.

## 0.3.20

- Ricrea il layout Atlas dalle singole isole UV connesse.
- Aggiunge la rotazione opzionale di 90° nel packing automatico pixel-perfect.
- Conserva densità dei pixel e ingombro esatto senza scaling o deformazioni.
- Crea una collection Atlas dedicata con copie indipendenti di mesh e materiali.
- Riunisce le copie in un solo materiale e una sola texture Atlas condivisa.
- Può eseguire il bake della Base Color dopo il packing.

## Stato della documentazione

Questa è la prima bozza bilingue. Verranno aggiunti screenshot, esempi animati, risoluzione dei problemi e il riferimento completo di tutte le impostazioni mentre il workflow dell'addon viene consolidato.
