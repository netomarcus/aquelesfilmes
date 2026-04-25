# Aqueles Filmes — Site

Site estático pronto para o GitHub Pages.

---

## Estrutura de arquivos

```
aquelesfilmes/
├── index.html       → página inicial
├── sobre.html       → sobre a produtora e o diretor
├── filmes.html      → filmografia completa
├── imagens.html     → galeria com lightbox e filtros
├── contato.html     → formulário de contato
├── style.css        → estilos compartilhados
└── images/          → coloque aqui todas as fotos
    ├── hero.jpg          (foto da home, ~1920px largura)
    ├── diretor.jpg       (foto do diretor, proporção 3:4)
    ├── levantados-thumb.jpg
    ├── paladino-thumb.jpg
    └── ...stills...
```

---

## Como publicar no GitHub Pages

1. Crie conta em github.com
2. Instale o GitHub Desktop (desktop.github.com)
3. No GitHub Desktop: File → New Repository → nome: `aquelesfilmes`
4. Arraste todos os arquivos para a pasta do repositório
5. Clique em "Commit to main" e depois "Publish repository"
6. No github.com, vá em Settings → Pages → Source: main → / (root) → Save
7. Em alguns minutos o site estará em: https://SEUNOME.github.io/aquelesfilmes

---

## Como atualizar o site depois

1. Edite o arquivo no VS Code
2. Salve
3. No GitHub Desktop: escreva uma mensagem (ex: "atualizo filmografia") e clique "Commit to main"
4. Clique "Push origin"
5. Pronto — o site atualiza em ~1 minuto

---

## Imagens

- Coloque todos os arquivos JPG na pasta `images/`
- Tamanho recomendado: máximo 1800px de largura
- Comprima em jpegmini.com ou squoosh.app antes de subir (mantém o site leve)
- Nos arquivos HTML, cada placeholder indica exatamente onde colocar a tag `<img>`

### Adicionar still na galeria (imagens.html)

Substitua cada bloco de placeholder:
```html
<div class="gallery-item" data-projeto="levantados" onclick="abreLb(this)">
  <div class="ph" style="aspect-ratio:3/4">...</div>
</div>
```

Por:
```html
<div class="gallery-item" data-projeto="levantados" onclick="abreLb(this)">
  <img src="images/levantados-01.jpg" alt="Levantados do Chão — still 01"
       data-caption="Levantados do Chão, 2024">
  <div class="overlay"><span class="overlay-label">Levantados do Chão</span></div>
</div>
```

---

## Trailers (filmes.html)

1. Suba o trailer no YouTube
2. Copie o ID do vídeo (a parte depois de `watch?v=`)
   Exemplo: em `youtube.com/watch?v=dQw4w9WgXcQ` o ID é `dQw4w9WgXcQ`
3. No filmes.html, cole o ID no atributo `data-yt` do filme:
   ```html
   <button class="trailer-btn" data-yt="dQw4w9WgXcQ" onclick="abreTrailer(this)">
   ```
4. O botão de play aparece automaticamente no hover da thumb

---

## Formulário de contato (contato.html)

1. Crie conta gratuita em formspree.io
2. Clique em "New Form"
3. Copie o endpoint gerado (ex: `https://formspree.io/f/xabcdefg`)
4. No contato.html, cole no atributo `action` do formulário:
   ```html
   <form action="https://formspree.io/f/xabcdefg" ...>
   ```
5. Plano gratuito: 50 envios/mês

---

## Domínio próprio (opcional — R$40/ano)

1. Registre `aquelesfilmes.com.br` em registro.br
2. No registro.br, configure os DNS apontando para o GitHub Pages
   (o GitHub explica o passo a passo em docs.github.com/pages/custom-domain)
3. No GitHub → Settings → Pages → Custom domain: coloque `aquelesfilmes.com.br`
