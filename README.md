<p align="center">
    <img src="https://github.com/Robert0Falconi/docker-jitsi-meet/blob/main/config/custom/web/images/jitsi-logo.png" alt="Jitsi" width="100">
</p>
<h1 align="center">JITSI</h1>
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
git clone https://github.com/Robert0Falconi/docker-jitsi-meet.git
cd docker-jitsi-meet
```

### Installazione di Docker

- Visita: [Docker Desktop](https://www.docker.com/products/docker-desktop)
- Scarica e installa Docker Desktop per il tuo sistema operativo
- Verifica l'installazione aprendo il terminale e digitando:

```bash
docker --version
```

### Variabili d'ambiente

Configura le seguenti variabili nel file `.env`:

- `HTTPS_PORT` = 8443 (Cambia se necessario)
- `DOCKER_HOST_ADDRESS` = 10.10.0.149 (Cambia con l'IP della tua rete)
- `PUBLIC_URL` = https://10.10.0.149:8443 (Cambia con l'IP della tua rete)
- `CONFIG`=/Users/Roberto/Desktop/docker-jitsi-meet/config (Percorso della cartella di configurazione)

### Build del progetto con Docker

- Apri Docker Desktop
- Assicurati di essere nella directory del progetto clonato
- Per costruire le immagini e avviare i container:

```bash
docker compose up -d --build
```

Qualora non funzionasse, digitare:

```bash
nano ~/.docker/config.json
```

A questo punto cambiare "desktop" con "" nel nano e riprovare con il `--build`.

- Se le immagini sono già presenti e vuoi solo avviare i container:

```bash
docker compose up
```

- Per fermare i container:

```bash
docker compose down
```

### Avvio del server Jitsi

- Apri il browser e naviga su: `PUBLIC_URL` (configurato da file .env)
- Da qui potrai accedere e utilizzare la piattaforma di videoconferenza

---

### Certificati SSL

Per l'utilizzo in produzione, è fortemente consigliato configurare certificati SSL validi per garantire connessioni sicure. In mancanza di tali certificati verrà mostrato un avviso su browser di connessione non sicura.

---

## Crediti

**Editor:**  
- [Roberto Falconi](https://github.com/Robert0Falconi)

**Basato su:**  
- [Jitsi Meet](https://jitsi.org/) - © Jitsi Team

---

© 2025 – Tutti i diritti riservati.
