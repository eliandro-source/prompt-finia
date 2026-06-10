# FinIA · Catálogo de Prompts

Site estático com o catálogo oficial dos 101 prompts FinIA para BPO e Contabilidade, organizados em 11 categorias.

## Estrutura

```
finia-prompts-site/
├── index.html       # Página única com todo o catálogo
├── netlify.toml     # Configuração de headers e cache para Netlify
├── _redirects       # Fallback de rotas para Netlify
├── robots.txt       # Permissão de indexação
├── sitemap.xml      # Mapa do site para buscadores
└── README.md        # Este arquivo
```

Tudo é estático — sem build, sem dependências, sem servidor. O `index.html` é autocontido (CSS inline, logos embutidos em base64, JS inline).

## Deploy

### Opção 1 · Netlify (recomendado · drag & drop)

1. Acesse https://app.netlify.com/drop
2. Arraste a pasta `finia-prompts-site/` inteira para a área indicada
3. Aguarde o upload (~30 segundos)
4. O Netlify gera uma URL automática tipo `https://random-name-123.netlify.app`
5. (Opcional) Em **Site settings → Change site name**, troque para algo como `finia-prompts` → fica `https://finia-prompts.netlify.app`

### Opção 2 · Netlify (CLI)

```bash
npm install -g netlify-cli
cd finia-prompts-site
netlify deploy --prod
```

### Opção 3 · Vercel

```bash
npm install -g vercel
cd finia-prompts-site
vercel --prod
```

### Opção 4 · GitHub Pages

1. Crie um repositório no GitHub (ex: `finia-prompts`)
2. Faça commit dos arquivos:
   ```bash
   cd finia-prompts-site
   git init
   git add .
   git commit -m "Catálogo FinIA · 101 prompts"
   git branch -M main
   git remote add origin https://github.com/SEU-USUARIO/finia-prompts.git
   git push -u origin main
   ```
3. No GitHub, vá em **Settings → Pages → Source → Deploy from a branch → main → / (root)**
4. Aguarde 1-2 minutos → site disponível em `https://SEU-USUARIO.github.io/finia-prompts/`

### Opção 5 · Cloudflare Pages

1. Acesse https://dash.cloudflare.com/?to=/:account/pages
2. **Create a project → Direct Upload**
3. Faça upload da pasta `finia-prompts-site/`
4. URL gerada: `https://finia-prompts.pages.dev`

### Opção 6 · Servidor próprio (Apache, Nginx, qualquer hospedagem cPanel)

Basta enviar o conteúdo da pasta `finia-prompts-site/` para o diretório público (`public_html`, `www`, `htdocs` etc) via FTP/SFTP. Não requer configuração adicional — `index.html` é servido automaticamente.

## Domínio personalizado

Em qualquer das plataformas acima é possível conectar um domínio próprio (ex: `prompts.finia.com.br`). Cada uma tem um passo a passo simples nas configurações de DNS.

## Manutenção

Para atualizar o catálogo (adicionar/remover prompts), basta substituir o `index.html` e fazer redeploy. Os headers do `netlify.toml` já estão configurados para `Cache-Control: max-age=0, must-revalidate` no HTML — atualizações refletem imediatamente para os usuários.
