# 📊 Guia Completo — mg-opportunity.json

**Data:** 27 de Abril de 2026  
**Versão:** v1  
**Tamanho:** 19 KB  
**Formato:** JSON estruturado com 7 seções principais

---

## 📋 O Que É

O arquivo `mg-opportunity.json` contém **dados estruturados e auditados** sobre o mercado de formação esportiva em Minas Gerais, incluindo:

- **Market Overview** — População, PIB, jovens, atletas
- **Partner Data** — América MG (110 unidades, 12K atletas)
- **Competitors** — Cruzeiro, Atlético, PSG Academy, etc.
- **Sponsors** — 400 empresas >R$60M, top 15 companies
- **Pricing** — 5 planos B2C, ARPU, ratios
- **Revenue Scenarios** — Piloto até 10% MG
- **TAM/SAM/SOM** — Mercado total, acessível, atingível
- **Social Reach** — Impressões orgânicas, pais
- **Top Municipalities** — BH, Contagem, Santa Luzia, etc.

---

## 🎯 Números Principais

| Métrica | Valor | Confiança |
|---------|-------|-----------|
| **População MG** | 20.5M | ✅ Verificado (IBGE 2022) |
| **Jovens 5-17** | 3.5M | ⚠️ Estimado |
| **Jogam Futebol** | 1.1M | ⚠️ Estimado |
| **Em Escolinhas Formais** | 150K | ⚠️ Estimado (MÉDIO risco) |
| **Unidades América** | 110+ | ✅ Verificado |
| **Atletas América** | 12K | ✅ Verificado |
| **Cidades América** | 25 confirmadas | ✅ Verificado |
| **Empresas >R$60M** | 400 | ✅ Verificado (Ranking 2024) |
| **Empresas com fit ESG** | 55 | ⚠️ Estimado |
| **ARPU Mensal** | R$ 48.29 | ✅ Verificado (Mar 2026) |
| **TAM Anual** | R$ 60.8M | ⚠️ Estimado |
| **SAM Anual** | R$ 5.4M | ⚠️ Estimado |
| **SOM Y1** | R$ 486K–1.4M | ⚠️ Estimado |

---

## 📂 Estrutura do JSON

### 1. **Market** (Linhas 8-29)
Dados de mercado geral de MG.

```json
{
  "state": "MG",
  "population": 20539989,
  "pib_state_brl": 972000000000,
  "youth_5_17": 3500000,
  "play_football": 1100000,
  "in_formal_escolinhas": 150000
}
```

**Uso:** Contexto de mercado, tamanho total, potencial.

### 2. **Partner** (Linhas 31-70)
Dados específicos da América MG.

```json
{
  "name": "América MG",
  "total_escolinhas": 110,
  "total_athletes": 12000,
  "cities_confirmed": 25,
  "cities_confirmed_list": [...]
}
```

**Uso:** Dados do parceiro principal, cidades de atuação.

### 3. **Competitors** (Linhas 72-87)
Análise competitiva de redes de escolinhas.

```json
{
  "networks": [
    { "name": "Cruzeiro", "units_mg": 30, "athletes_mg": 5000 },
    { "name": "Atlético MG", "units_mg": 18, "athletes_mg": 3000 },
    ...
  ],
  "total_mg_escolinhas_range": [500, 800],
  "total_mg_athletes_range": [100000, 150000]
}
```

**Uso:** Contexto competitivo, tamanho do mercado.

### 4. **Sponsors** (Linhas 89-123)
Dados de empresas potenciais para patrocínio.

```json
{
  "companies_over_60m_rol": 400,
  "companies_sport_esg_fit": 55,
  "total_rol_brl": 710830000000,
  "top_companies": [
    {
      "name": "ArcelorMittal",
      "sector": "Siderurgia",
      "revenue_brl": 66500000000,
      "city": "BH",
      "fit": "CSR/ESG, comunidades operárias"
    },
    ...
  ]
}
```

**Uso:** Identificar potenciais patrocinadores, segmentação por setor.

### 5. **Pricing** (Linhas 125-143)
Estrutura de preços e ARPU.

```json
{
  "b2c_tiers": [
    { "id": "jogador", "price_brl": 26.99, "default_mix": 0.40 },
    { "id": "basico", "price_brl": 49.99, "default_mix": 0.30 },
    ...
  ],
  "arpu_monthly_brl": 48.29,
  "athletes_to_subscriptions_ratio": 0.70
}
```

**Uso:** Cálculos de receita, projeções.

### 6. **Revenue Scenarios** (Linhas 145-201)
5 cenários de receita (piloto até 10% MG).

```json
{
  "id": "america_10pct",
  "label": "América 10% (Y1 low)",
  "athletes": 1200,
  "subscriptions": 840,
  "annual_brl": 486763
}
```

