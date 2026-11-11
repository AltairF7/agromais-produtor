# Agromais — Escritório Contábil

Landing page de alta conversão do Agromais, software de gestão fiscal e financeira do produtor rural, voltada para escritórios contábeis.

## Estrutura do projeto

```text
agromais-contabil/
├── index.html
├── vercel.json
└── README.md
```

- **index.html** — a página completa: HTML, CSS e JavaScript em um único arquivo, sem dependências externas e sem processo de build.
- **vercel.json** — define cabeçalhos de segurança (X-Content-Type-Options, X-Frame-Options, Referrer-Policy e Permissions-Policy) e a política de cache para o `index.html`.

## Como publicar no GitHub

1. Crie um repositório novo no GitHub (pode ser privado). Sugestão de nome: `agromais-contabil`
2. Não inicialize com README, `.gitignore` ou licença
3. Na página do repositório, clique em **Add file** e depois em **Upload files**
4. Arraste os arquivos `index.html`, `vercel.json` e `README.md`
5. Escreva a mensagem de commit "Deploy inicial" e clique em **Commit changes**

Alternativa por linha de comando:

```bash
git init
git add .
git commit -m "Deploy inicial"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/agromais-contabil.git
git push -u origin main
```

## Como importar no Vercel

1. Acesse [vercel.com](https://vercel.com) e faça login (pode entrar com a conta do GitHub)
2. Clique em **Add New** e depois em **Project**
3. Conecte sua conta do GitHub se ainda não estiver conectada
4. Selecione o repositório `agromais-contabil` e clique em **Import**
5. Nas configurações do projeto, preencha:
   - **Framework Preset:** Other
   - **Build Command:** deixe vazio
   - **Output Directory:** deixe vazio
   - **Root Directory:** `./`
   - **Install Command:** deixe vazio
6. Clique em **Deploy**
7. Em cerca de 30 segundos a página estará no ar com uma URL do tipo `agromais-contabil.vercel.app`

## Como configurar domínio próprio

1. No painel do projeto no Vercel, vá em **Settings** e depois em **Domains**
2. Digite o domínio desejado e clique em **Add**
3. O Vercel mostrará os registros de DNS a configurar no seu provedor de domínio
4. Para domínio raiz (exemplo.com.br): crie um registro do tipo **A** apontando para `76.76.21.21`
5. Para subdomínio (exemplo: lp.exemplo.com.br): crie um registro do tipo **CNAME** apontando para `cname.vercel-dns.com`
6. Aguarde a propagação do DNS (pode levar de alguns minutos até 24 horas)
7. O certificado HTTPS é emitido automaticamente pelo Vercel após a propagação

## Antes de publicar — checklist

- [ ] Substituir `SEU_PIXEL_ID` pelo ID do Meta Pixel (2 ocorrências no index.html)
- [ ] Substituir `G-XXXXXXXXXX` pelo ID do Google Analytics 4 (2 ocorrências no index.html)
- [ ] Confirmar que o número do WhatsApp está correto: (55) 98112-4961
- [ ] Testar todos os botões de WhatsApp em desktop e celular
- [ ] Validar o Meta Pixel com a extensão Meta Pixel Helper
- [ ] Validar o Google Tag com a extensão Tag Assistant
- [ ] Testar o acordeão de Perguntas Frequentes em desktop e mobile
- [ ] Revisar a exibição em celular (menu hambúrguer, textos e botões)
- [ ] Confirmar que os textos e depoimentos estão corretos

## Atualizações futuras

Após o primeiro deploy, qualquer alteração no repositório do GitHub é publicada automaticamente pelo Vercel em poucos segundos. Basta editar o `index.html` diretamente no GitHub (ou enviar a nova versão) e fazer commit — o Vercel detecta a mudança e publica a nova versão sem nenhuma configuração adicional.

## Rastreamento de conversão

A página dispara o evento **PageView** ao carregar e, no clique de qualquer botão de WhatsApp, dispara o evento **Contact** no Meta e **generate_lead** no Google Analytics 4.

O script escuta qualquer link que contenha `wa.me`, portanto novos botões de WhatsApp são rastreados automaticamente, sem necessidade de alterar o código de rastreamento.
