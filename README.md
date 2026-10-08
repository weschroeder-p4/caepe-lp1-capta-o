# lp1.caepe.com.br — Landing da Pós-Graduação e Treinamentos CAEPE

Página única em HTML+CSS (sem framework), estrutura em 19 dobras espelhando a página-modelo PHDPlus, adaptada à identidade do CAEPE (azul-marinho #031D3C, amarelo #ECBA37, Montserrat + Inter).

## Antes de publicar — preencher

Tudo fica no bloco `CAEPE_CONFIG`, no topo do `index.html`:

| Campo | O que colocar |
|---|---|
| `formUrl` | Já configurado: https://typebot.co/cadastro-vsl. Todos os botões "Quero conhecer as formações" levam para ele, repassando as UTMs da URL. |
| `metaPixelId` | ID do Pixel. Dispara PageView; botões disparam `Lead` (formulário) e `Contact` (WhatsApp). |
| `clarityId` | ID do Microsoft Clarity. |

O token da API de Conversões **não** vai neste arquivo.

## Vídeos (Vturb)

- **Vídeo principal (dobra 02):** já instalado (Vturb, player `vid-6a5a6a11e36bed603b18f005`). Para trocar, substitua o bloco dentro de `id="vsl-caepe"`. O aviso "Você já começou a assistir / Continuar / Do início" é nativo do Vturb (ative "continuar de onde parou").
- **Depoimentos (dobra 07):** em cada `<div class="poster">`, troque pelo embed do vídeo do(a) aluno(a). Há um 4º depoimento comentado no código, pronto para descomentar.

## Pontos para confirmar com a Dra. Caroline

1. **Número de alunos (dobra 03):** usei "Centenas de médicos", como no site oficial. Trocar se houver número oficial.
2. **Certificado do Plano Avançado (comparativo):** está como "Emitido pelo CAEPE". Confirmar se é curso livre.
3. **FAQ "Preciso ser médico formado?":** confirmar critério de entrada da Pós.

## Estrutura

```
/ (raiz do repositório)
├── index.html          ← a página
├── CNAME               ← lp1.caepe.com.br
├── .nojekyll
├── robots.txt / sitemap.xml
├── site.webmanifest, favicon.ico, favicon-*.png, apple-touch-icon.png, android-chrome-*.png
├── og-image.jpg        ← prévia no WhatsApp/Facebook (1200x630)
└── assets/             ← logos, fotos (otimizadas)
```

## Publicar (GitHub Pages + Cloudflare)

1. Crie um repositório **público** no GitHub (ex.: `caepe-lp1`).
2. *Add file → Upload files*: arraste o **conteúdo** desta pasta (não a pasta por fora). O `CNAME` precisa ficar na raiz. Se os arquivos ocultos (`.nojekyll`) não forem, tudo bem.
3. *Settings → Pages*: Source = branch `main`, pasta `/ (root)`. Salvar.
4. Cloudflare → DNS de `caepe.com.br`: registro **CNAME** `lp1` → `SEU-USUARIO.github.io`, **DNS only (nuvem cinza)**.
5. *Settings → Pages → Custom domain*: `lp1.caepe.com.br`. Aguarde "DNS check successful".
6. Marque **Enforce HTTPS** quando liberar.
7. Teste: cadeado HTTPS, Meta Pixel Helper, link colado no WhatsApp (prévia), Clarity registrando sessão.

Para atualizar depois: *Add file → Upload files* com o arquivo de mesmo nome. Ele substitui o antigo, não precisa apagar.
