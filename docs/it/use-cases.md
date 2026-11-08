# Casi d'uso

Alcuni esempi pratici per scegliere il percorso più adatto. Parti sempre da una fotografia che puoi utilizzare e condividere per il tuo progetto.

## Estrarre una superficie da una foto

Per mattoni, intonaco, pavimenti o insegne, carica la foto e usa **Capture → Texture** per delimitare la superficie con quattro punti. Inizia con **Perspective Correct**, controlla gli angoli e scegli le proporzioni con **Target UV Ratio**. Non serve risolvere la prospettiva per una semplice cattura 2D.

Se conosci le proporzioni reali, usa **Custom Ratio**: una sola fotografia non sempre permette di ricavarle con precisione. Vedi la [Guida rapida](quick-start.md).

## Ricostruire una facciata semplice

Per allineare box o piani a un edificio, usa **Match Perspective**, controlla le guide X, Y e, se necessarie, Z, quindi premi **Solve Camera**. Crea la geometria con **Create Box** o con i piani prospettici e verifica snapping e allineamento sulla foto. Per i controlli consulta il [Workflow completo](workflow.md).

## Pulire e ripetere un materiale

Per una texture con illuminazione non uniforme, prova **Clean Lighting** sulla texture estratta, confronta l'anteprima e crea una copia. Se servono correzioni locali puoi usare **Advanced Retouch**. Poi verifica **Make Seamless** o crea una **Trim Sheet**, controllando sempre le giunzioni nelle ripetizioni.

Ombre nette, riflessi e zone bruciate potrebbero richiedere ulteriori ritocchi; le operazioni non recuperano necessariamente informazioni mancanti.

## Preparare più superfici per l'export

Per organizzare più mesh texturizzate, valuta l'**Atlas automatico**, verificando UV, materiali e dimensione massima. Poi controlla selezione, scala e formato prima di esportare con il preset per mesh statiche. Vedi [Trim Sheet e Atlas](trim-atlas.md) e [Consigli export](export-tips.md).
