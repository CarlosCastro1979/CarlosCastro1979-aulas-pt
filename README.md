# Aulas PT

PWA leve para marcar horários feitos — duas pessoas, um preço fixo, o mesmo **código da casa**.

**Live (GitHub Pages):** https://carloscastro1979.github.io/CarlosCastro1979-aulas-pt/

Repositório **independente** da logística (`analises-stock-SAPxUnilog`). Sem pastas partilhadas, sem PRs cruzados.

## Conteúdo

- `index.html` — app (Agenda / Resumo / Definições)
- `manifest.json`, `sw.js`, ícones — instalação PWA
- `supabase.sql` — schema a correr uma vez no Supabase

## Supabase (importante)

A app **não** deve depender para sempre do projeto Supabase da logística.

1. (Recomendado) Cria um projeto Supabase só para Aulas PT.
2. Abre o SQL Editor e executa `supabase.sql`.
3. Em `index.html`, altera o bloco `SB_DEFAULT` (`url` + `anonKey`), **ou** no browser:

```js
localStorage.setItem('aulas_pt_sb', JSON.stringify({
  url: 'https://SEU-PROJETO.supabase.co',
  anonKey: 'eyJ...chave-anon...'
}));
location.reload();
```

Valores actuais em `SB_DEFAULT` são temporários só para a app continuar a abrir até haver projeto dedicado.

## Uso

1. Abre o link Pages no telemóvel.
2. Introduz o **código da casa** (igual nos dois aparelhos).
3. Agenda: escolhe o dia → marca A/B.
4. Resumo + WhatsApp; Definições com autosave ~1 s.
5. Banner **Instalar** (Chrome) ou “Adicionar ao ecrã inicial”.

## Deploy

GitHub Pages: branch `main`, pasta `/` (raiz). Ficheiro `.nojekyll` incluído.
