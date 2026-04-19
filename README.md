# NucleoDigest — Documentação Técnica v1.0

> [cite_start]**Inteligência Biológica Preditiva e Otimização Econômica para Biodigestores Industriais.** > Uma solução desenvolvida para o **Hackathon Low Hack (Siemens & Truechange)** focada em transformar resíduos em receita através da economia circular, sem incineração[cite: 1, 3, 4].

---

## 👥 Equipe Técnica
| Membro | Responsabilidade Principal |
| :--- | :--- |
| **Participante 1** | Especialista Mendix e Lógica de Microflows |
| **Participante 2** | Engenheiro de Biogás e Regras Biológicas |
| **Participante 3** | Arquiteto de Soluções e Integrações REST |
| **Participante 4** | UX/UI Designer e Prototipação Atlas UI |
| **Participante 5** | Analista de Negócios e Motor Econômico |

---

## 📄 Visão Geral
[cite_start]O **NucleoDigest** resolve dois gargalos críticos da indústria de biogás: a fragilidade do microbioma e a subotimização financeira[cite: 1, 9]. [cite_start]Enquanto sistemas tradicionais monitoram apenas o hardware, o NucleoDigest foca na **biologia**[cite: 1, 21].

### O Problema
* [cite_start]**Colapsos Invisíveis**: Falhas biológicas por acidificação ou inibição por amônia costumam ser detectadas tarde demais[cite: 1, 9].
* [cite_start]**Prejuízos Sistêmicos**: Um único colapso pode representar perdas superiores a **R$ 500 mil** em receita não gerada[cite: 1, 11].
* [cite_start]**Indecisão de Mercado**: Operadores raramente possuem dados em tempo real para decidir entre vender energia ou emitir créditos de carbono[cite: 1, 9].

### A Solução
1.  [cite_start]**Inteligência Biológica Preditiva**: Monitoramento em tempo real de pH, Metano (CH4), Ácidos Graxos Voláteis (AGV) e Amônia (NH3) para prever colapsos[cite: 1, 15, 16].
2.  [cite_start]**Otimização Econômica Dinâmica**: Motor de cálculo que analisa o lucro por MWh cruzando preços spot de energia, CBIOs, custos logísticos e *tipping fees*[cite: 1, 18].

---

## 🏗️ Arquitetura da Solução
[cite_start]A aplicação foi estruturada em quatro camadas verticais integradas[cite: 1, 29, 30]:

| Camada | Descrição | Tecnologia |
| :--- | :--- | :--- |
| **1. Fontes Externas** | [cite_start]Sensores IoT e APIs de Mercado (CCEE/B3)[cite: 1, 31]. | REST / JSON Mock |
| **2. Middleware REST** | [cite_start]Normalização de dados para o formato Mendix[cite: 1, 31]. | Mendix REST Service |
| **3. Mendix Core** | [cite_start]Processamento de lógica, banco de dados e agendamentos[cite: 1, 31]. | Mendix Studio Pro |
| **4. Outputs** | [cite_start]Dashboard de decisão e execução de ordens[cite: 1, 31]. | Atlas UI / Data Binding |

---

## 📡 Documentação de APIs (REST)

*(Espaço reservado para o Fluxograma SVG de Integração)*

### Inbound: Monitoramento de Sensores
[cite_start]**Endpoint:** `POST /api/leitura` [cite: 1, 81]  
[cite_start]**Objetivo:** Receber dados físico-químicos dos sensores IoT[cite: 1, 79].

**Payload Exemplo (JSON):**
```json
{
  "biodigestor_id": 1,
  "ph": 6.3,
  "ch4_pct": 58.2,
  "agv_mgL": 4200,
  "nh3_mgL": 1800,
  "timestamp": "2026-04-19T14:30:00Z"
}
