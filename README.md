# Web Scraper per Dati sul Traffico Aereo ✈️

Questo script Python è progettato per automatizzare il download e l'elaborazione dei dati sul traffico passeggeri degli aeroporti italiani dal sito https://assaeroporti.com/dati-di-traffico/. 
I dati sono estratti dai file Excel mensili forniti da Assaeroporti.

Il programma esegue i seguenti passaggi:

1- Genera URL:
Crea una lista di URL per i file Excel mensili, coprendo un intervallo di tempo specifico (attualmente da gennaio 2019 a settembre 2025).
*E' possibile variare il periodo di estrazione dei file cambiando le date di inizio e fine*

2- Scarica e Processa: 
Scarica ogni file Excel, gestendo eventuali errori di rete con un meccanismo di retry automatico. Dal file, estrae il foglio "Passeggeri Mese".

3- Pulizia e Trasformazione:
Aggiunge una colonna 'data' basata sull'anno e sul mese del file.
Rinomina le colonne per maggiore chiarezza.
Pulisce i nomi degli aeroporti eliminando caratteri speciali.
Rimuove le righe di riepilogo non necessarie.
Sostituisce i valori mancanti (NaN) con zero.

4- Trasforma i dati da un formato "wide" (ampio) a uno "long" (lungo), rendendoli più adatti per l'analisi e la visualizzazione.

5- Esporta: 
Combina tutti i dati in un unico DataFrame e lo salva in un file CSV chiamato passeggeri_aeroporti_long.csv.

