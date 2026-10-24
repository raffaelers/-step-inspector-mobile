# STEP Inspector Mobile 0.3

Novità: trascinamento invertito rispetto alla v0.2; pulsante **Interroga** per leggere coordinate del punto toccato, normale triangolo, ingombro della mesh selezionata e area del triangolo. Questi valori provengono dalla triangolazione, non da superfici analitiche STEP. Non sono misure di collaudo.

## Aggiornamento GitHub Pages
Carica **tutti i file dentro questa cartella** nella root del repository (non lo ZIP), sostituendo i precedenti. Conferma con Commit changes e attendi il deploy. Apri il sito in Safari, poi eventualmente reinstalla l'app dalla schermata Home se la cache resta vecchia.

## Limiti
La modalità offline dipende dalla cache e dal caricamento precedente delle librerie esterne; il caricamento STEP può richiedere rete al primo uso. La funzione Interroga non calcola diametri o raggi esatti: richiedono l'accesso alle superfici B-Rep con ulteriori sviluppi.
