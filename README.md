<p align="center">
  <a href="https://github.com/Robert0Falconi/jitsi">
    <img src="https://jitsi.org/wp-content/uploads/2018/08/jitsi-logo-blue-grey-text.png" alt="Jitsi" width="200">
  </a>
</p>
<p align="center">
    <em>Piattaforma self-hosted per videoconferenze open source</em>
</p>

---

## Descrizione generale

Questo progetto fornisce una soluzione completa per l'implementazione di un server Jitsi Meet self-hosted, una piattaforma di videoconferenza open source che garantisce privacy e controllo totale sui propri dati.

Jitsi Meet permette di creare riunioni video sicure e di alta qualità senza dipendere da servizi di terze parti, ideale per aziende, istituzioni educative e organizzazioni che necessitano di una soluzione di comunicazione affidabile.

---

## Requisiti minimi di sistema

- **Disco:** almeno **20 GB**
- **CPU:** **4–8 core dedicati**
- **RAM:** **8 GB** consigliati (minimo 4 GB per riunioni piccole)
- **Rete:** uplink **1 Gbit/s** (10 Gbit/s consigliati per installazioni professionali)

### Velocità minima (upload/download)

- **180p** → 200 kbit/s  
- **360p** → 500 kbit/s  
- **720p (HD)** → 2.5 Mbit/s  
- **4K** → 10 Mbit/s  

> **Nota:** la banda richiesta scala in funzione del numero di utenti.

---

## Manuale Installazione

### Collegamento al repository Git

Se Git non è già installato sul tuo sistema, scaricalo e installalo seguendo le istruzioni ufficiali: [Git Downloads](https://git-scm.com/downloads).

Apri il terminale e digita il comando:

```bash
git clone https://github.com/Robert0Falconi/jitsi.git
cd jitsi
```

### Installazione di Docker

- Visita: [Docker Desktop](https://www.docker.com/products/docker-desktop)
- Scarica e installa Docker Desktop per il tuo sistema operativo
- Verifica l'installazione aprendo il terminale e digitando:

```bash
docker --version
```

### Build del progetto con Docker

- Apri Docker Desktop
- Assicurati di essere nella directory del progetto clonato
- Per costruire le immagini e avviare i container:

```bash
docker-compose up --build
```

Qualora non funzionasse, digitare:

```bash
nano ~/.docker/config.json
```

A questo punto cambiare "desktop" con "" nel nano e riprovare con il `--build`.

- Se le immagini sono già presenti e vuoi solo avviare i container:

```bash
docker-compose up
```

- Per fermare i container:

```bash
docker-compose down
```

### Avvio del server Jitsi

- Apri il browser e naviga su: `http://localhost:8000/` (o l'indirizzo configurato)
- Da qui potrai accedere e utilizzare la piattaforma di videoconferenza

---

## Configurazione

### Variabili d'ambiente

Prima del primo avvio, è consigliabile configurare le seguenti variabili nel file `.env`:

- `JITSI_DOMAIN`: il dominio dove sarà raggiungibile Jitsi
- `JITSI_HTTP_PORT`: porta HTTP (default: 8000)
- `JITSI_HTTPS_PORT`: porta HTTPS (default: 8443)
- `TZ`: timezone del server

### Certificati SSL

Per l'utilizzo in produzione, è fortemente consigliato configurare certificati SSL validi per garantire connessioni sicure.

---

## Crediti

**Autore:**  
- [Roberto Falconi](https://github.com/Robert0Falconi)

**Basato su:**  
- [Jitsi Meet](https://jitsi.org/) - © Jitsi Team

---

© 2025 – Tutti i diritti riservati.  
Nessuna parte di questo progetto può essere riprodotta, distribuita o utilizzata per scopi commerciali senza l'autorizzazione scritta dell'autore.