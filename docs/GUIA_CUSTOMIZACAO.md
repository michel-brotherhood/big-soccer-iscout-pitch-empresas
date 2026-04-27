# Guia de Customização para Claude Code

## 🎯 Objetivo

Este guia fornece instruções práticas para customizar a apresentação Big Soccer by iSCOUT usando Claude Code ou qualquer editor de código.

---

## 📝 Edições Comuns

### 1. Alterar Cores da Marca

**Localização**: `index.html` → `<style>` → `:root`

```css
:root {
  --brand-pink: #de204c;    /* Mude para sua cor principal */
  --brand-lime: #c9d148;    /* Mude para sua cor secundária */
  --slide-accent: #de204c;  /* Cor dinâmica dos slides */
}
```

**Exemplo**: Para azul e laranja
```css
--brand-pink: #0066cc;
--brand-lime: #ff9900;
```

---

### 2. Alterar Textos dos Slides

**Localização**: `index.html` → `<div class="slide">`

**Exemplo - Slide de Capa**:
```html
<!-- Antes -->
<div class="title-subtitle ai" style="--d:.3s;margin-top:24px;">
  Transformando a formação esportiva em Atibaia
</div>

<!-- Depois -->
<div class="title-subtitle ai" style="--d:.3s;margin-top:24px;">
  Seu novo texto aqui
</div>
```

**Dica**: Use `<span class="accent">texto</span>` para destacar em cor

---

### 3. Alterar Imagens

**Localização**: `index.html` → `src="assets/..."`

```html
<!-- Antes -->
<img class="hero-bg" src="assets/01-hero-stadium.webp" alt="">

<!-- Depois -->
<img class="hero-bg" src="assets/sua-imagem.webp" alt="">
```

**Passos**:
1. Coloque a nova imagem em `/assets/`
2. Altere o `src` no HTML
3. Mantenha o formato WebP para melhor performance

---

### 4. Adicionar Novo Slide

**Localização**: `index.html` → `<div class="deck">`

**Template**:
```html
<!-- Novo Slide -->
<div class="slide" data-accent="#de204c" data-section="MINHA SEÇÃO">
  <img class="hero-bg" src="assets/imagem.webp" aria-hidden="true" alt="">
  <div class="hero-overlay" style="background:linear-gradient(...)"></div>
  
  <div class="kicker ai" style="--d:.05s">Subtítulo</div>
  <div class="headline ai" style="--d:.15s">
    Meu <span class="accent">título</span> aqui.
  </div>
  <div class="subline ai" style="--d:.3s">
    Descrição do slide...
  </div>
</div>
```

**Importante**:
- Mantenha `data-section` único
- Use `data-accent` com cor hex válida
- Incremente `--d` (delay) para cada elemento

---

### 5. Alterar Números/Dados

**Localização**: Procure pelos números nos slides

**Exemplo - Slide de Alcance**:
```html
<!-- Antes -->
<div class="stat-num">500+</div>
<div class="stat-label">Atletas em Formação</div>

<!-- Depois -->
<div class="stat-num">1000+</div>
<div class="stat-label">Meu novo rótulo</div>
```

---

### 6. Alterar Logo

**Localização**: `index.html` → `<img class="brand-logo-img">`

```html
<!-- Antes -->
<img class="brand-logo-img" src="assets/big-soccer-logo.webp" alt="BigSoccer by iSCOUT">

<!-- Depois -->
<img class="brand-logo-img" src="assets/nova-logo.webp" alt="Minha Logo">
```

---

### 7. Alterar Animações

**Localização**: `index.html` → `<style>` → `@keyframes`

**Exemplo - Velocidade das Orbs**:
```css
/* Antes */
.orb-a { animation: floatA 12s ease-in-out infinite; }

/* Depois (mais rápido) */
.orb-a { animation: floatA 6s ease-in-out infinite; }
```

