<div align="center">
  <!-- Substitua o link abaixo pela URL real da logo do NucleoDigest -->
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
      <b>Participante 1</b>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P2&background=random&color=fff&rounded=true" width="100" alt="Participante 2"><br>
      <b>Participante 2</b>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P3&background=random&color=fff&rounded=true" width="100" alt="Participante 3"><br>
      <b>Participante 3</b>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P4&background=random&color=fff&rounded=true" width="100" alt="Participante 4"><br>
      <b>Participante 4</b>
    </td>
    <td align="center">
      <img src="https://ui-avatars.com/api/?name=P5&background=random&color=fff&rounded=true" width="100" alt="Participante 5"><br>
      <b>Participante 5</b>
    </td>
  </tr>
</table>

---

## 📄 Descrição

**NucleoDigest** é uma infraestrutura digital desenvolvida para o **Hackathon LowHack & Truechange**, focada em resolver a fragilidade sistêmica e a ineficiência econômica de biodigestores industriais. 

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

O núcleo do sistema opera através de quatro blocos de integração REST (dois inbound e dois outbound), orquestrados diretamente pelo Mendix. 

*(Espaço reservado para o Fluxograma SVG de Integração)*

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
```

### 2. Outbound Interno: Guard Biológico e Notificações
O Microflow `AnalisarRisco` processa a leitura em cascata. Se o pH cair ou o AGV ultrapassar o limite configurado via *App Constants*, ele dispara uma requisição HTTP POST assíncrona (via **Consumed REST**) para serviços externos como SendGrid ou Slack, notificando a emergência e gerando um `AlertaBiologico`.

### 3. Outbound de Mercado: Consulta CCEE e RenovaBio (`GET`)
Um **Scheduled Event** roda a cada 1 hora para fazer chamadas HTTP GET nas APIs de preço de energia e crédito de carbono.
Caso o sistema identifique um status saudável no digestor, o Microflow `CalcularOtimizacao` cruza a produção com os preços obtidos e gera uma `Recomendacao` de venda (Energia ou CBIOs) diretamente para a aprovação do operador via Data Binding no dashboard.

---
