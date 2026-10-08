# Landing Page: Ebook Joelho "PRP ou Ácido Hialurônico?" (Proregen)

Página estática para captura de leads e entrega do PDF gratuito
**PRP ou Ácido Hialurônico? O que a ciência mais recente mostra sobre a artrose de joelho**,
com oferta do livro **Dói Aqui?** (Dr. André Kruel e Dr. Fábio Costa, Editora Gente).

Clonada da LP de coluna (`/workspace/lp-ebook-coluna`, mesmo visual, mesma marca, mesmo formulário).

## Produção (ligado)

- LP: https://kruelandre-jpg.github.io/proregen-lp-ebook-joelho/
- PDF: https://kruelandre-jpg.github.io/proregen-lp-ebook-joelho/assets/Ebook-Proregen-Joelho-PRP-AH.pdf
- Repositório: https://github.com/kruelandre-jpg/proregen-lp-ebook-joelho (público, GitHub Pages: branch `main`, pasta `/`)
- Form (editar): https://docs.google.com/forms/d/1xPzUMzYMUc2JH0WI6x0QzigushSWmcTtqxx0IJVGjRc/edit
- Form (público): https://docs.google.com/forms/d/e/1FAIpQLSdr3QukBusZnSz9PNobm4qA292Ltv4Jv0QI09jZ5-Vs6wkXRg/viewform
- Form (envio): https://docs.google.com/forms/d/e/1FAIpQLSdr3QukBusZnSz9PNobm4qA292Ltv4Jv0QI09jZ5-Vs6wkXRg/formResponse
- Planilha de respostas (a mesma da LP de coluna): https://docs.google.com/spreadsheets/d/19KvaI8NpkFN5sy23o-YbOq5dU86pzOh5xXNGKq9RAIY/edit
- Entries: nome `entry.212396162` · whatsapp `entry.1389541124` · email `entry.471275429` · interesse `entry.30545821`
- **Interesse enviado por esta LP: `Joelho`** (opção existente no form: Coluna / Joelho / Outro)

As duas LPs gravam na mesma planilha. No Manychat (ou Make/Zapier), segmente pela coluna
**Interesse**: `Coluna` = LP de coluna, `Joelho` = esta LP.

## Estrutura

```
lp-ebook-joelho/
├── index.html
├── styles.css           ← estilos da LP de coluna + blocos novos (estatísticas, para quem, autor)
├── config.js            ← URL do Google Forms, entries, interesse fixo "Joelho"
├── app.js
├── README.md
├── preview/             ← screenshots desktop e mobile (não usados pela página)
└── assets/
    ├── logo-h-dark.svg
    ├── logo-h-light.svg
    ├── doi-aqui-capa.jpg
    ├── ebook-joelho-capa.jpg   ← capa do PDF (pdftoppm, página 1)
    ├── og-joelho.jpg           ← imagem de prévia (WhatsApp/redes), 1200×630
    └── Ebook-Proregen-Joelho-PRP-AH.pdf
```

Sem build. Abra `index.html` no navegador ou hospede a pasta em qualquer static host.

## Seções

1. Hero (capa do PDF, números da revisão: 28 estudos, 2.685 pacientes, 2026)
2. Formulário (nome, WhatsApp, e-mail; interesse fixo "Joelho" em campo oculto)
3. Agradecimento na mesma página: download do PDF, WhatsApp, livro Dói Aqui?
4. O que você vai aprender (6 capítulos do ebook)
5. Para quem é
6. Sobre o autor
7. Livro Dói Aqui?
8. Rodapé com CREMERS 23627, RQE 14323, WhatsApp (54) 99689-1295, aviso educativo e referência

## Fluxo no navegador

1. Usuário preenche e envia.
2. O JS faz `POST` para o `formResponse` com `fetch(..., { mode: 'no-cors' })`
   (resposta opaca; o Forms registra mesmo assim). Se o fetch falhar, há fallback via iframe oculto.
3. Em seguida: esconde o formulário, mostra o agradecimento, botão de download do PDF e oferta do livro.

## Marca

| Token   | Hex     |
|---------|---------|
| `--blue`  | `#66B2E0` |
| `--char`  | `#3A3C38` |
| `--white` | `#FFFFFF` |
| `--tint`  | `#EEF6FC` |
| `--tint2` | `#DCEEF9` |

Fonte: **Sora** (Google Fonts CDN). Logos canônicos copiados da LP de coluna.

## Contato na página

- Dr. André Kruel · CREMERS/CRM-RS 23627 · RQE 14323
- [proregen.com.br](https://proregen.com.br)
- WhatsApp (54) 99689-1295

## Publicar atualização

```
cd /workspace/lp-ebook-joelho
git add -A && git commit -m "Atualiza LP" && git push
```
(GitHub Pages republica sozinho em ~1 min.)