**Tempos Comuns**:
- Rápido: 6-8s
- Normal: 10-15s
- Lento: 18-25s

---

### 8. Alterar Tipografia

**Localização**: `index.html` → `<style>` → `.headline`, `.subline`, etc.

**Exemplo - Tamanho da Headline**:
```css
/* Antes */
.headline {
  font-size: clamp(2rem, 5vw, 3.8rem);
}

/* Depois (maior) */
.headline {
  font-size: clamp(2.5rem, 6vw, 4.5rem);
}
```

**Nota**: Use `clamp()` para responsividade automática

---

### 9. Alterar Espaçamento

**Localização**: `index.html` → `<style>` → `padding`, `margin`, `gap`

**Exemplo - Padding dos Slides**:
```css
/* Antes */
.slide { padding: 60px 80px; }

/* Depois (mais compacto) */
.slide { padding: 40px 60px; }
```

---

### 10. Alterar Duração de Transições

**Localização**: `index.html` → `<style>` → `transition`

**Exemplo - Transição de Slides**:
```css
/* Antes (rápido) */
.slide { transition: opacity 0.55s cubic-bezier(.4,0,.2,1), ... }

/* Depois (mais lento) */
.slide { transition: opacity 1s cubic-bezier(.4,0,.2,1), ... }
```

---

## 🎨 Customizações Avançadas

### Alterar Paleta de Cores Completa

**Localização**: `index.html` → `:root`

```css
:root {
  --bg:       #0a0a0f;      /* Fundo principal */
  --surface:  #12121a;      /* Superfícies */
  --text:     #e0e0e0;      /* Texto padrão */
  --dim:      #888;         /* Texto secundário */
  --bright:   #fff;         /* Texto destaque */
  
  /* Cores de seção */
  --blue:   #4fc3f7;
  --green:  #22c55e;
  --amber:  #f59e0b;
  --purple: #a78bfa;
  --orange: #f97316;
  
  /* Cores de marca */
  --brand-pink: #de204c;
  --brand-lime: #c9d148;
}
```

---

### Criar Novo Componente

**Exemplo - Novo Card Style**:

```css
/* Adicione no <style> */
.card-custom {
  background: var(--surface);
  border: 2px solid var(--brand-pink);
  border-radius: 16px;
  padding: 24px 32px;
  box-shadow: 0 8px 32px rgba(222, 32, 76, 0.15);
}
```

**Use no HTML**:
```html
<div class="card-custom ai" style="--d:.3s">
  Conteúdo customizado
</div>
```

---

### Alterar Layout de Grid

**Localização**: `index.html` → `.ganha-grid`, `.pilares-grid`, etc.

```css
/* Antes - 2 colunas */
.ganha-grid { grid-template-columns: 1fr 1fr; }

/* Depois - 3 colunas */
.ganha-grid { grid-template-columns: 1fr 1fr 1fr; }
```

---

### Adicionar Efeito de Hover

**Exemplo - Hover em Cards**:

```css
.card:hover {
  border-color: var(--brand-pink);
  box-shadow: 0 0 40px rgba(222, 32, 76, 0.2);
  transform: translateY(-4px);
}
```

---

## 🔧 Troubleshooting

### Problema: Imagens não aparecem
**Solução**: 
1. Verifique o caminho: `assets/nome-arquivo.webp`
2. Certifique-se que o arquivo existe em `/assets/`
3. Use caminhos relativos: `assets/` (não `/assets/`)

### Problema: Cores não mudam
**Solução**:
1. Limpe o cache do navegador (Ctrl+Shift+Delete)
2. Verifique se editou `:root` corretamente
3. Use cores em formato hex: `#rrggbb`

### Problema: Animações não funcionam
**Solução**:
1. Verifique se `prefers-reduced-motion` está desativado
2. Confirme que o `--d` (delay) está correto
3. Teste em outro navegador

