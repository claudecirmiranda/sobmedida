# sob-medida

Landing page estática (HTML/CSS puro, sem build, sem backend) para
`sobmedida.soaone.com.br`.

## Deploy no Vercel

1. Crie um repositório (ex: `github.com/claudecirmiranda/sobmedida`) e suba
   este conteúdo:
   ```bash
   git init
   git add .
   git commit -m "Landing sob medida"
   git branch -M main
   git remote add origin https://github.com/claudecirmiranda/sobmedida.git
   git push -u origin main
   ```
2. No painel do Vercel: **New Project → Import** o repositório.
3. **Framework Preset: Other** (é HTML estático puro, sem servidor —
   não tem o risco de detecção automática que teve no projeto `localizador`,
   mas "Other" continua sendo o preset correto aqui).
4. Deploy. Nenhuma env var é necessária.

## Apontar o domínio sobmedida.soaone.com.br

1. No projeto no Vercel: **Settings → Domains → Add** → digite
   `sobmedida.soaone.com.br` → Add.
2. O Vercel vai mostrar um registro **CNAME** para configurar (algo como
   `cname.vercel-dns.com`) — é isso que você usa no passo do Hostinger.
3. Na Hostinger (DNS do domínio `soaone.com.br`): crie um registro
   **CNAME** — Nome: `sobmedida`, Aponta para: o valor que o Vercel
   mostrou, TTL padrão.
4. Aguarde propagar (geralmente minutos) e o Vercel emite o certificado
   SSL sozinho assim que validar o DNS.

## Teste

```bash
dig sobmedida.soaone.com.br +short
curl -I https://sobmedida.soaone.com.br
```
