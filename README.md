<div align="center">
  <img src="https://ui-avatars.com/api/?name=ND&background=1D9E75&color=fff&size=200&rounded=true&font-size=0.4" alt="NucleoDigest Logo" width="150" height="150">
  <br><br>
  <i>Inteligência biológica preditiva e otimização econômica — garantindo a saúde e a máxima rentabilidade de biodigestores industriais.</i>
  <br><br>
</div>

---

## 👥 Membros da Equipe

<table align="center">
  <tr>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P1&background=random&color=fff&rounded=true" width="100" alt="Participante 1"><br>
      <b>Participante 1</b><br>
      <i>Especialista Mendix</i>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P2&background=random&color=fff&rounded=true" width="100" alt="Participante 2"><br>
      <b>Participante 2</b><br>
      <i>Eng. de Biogás</i>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P3&background=random&color=fff&rounded=true" width="100" alt="Participante 3"><br>
      <b>Participante 3</b><br>
      <i>Arquiteto de Soluções</i>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P4&background=random&color=fff&rounded=true" width="100" alt="Participante 4"><br>
      <b>Participante 4</b><br>
      <i>UX/UI Designer</i>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P5&background=random&color=fff&rounded=true" width="100" alt="Participante 5"><br>
      <b>Participante 5</b><br>
      <i>Regras de Negócio</i>
    </td>
  </tr>
</table>

---

## 📄 Descrição

**NucleoDigest** é uma infraestrutura digital desenvolvida para o **Hackathon Siemens & Truechange**, focada em resolver a fragilidade sistêmica e a ineficiência econômica de biodigestores industriais. 

Nosso propósito é conectar o **monitoramento biológico do microbioma** com as **decisões de mercado em tempo real** (energia spot, créditos CBIO e tipping fees), traduzindo dados brutos de sensores em operações mais seguras, eficientes e lucrativas.

O NucleoDigest foca em:
* **Prever colapsos anaeróbicos** monitorando AGV e pH antes que ocorram.
* **Otimizar a geração de receita**, direcionando o biogás para a fonte mais lucrativa do dia.
* **Criar um "Guard Biológico"**, garantindo que a busca por lucro nunca comprometa a saúde do reator.
* **Viabilizar a economia circular** de forma economicamente autossustentável.

Inspirada na complexidade biológica dos digestores, o NucleoDigest traduz dados físico-químicos e financeiros em **decisões de operação simples e rentáveis**, tornando visível e acionável o que antes operava no escuro.

---

## 💎 Pilares da Solução

**Inteligência Biológica Preditiva**
Monitoramento de tendências de ácidos graxos voláteis (AGV) e pH, prevendo colapsos de 2 a 5 dias antes de impactarem a produção.

**Fail-safe Operacional (Guard)**
O motor econômico é subordinado à biologia. O sistema bloqueia automaticamente qualquer recomendação de venda ou aumento de carga se o sistema estiver em risco crítico.

**Otimização Econômica Dinâmica**
Cálculo automatizado cruzando a produção estimada com APIs da CCEE e da B3 (RenovaBio), indicando ao operador exatamente onde o metro cúbico do biogás vale mais.

**Baixa Complexidade, Alto Impacto (Low-Code)**
Totalmente desenvolvido na plataforma Mendix, utilizando integrações REST e fluxos visuais, sem necessidade de infraestrutura pesada ou complexidade de machine learning para a versão MVP.

---

## ⚠️ O Problema

Biodigestores industriais são sistemas biologicamente frágeis operados como se fossem máquinas. A fragilidade sistêmica no monitoramento focado apenas no equipamento — ignorando o microbioma — compromete a viabilidade das plantas.

Um colapso biológico leva de 15 a 20 dias para ser corrigido, período em que o biodigestor não gera biogás. **O impacto? Uma perda estimada de R$ 52.000 a R$ 90.000 por evento de colapso.**

O desafio do Hackathon:
> *"Geração de energia via economia circular — resíduos sem incineração. Como integrar dados e criar tecnologia de impacto?"*

---

## 🎯 O que o NucleoDigest resolve

* 🟢 **Evita colapsos e prejuízos:** Detecta anomalias precocemente (Ideia 1).
* 📈 **Maximiza o lucro diário:** Calcula se vale mais a pena vender energia ou emitir carbono (Ideia 2).
* ⚙️ **Simplifica a operação:** Entrega uma recomendação pronta (Aprovar/Rejeitar) para o operador na planta.

---

## 📡 Documentação das APIs e Fluxo REST

O núcleo do sistema opera através de quatro blocos de integração REST (dois inbound e dois outbound), orquestrados diretamente pelo Mendix. Abaixo apresentamos o fluxograma da arquitetura de integração:

<div align="center">
  <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 800 450" width="100%">
    <defs>
      <style>
        .box { fill: #1A1D27; stroke: #333; stroke-width: 2; rx: 8; }
        .text-title { fill: #F1EFE8; font-family: Inter, sans-serif; font-weight: bold; font-size: 14px; }
        .text-desc { fill: #888780; font-family: Inter, sans-serif; font-size: 12px; }
        .line { stroke: #7F77DD; stroke-width: 2; fill: none; }
        .line-dashed { stroke: #EF9F27; stroke-width: 2; stroke-dasharray: 5,5; fill: none; }
        .arrow { fill: #7F77DD; }
        .arrow-dashed { fill: #EF9F27; }
        .box-highlight { fill: #1D9E75; stroke: #1D9E75; rx: 8; }
        .text-highlight { fill: #1A1D27; font-family: Inter, sans-serif; font-weight: bold; font-size: 14px; }
      </style>
      <marker id="arrowhead" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
        <polygon points="0 0, 10 3.5, 0 7" class="arrow" />
      </marker>
      <marker id="arrowhead-dashed" markerWidth="10" markerHeight="7" refX="9" refY="3.5" orient="auto">
        <polygon points="0 0, 10 3.5, 0 7" class="arrow-dashed" />
      </marker>
    </defs>
    
    <rect width="100%" height="100%" fill="#0F1117" rx="10"/>

    <rect x="30" y="100" width="140" height="70" class="box" />
    <text x="100" y="130" class="text-title" text-anchor="middle">Sensores IoT</text>
    <text x="100" y="150" class="text-desc" text-anchor="middle">pH, CH4, AGV</text>

    <rect x="250" y="80" width="300" height="230" class="box" style="stroke: #1D9E75;" />
    <text x="400" y="110" class="text-title" fill="#1D9E75" text-anchor="middle">Plataforma Mendix (Core)</text>

    <rect x="270" y="130" width="260" height="40" class="box" />
    <text x="400" y="155" class="text-title" text-anchor="middle">1. ImportarLeitura (REST Inbound)</text>

    <rect x="270" y="190" width="260" height="40" class="box" />
    <text x="400" y="215" class="text-title" text-anchor="middle">2. AnalisarRisco (Thresholds)</text>

    <rect x="270" y="250" width="260" height="40" class="box" />
    <text x="400" y="275" class="text-title" text-anchor="middle">3. CalcularOtimizacao (Motor Econ)</text>

    <rect x="620" y="240" width="150" height="80" class="box" />
    <text x="695" y="265" class="text-title" text-anchor="middle">APIs Mercado</text>
    <text x="695" y="285" class="text-desc" text-anchor="middle">CCEE (Energia)</text>
    <text x="695" y="300" class="text-desc" text-anchor="middle">B3 (CBIOs)</text>

    <rect x="150" y="360" width="200" height="60" class="box" style="stroke:#E24B4A" />
    <text x="250" y="385" class="text-title" fill="#E24B4A" text-anchor="middle">Notificação Externa (POST)</text>
    <text x="250" y="405" class="text-desc" text-anchor="middle">Alerta de Colapso Crítico</text>

    <rect x="450" y="360" width="200" height="60" class="box-highlight" />
    <text x="550" y="385" class="text-highlight" text-anchor="middle">Dashboard (Frontend)</text>
    <text x="550" y="405" fill="#1A1D27" font-family="Inter" font-size="12" text-anchor="middle">Data Binding Mendix</text>

    <line x1="170" y1="135" x2="260" y2="135" class="line" marker-end="url(#arrowhead)" />
    <text x="215" y="125" class="text-desc" fill="#7F77DD" text-anchor="middle">POST /api/leitura</text>

    <line x1="400" y1="170" x2="400" y2="182" class="line" marker-end="url(#arrowhead)" />
    <line x1="400" y1="230" x2="400" y2="242" class="line" marker-end="url(#arrowhead)" />

    <path d="M 270 210 L 250 210 L 250 350" class="line-dashed" marker-end="url(#arrowhead-dashed)" />
    
    <line x1="620" y1="270" x2="540" y2="270" class="line" marker-end="url(#arrowhead)" />
    <text x="580" y="260" class="text-desc" text-anchor="middle">GET (1h)</text>

    <line x1="400" y1="310" x2="400" y2="335" x2="550" y2="335" y2="350" class="line" marker-end="url(#arrowhead)" />
    <path d="M 400 310 L 400 335 L 550 335 L 550 352" class="line" marker-end="url(#arrowhead)" />
  </svg>
</div>

### 1. Inbound: Sensores IoT (`POST /api/leitura`)
Responsável por garantir que os dados brutos cheguem ao Mendix. Exposto nativamente via **Published REST Service**.

* **Frequência:** A cada 5–15 minutos.
* **Autenticação:** Header `X-API-Key`.
* **Mapeamento:** Transforma o JSON diretamente na entidade `LeituraSensor` via Import Mappings.

**Exemplo de Payload:**
```json
{
  "biodigestor_id": 1,
  "ph": 6.3,
  "ch4_pct": 58.2,
  "temperatura_c": 37.1,
  "agv_mgL": 4200,
  "timestamp": "2026-04-19T14:30:00Z"
}