### Problema: Layout quebrado em mobile
**Solução**:
1. Verifique os `@media` queries
2. Teste com DevTools (F12 → Toggle device toolbar)
3. Ajuste os breakpoints conforme necessário

---

## 📱 Responsividade

### Breakpoints Padrão

```css
/* Desktop */
@media (min-width: 1024px) { /* Estilos desktop */ }

/* Tablet */
@media (max-width: 1024px) { /* Estilos tablet */ }

/* Mobile */
@media (max-width: 768px) { /* Estilos mobile */ }
```

### Adicionar Breakpoint Customizado

```css
@media (max-width: 600px) {
  .headline { font-size: clamp(1.5rem, 4vw, 2.5rem); }
  .slide { padding: 30px 20px; }
}
```

---

## 🚀 Deploy Rápido

### Vercel (Recomendado)
```bash
npm install -g vercel
vercel
```

### GitHub Pages
```bash
git add .
git commit -m "Update"
git push origin main
```

### Netlify
```bash
npm install -g netlify-cli
netlify deploy --prod --dir=.
```

---

## 📊 Estrutura do Código

### HTML
- Semântico e acessível
- Cada slide é um `<div class="slide">`
- Elementos com `class="ai"` para animação

### CSS
- Variables CSS em `:root`
- Mobile-first approach
- Clamp() para tipografia responsiva
- Flexbox e Grid para layouts

### JavaScript
- Vanilla (sem dependências)
- Event listeners para navegação
- RequestAnimationFrame para animações
- LocalStorage para preferências

---

## 💡 Dicas & Boas Práticas

### ✅ Faça
- Use `clamp()` para tipografia responsiva
- Mantenha delays progressivos (`--d`)
- Teste em mobile antes de publicar
- Use WebP para imagens
- Mantenha acessibilidade (ARIA labels)

### ❌ Evite
- Não altere a estrutura HTML drasticamente
- Não remova o JavaScript de navegação
- Não use cores muito similares (contraste)
- Não adicione muitas animações (performance)
- Não esqueça de testar em diferentes navegadores

---

## 📚 Recursos Úteis

### Ferramentas Online
- **Color Picker**: https://htmlcolorcodes.com/
- **Easing Functions**: https://easings.net/
- **Responsive Test**: https://responsively.app/
- **WebP Converter**: https://convertio.co/

### Documentação
- **CSS Clamp**: https://developer.mozilla.org/en-US/docs/Web/CSS/clamp()
- **CSS Grid**: https://css-tricks.com/snippets/css/complete-guide-grid/
- **Flexbox**: https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- **SVG**: https://developer.mozilla.org/en-US/docs/Web/SVG

---

## 🎓 Exemplos Práticos

### Exemplo 1: Mudar Cor de Seção
```html
<!-- Mude data-accent -->
<div class="slide" data-accent="#ff6b6b" data-section="NOVA SEÇÃO">
  <!-- Conteúdo -->
</div>
```

### Exemplo 2: Adicionar Emoji
```html
<div class="kicker">🎯 Meu Novo Kicker</div>
```

### Exemplo 3: Destacar Texto
```html
<div class="headline">
  Meu texto com <span class="accent">destaque em cor</span>
</div>
```

### Exemplo 4: Adicionar Badge
```html
<span class="badge badge-accent">✨ Novo Badge</span>
```

---

## 🔐 Segurança

### Boas Práticas
- ✅ Valide URLs antes de adicionar links
- ✅ Use HTTPS para deploy
- ✅ Não exponha dados sensíveis no HTML
- ✅ Mantenha dependências atualizadas

---

## 📞 Suporte

Se tiver dúvidas sobre customização:
1. Consulte `ESTRUTURA_SLIDES.md` para detalhes de cada slide
2. Verifique o `README.md` para visão geral
3. Teste alterações em um branch separado
4. Use DevTools (F12) para debugar

---

**Última atualização**: 27 de Abril de 2026

Aproveite a customização! 🎨
