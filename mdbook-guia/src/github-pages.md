## Publicar el llibre amb GitHub Pages

Un cop tinguis el llibre creat i funcionant en local, pots publicar-lo fàcilment a Internet utilitzant **GitHub Pages**.  
Això permetrà accedir-hi des de qualsevol navegador mitjançant una URL pública.

---

### 1. Crear el workflow d'automatització

Perquè GitHub construeixi i publiqui automàticament el llibre cada vegada que facis `git push`, cal afegir un workflow.

Dins del repositori, crea la ruta:

```
.github/workflows/build-mdbook.yml
```

i afegeix-hi:

```yaml
name: Build and Deploy mdBook

on:
    push:
        branches:
            - main

jobs:
    build-and-deploy:
        runs-on: ubuntu-latest

        steps:
            - name: Checkout repository
                uses: actions/checkout@v4

            - name: Install mdBook
                run: |
                    curl -L https://github.com/rust-lang/mdBook/releases/latest/download/mdbook-linux-amd64.tar.gz -o mdbook.tar.gz
                    tar -xzf mdbook.tar.gz
                    sudo mv mdbook /usr/local/bin/

            - name: Build the book
                run: mdbook build

            - name: Deploy to GitHub Pages
                uses: peaceiris/actions-gh-pages@v4
                with:
                    github_token: ${{ secrets.GITHUB_TOKEN }}
                    publish_dir: ./book
```

Aquest workflow:

- Instal·la **mdBook** al runner d'Ubuntu.
- Genera el llibre en format HTML.
- Publica el contingut generat a la branca `gh-pages`.

---

### 2. Activar GitHub Pages

Un cop creat el workflow:

1. Ves al repositori a GitHub.
2. Fes clic a la pestanya **Settings**.
3. A la barra lateral, selecciona **Pages**.
4. A l'apartat **Build and deployment**, assegura't que la branca seleccionada és `gh-pages`.
5. Desa els canvis si cal.
6. Accedeix a la URL pública que apareix per veure el llibre publicat.

Entra a:

```
Settings → Pages
```

Configura:

- **Source**: selecciona "Deploy from a branch".
- **Branch**: tria `gh-pages`.
- **Folder**: selecciona `/ (root)`.

Això farà que GitHub Pages publiqui el contingut generat pel workflow automàticament.

---

### 3. Accedir al llibre publicat

Quan el workflow hagi finalitzat correctament, el llibre estarà disponible a una URL com:

```
https://<usuari-o-organitzacio>.github.io/<nom-del-repositori>/
```

Exemple:

```
https://carlescanals.github.io/practica-mdbook/
```

---

### 4. Actualitzar el llibre

Cada vegada que facis:

```sh
git add .
git commit -m "Actualització del contingut"
git push
```

GitHub:

- Reconstruirà automàticament el llibre.
- Actualitzarà la versió publicada a GitHub Pages.