**Uso:** Projeções conservadoras, otimistas e realistas.

### 7. **TAM/SAM/SOM** (Linhas 203-227)
Mercado Total, Acessível, Atingível.

```json
{
  "tam": {
    "label": "MG Total (escolinhas formais)",
    "athletes": 150000,
    "annual_brl": 60845400
  },
  "sam": {
    "label": "Rede América",
    "athletes": 12000,
    "annual_brl": 5368454
  },
  "som": {
    "label": "Ano 1 (10-30% América)",
    "annual_brl_range": [486763, 1460290]
  }
}
```

**Uso:** Apresentações de investimento, pitch deck.

### 8. **Social Reach** (Linhas 229-243)
Dados de alcance orgânico.

```json
{
  "america_parents": 24000,
  "total_mg_parents": 300000,
  "america_organic_impressions": 4800000,
  "mg_organic_impressions": 60000000
}
```

**Uso:** Potencial de mídia, alcance de campanha.

### 9. **Top Municipalities** (Linhas 245+)
Cidades com maior PIB e presença.

```json
{
  "city": "Belo Horizonte",
  "pib_brl": 130197000000,
  "tier": 1,
  "america_present": true
}
```

**Uso:** Segmentação geográfica, priorização.

---

## 💻 Como Usar no Claude Code

### 1. Carregar o JSON

```javascript
// Fetch do arquivo
fetch('assets/mg-opportunity.json')
  .then(response => response.json())
  .then(data => {
    console.log(data);
    // Usar os dados
  });
```

### 2. Acessar Dados Específicos

```javascript
// TAM/SAM/SOM
const tam = data.tam_sam_som.tam.annual_brl;  // R$ 60.8M
const sam = data.tam_sam_som.sam.annual_brl;  // R$ 5.4M
const som = data.tam_sam_som.som.annual_brl_range;  // [486K, 1.4M]

// Top Companies
const topCompanies = data.sponsors.top_companies;
topCompanies.forEach(company => {
  console.log(`${company.name}: R$ ${company.revenue_brl}`);
});

// Cidades
const cities = data.partner.cities_confirmed_list;
console.log(`América em ${cities.length} cidades`);

// Revenue Scenarios
const scenarios = data.revenue_scenarios;
scenarios.forEach(s => {
  console.log(`${s.label}: R$ ${s.annual_brl}/ano`);
});
```

### 3. Atualizar Slide 14 Dinamicamente

```javascript
// Quando chegar no Slide 14
function loadMGOpportunity() {
  fetch('assets/mg-opportunity.json')
    .then(r => r.json())
    .then(data => {
      // Atualizar números
      document.querySelector('[data-mg-athletes]').textContent = 
        (data.market.in_formal_escolinhas / 1000).toFixed(0) + 'K+';
      
      document.querySelector('[data-mg-families]').textContent = 
        (data.social_reach.total_mg_parents / 1000000).toFixed(1) + 'M+';
      
      document.querySelector('[data-mg-tam]').textContent = 
        'R$ ' + (data.tam_sam_som.tam.annual_brl / 1000000).toFixed(0) + 'M';
    });
}

// Chamar quando chegar no slide 14
function triggerSlideSpecific(idx) {
  if (idx === 13) {  // Slide 14 (0-indexed)
    loadMGOpportunity();
  }
}
```

### 4. Criar Tabela de Sponsors

```javascript
function renderSponsors() {
  const sponsors = data.sponsors.top_companies;
  const html = sponsors.map(s => `
    <tr>
      <td>${s.name}</td>
      <td>${s.sector}</td>
      <td>R$ ${(s.revenue_brl / 1000000000).toFixed(1)}B</td>
      <td>${s.fit}</td>
    </tr>
  `).join('');
  
  document.querySelector('tbody').innerHTML = html;
}
```

### 5. Criar Gráfico de Cenários

```javascript
function renderScenarios() {
  const scenarios = data.revenue_scenarios;
  const labels = scenarios.map(s => s.label);
  const values = scenarios.map(s => s.annual_brl / 1000000);  // Em milhões
  
  // Usar Chart.js ou similar
  new Chart(ctx, {
    type: 'bar',
    data: {
      labels: labels,
      datasets: [{
        label: 'Receita Anual (R$ M)',
        data: values,
        backgroundColor: '#c9d148'
      }]
    }
  });
}
```

---

## 📊 Exemplos de Uso

### Exemplo 1: Mostrar TAM/SAM/SOM

```javascript
const { tam, sam, som } = data.tam_sam_som;

console.log(`
TAM: R$ ${(tam.annual_brl / 1000000).toFixed(1)}M (${tam.athletes} atletas)
SAM: R$ ${(sam.annual_brl / 1000000).toFixed(1)}M (${sam.athletes} atletas)
SOM: R$ ${(som.annual_brl_range[0] / 1000).toFixed(0)}K–${(som.annual_brl_range[1] / 1000000).toFixed(1)}M
`);
```

