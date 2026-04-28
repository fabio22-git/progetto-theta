# 🛡️ Progetto Theta: Zero Trust Network Architecture

**Team:** Mr. Robot Crew | **Contesto:** Build Week 1 @ EPICODE Institute of Technology

Questo progetto documenta la ristrutturazione logica, fisica ed economica dell'infrastruttura IT di un'azienda fittizia ("Compagnia Theta"). L'obiettivo è stato transizionare da una rete "piatta" e vulnerabile a un'architettura resiliente basata sul modello **Zero Trust**, implementando rigorose logiche di segmentazione e difesa in profondità (Defense-in-Depth).

---

### 🎯 Obiettivi e Scenario Aziendale
- **Infrastruttura:** 6 piani operativi, 120 postazioni di lavoro, 1 Web Server aziendale.
- **Sfida:** Mettere in sicurezza il perimetro e isolare le minacce interne (es. Ransomware) limitando i movimenti laterali.
- **Deliverables:** Progettazione topologia di rete, hardening dei dispositivi, collaudi di sicurezza in Python e budgeting (CAPEX/OPEX).

---

### 🛠️ Tecnologie e Strumenti Utilizzati

![Cisco Packet Tracer](https://img.shields.io/badge/Cisco_Packet_Tracer-049BDB?style=for-the-badge&logo=cisco&logoColor=white)
![Firewall ASA](https://img.shields.io/badge/Cisco_ASA_Firewall-E02424?style=for-the-badge&logo=fortinet&logoColor=white)
![Python](https://img.shields.io/badge/Python_Security_Scripts-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Snort IDS](https://img.shields.io/badge/Snort_IDS/IPS-000000?style=for-the-badge&logo=snort&logoColor=white)

---

### ⚙️ Dettagli dell'Architettura (Fasi Operative)

#### 1. Network Engineering & Segmentazione (Layer 2/3)
Progettazione da zero della topologia di rete:
- Creazione e isolamento di **6 VLAN dedicate** (una per piano operativo) per compartimentare il traffico.
- Configurazione di routing Inter-VLAN centralizzato per una gestione ottimizzata dei pacchetti.
- Implementazione di **Port Security** sugli switch di accesso per mitigare attacchi fisici (MAC Spoofing/Flooding).

#### 2. Sicurezza Perimetrale e DMZ
Applicazione del principio del *Least Privilege* tramite **Cisco ASA Firewall**:
- Definizione di rigide zone di fiducia: **INSIDE** (livello 100), **OUTSIDE** (livello 0) e **DMZ** (livello 50).
- Configurazione di policy NAT/PAT e **Access Control List (ACL)** iper-granulari per l'esposizione controllata del Web Server aziendale.

#### 3. Vulnerability Validation (Python)
- Sviluppo di tool di auditing HTTP e port scanning via raw socket in **Python**.
- Collaudo empirico delle regole del firewall, rivelando l'efficacia del blocco al Layer 4, ma esponendo vulnerabilità architetturali al Layer 7 (es. metodo HTTP DELETE non inibito), prontamente documentate nel report.

#### 4. Integrazione IDS/IPS
- Progettazione logica per l'inserimento di sonde **Snort (Intrusion Prevention System)** nei punti nevralgici della rete, per l'ispezione profonda dei pacchetti e la mitigazione degli attacchi applicativi.

---

### 📊 IT Budgeting e Documentazione

Oltre all'implementazione tecnica, il progetto ha previsto una forte componente manageriale:
- Redazione di un **Executive Summary** per stakeholder non tecnici.
- Stesura di un piano finanziario dettagliato (**CAPEX/OPEX**) per l'approvvigionamento hardware (switch, firewall, cavi) e il mantenimento operativo.

---

### 📂 Risorse del Progetto

In questa repository sono disponibili i file sorgenti e la documentazione completa:

- 📄 **[Report Tecnico Finale (PDF)](https://github.com/fabio22-git/progetto-theta/blob/main/Report%20Tecnico%20Theta.%20Architettura%2C%20Sicurezza%20e%20Investimenti.pdf)**: Analisi dettagliata dell'architettura, dei collaudi e del budget.
- 🌐 **[Topologia Cisco Packet Tracer (.pkt)](./progetto-theta.pkt)**: File sorgente del progetto per la simulazione dell'intera infrastruttura di rete.

*(Nota: Per visualizzare correttamente il file .pkt è necessario Cisco Packet Tracer v8.2 o superiore)*

> 📥 **Scarica e consulta la documentazione ufficiale:** [Report Tecnico Theta - Architettura e Sicurezza (PDF)](INSERIRE_QUI_IL_LINK_AL_PDF_DOPO_AVERLO_CARICATO)
