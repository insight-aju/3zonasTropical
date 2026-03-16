# Tema light remoto para INSIGHT Audio 3 Zonas

## Estrutura recomendada no repositório

```text
seu-repo/
├─ .nojekyll
├─ index.html
├─ themes/
│  └─ tema-light.css
└─ img/
   └─ background-light.svg
```

## Arquivos deste pacote

- `themes/tema-light.css`
- `img/background-light.svg`
- `README-instalacao.md`

## Forma mais estável: usar GitHub Pages

Depois de subir os arquivos e ativar o **GitHub Pages**, a URL do tema ficará assim:

```text
https://SEUUSUARIO.github.io/SEUREPO/themes/tema-light.css
```

A imagem de fundo ficará assim:

```text
https://SEUUSUARIO.github.io/SEUREPO/img/background-light.svg
```

Como o CSS já usa `../img/background-light.svg`, basta manter essa estrutura de pastas que ele encontra a imagem sozinho.

## Passo a passo

1. Crie ou use um repositório no GitHub.
2. Envie os arquivos mantendo exatamente as pastas `themes/` e `img/`.
3. Crie um arquivo vazio chamado `.nojekyll` na raiz do repositório.
4. Crie um `index.html` simples na raiz só para o GitHub Pages ter um arquivo de entrada.
5. No GitHub, abra:
   - `Settings`
   - `Pages`
   - em **Build and deployment**, escolha:
     - **Source** = `Deploy from a branch`
     - **Branch** = `main`
     - **Folder** = `/ (root)`
6. Salve e aguarde a publicação.
7. Copie a URL do CSS publicado.
8. No painel `/diag` do ESP32, cole essa URL no campo **Tema remoto**.
9. Clique em **Salvar**.

## index.html mínimo para o Pages

```html
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>INSIGHT Theme Host</title>
</head>
<body>
  <p>Host de arquivos do tema remoto do INSIGHT.</p>
</body>
</html>
```

## Dica de teste antes do GitHub

Se quiser testar localmente no PC:

### Python

```bash
cd pasta-do-repo
python -m http.server 8080
```

A URL do tema ficará assim:

```text
http://IP-DO-SEU-PC:8080/themes/tema-light.css
```

Depois é só colar essa URL temporária no `/diag` do ESP32.

## Observações

- O seu firmware já está correto para tema remoto: ele busca o CSS e aplica por cima do estilo local.
- Como o CSS remoto aponta a imagem com caminho relativo, é importante **não mover** `background-light.svg` para outra pasta sem ajustar o caminho.
- Se trocar o nome do repositório, a URL do GitHub Pages muda.