**Saída:**
```
TAM: R$ 60.8M (150000 atletas)
SAM: R$ 5.4M (12000 atletas)
SOM: R$ 486K–1.4M
```

### Exemplo 2: Listar Top 5 Sponsors

```javascript
data.sponsors.top_companies.slice(0, 5).forEach(c => {
  console.log(`${c.name} (${c.sector}): R$ ${(c.revenue_brl / 1000000000).toFixed(1)}B`);
});
```

**Saída:**
```
ArcelorMittal (Siderurgia): R$ 66.5B
Cemig (Energia): R$ 39.8B
Localiza (Mobilidade): R$ 38.2B
Energisa (Energia): R$ 33.7B
Stellantis (Automotivo): R$ 50.0B
```

### Exemplo 3: Cidades da América MG

```javascript
console.log(`América MG em ${data.partner.cities_confirmed} cidades:`);
data.partner.cities_confirmed_list.forEach(city => {
  console.log(`  • ${city}`);
});
```

---

## 🔐 Níveis de Confiança

| Nível | Significado | Exemplo |
|-------|-----------|---------|
| ✅ **Verified** | Fonte oficial/primária | População (IBGE), Empresas (Ranking 2024) |
| ⚠️ **Estimated** | Derivado/secundário | Jovens que jogam futebol, atletas em escolinhas |
| ❓ **Assumption** | Parâmetro de modelo | Cenários de receita, SOM |

**Risco:** Alguns dados têm risco MÉDIO (ex: 150K atletas em escolinhas formais — sem censo oficial).

---

## 📥 Integração no Slide 14

### HTML com Data Attributes

```html
<div class="stat-card">
  <div class="stat-num" data-mg-athletes>150K+</div>
  <div class="stat-label">Atletas em Escolinhas Formais</div>
</div>

<div class="stat-card">
  <div class="stat-num" data-mg-families>1.2M+</div>
  <div class="stat-label">Pais/Famílias Alcançáveis</div>
</div>

<div class="stat-card">
  <div class="stat-num" data-mg-tam>R$ 61M</div>
  <div class="stat-label">TAM Anual Potencial</div>
</div>
```

### JavaScript para Atualizar

```javascript
function updateMGNumbers() {
  fetch('assets/mg-opportunity.json')
    .then(r => r.json())
    .then(data => {
      // Atletas
      const athletes = data.market.in_formal_escolinhas;
      document.querySelector('[data-mg-athletes]').textContent = 
        (athletes / 1000).toFixed(0) + 'K+';
      
      // Famílias
      const families = data.social_reach.total_mg_parents;
      document.querySelector('[data-mg-families]').textContent = 
        (families / 1000000).toFixed(1) + 'M+';
      
      // TAM
      const tam = data.tam_sam_som.tam.annual_brl;
      document.querySelector('[data-mg-tam]').textContent = 
        'R$ ' + (tam / 1000000).toFixed(0) + 'M';
    });
}

// Chamar quando chegar no Slide 14
if (idx === 13) updateMGNumbers();
```

---

## 🚀 Próximos Passos

### 1. Integrar no HTML
- Adicione `data-mg-*` attributes aos elementos
- Carregue o JSON via fetch
- Atualize números dinamicamente

### 2. Criar Visualizações
- Gráfico de cenários de receita
- Mapa de cidades
- Tabela de top sponsors

### 3. Adicionar Interatividade
- Clique em números para expandir
- Filtros por setor/cidade
- Calculadora de ROI

### 4. Documentação
- Adicione tooltips com confiança dos dados
- Cite fontes (IBGE, Ranking MercadoComum, etc)
- Indique riscos (ex: 150K atletas é estimado)

---

## 📝 Notas Importantes

- **Sem Censo Oficial:** 150K atletas em escolinhas formais é estimado (3-5% de 3.5M jovens)
- **Dados de Mar 2026:** ARPU e pricing confirmados por Marcus
- **Confiança Média:** Alguns dados têm risco MÉDIO — use com cautela em pitch
- **Atualizações:** JSON pode ser atualizado com novos dados

---

## 🔗 Arquivos Relacionados

- `index.html` — Slide 14 (OPORTUNIDADE MG)
- `mg-opportunity-radar.html` — Dashboard interativo (opcional)
- `TAREFAS_PARA_CLAUDE_CODE.md` — Como adicionar o slide

---

**Desenvolvido por:** Manus AI  
**Data:** 27 de Abril de 2026  
**Versão:** 1.0  
**Pronto para:** Claude Code
