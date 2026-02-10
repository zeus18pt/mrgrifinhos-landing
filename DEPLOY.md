# 🚀 Deploy no Vercel

## Passos para configurar deploy automático:

### 1. Acede ao Vercel
- Vai a https://vercel.com
- Login com GitHub (zeus18pt)

### 2. Importar Projeto
- Clica em "Add New Project"
- Seleciona "Import Git Repository"
- Escolhe: `zeus18pt/mrgrifinhos-landing`

### 3. Configurar Deploy
- **Framework Preset:** Other (HTML/CSS/JS)
- **Root Directory:** ./ (default)
- **Build Command:** (deixar vazio)
- **Output Directory:** (deixar vazio)

### 4. Environment Variables
Não são necessárias para este projeto estático.

### 5. Deploy
- Clica em "Deploy"
- O Vercel vai gerar URL tipo: `mrgrifinhos-landing.vercel.app`

### 6. Dominio Custom (opcional)
Se quiseres usar `mrgrifinhos.com`:
1. Vai a Project Settings → Domains
2. Adiciona domínio personalizado
3. Configura DNS no teu registrador

## 🔄 Auto-Deploy
Cada push para `main` faz deploy automático!

## 📁 Estrutura do Projeto
```
/
├── index.html      ← Entry point
├── css/
│   └── styles.css  ← Estilos
├── js/
│   └── main.js     ← Interatividade
└── vercel.json     ← Config Vercel
```

## 🎨 Cores do Projeto
- Primary: #9146FF (Twitch Purple)
- Secondary: #00D4AA (Neon Green)
- Accent: #FF6B35 (Orange)
- Background: #0F0F0F (Dark)

---

**Status:** ✅ Código pronto no GitHub
**Próximo passo:** Conectar ao Vercel (2 minutos)
