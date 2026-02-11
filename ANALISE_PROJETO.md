# Análise Técnica do Projeto `mrgrifinhos-landing`

Data: 2026-02-11

## Resumo executivo

O projeto está bem orientado para uma landing page estática (HTML/CSS/JS), com boa identidade visual e estrutura sem dependências de build. O principal risco atual é de manutenção e performance por causa do tamanho do CSS, além de alguns pontos de segurança e acessibilidade que podem ser melhorados.

## Pontos fortes

- **Stack simples e robusta** para deploy estático (`index.html`, `css/styles.css`, `js/main.js`).
- **Boa consistência de branding** (hero, parceiros, secção de contacto).
- **Layout responsivo** com múltiplos breakpoints para mobile.
- **Código JS modular** em funções separadas para scroll, menu e cópia de código.

## Observações técnicas

### 1) Arquitetura e organização

- O repositório é focado numa SPA estática simples, sem pipeline de build, o que reduz fricção operacional.
- A documentação de deploy e investigação existe e ajuda no contexto operacional.

### 2) Front-end e UX

- Hero section com proposta de valor clara e CTAs bem visíveis.
- Secção de parceiros e contacto com blocos orientados a conversão.
- Interações úteis: smooth scroll, menu mobile e botões de cópia.

### 3) Riscos / dívida técnica

1. **CSS muito extenso para o escopo atual**
   - `css/styles.css` tem ~3k linhas, com vários blocos de media queries repetidos.
   - Risco: regressões em alterações futuras e custo de manutenção elevado.

2. **Código JS potencialmente órfão**
   - Existe `initContactForm()` no JS, mas o HTML atual não tem `<form>` com `.contacto-form`.
   - Risco: complexidade desnecessária e confusão para futuros contribuidores.

3. **Segurança em links externos**
   - Vários links usam `target="_blank"` sem `rel="noopener noreferrer"`.
   - Risco: tabnabbing e partilha de contexto da janela.

4. **Acessibilidade e motion preferences**
   - Existem animações contínuas e efeitos visuais, mas sem fallback evidente para `prefers-reduced-motion`.
   - Risco: impacto para utilizadores sensíveis a movimento.

## Plano recomendado (prioridade)

### Alta prioridade (1-2 dias)

1. Adicionar `rel="noopener noreferrer"` em todos os links externos com `target="_blank"`.
2. Remover ou completar a lógica de formulário (`initContactForm`) para evitar código morto.
3. Definir um baseline de qualidade:
   - validação HTML,
   - lint simples de CSS/JS,
   - checklist de acessibilidade básica.

### Média prioridade (3-5 dias)

1. Refatorar CSS por blocos/componentes (navbar, hero, parceiros, contacto, footer).
2. Consolidar media queries repetidas em blocos únicos por breakpoint.
3. Criar estilos para `:focus-visible` em links e botões interativos.

### Baixa prioridade (evolutivo)

1. Otimização de imagens (formatos modernos + dimensões responsivas).
2. Melhorar SEO social (Open Graph/Twitter cards).
3. Definir métricas de performance (LCP/CLS/INP) para acompanhar evolução.

## Conclusão

A base está sólida para uma landing page de conversão e branding. O próximo salto de qualidade está menos em novas features e mais em **hardening técnico**: segurança em links, acessibilidade e simplificação de CSS/JS para reduzir custo de manutenção.
