# practica-mdbook

## Guia: Crear un mdBook i publicar-lo a GitHub Pages

### 1. Instal·la mdBook

Descarrega i instal·la mdBook executant:

```bash
cargo install mdbook
```
O bé segueix les instruccions oficials: [https://rust-lang.github.io/mdBook/](https://rust-lang.github.io/mdBook/)

### 2. Crea el teu llibre

```bash
mdbook init nom-del-llibre
cd nom-del-llibre
```

### 3. Escriu el contingut

Edita els fitxers Markdown dins la carpeta `src/` del llibre.

### 4. Previsualitza localment

```bash
mdbook serve
```
Obre el navegador a [http://localhost:3000](http://localhost:3000) per veure el llibre.

### 5. Compila el llibre

```bash
mdbook build
```
El resultat es troba a la carpeta `book/`.

### 6. Publica a GitHub Pages

1. Puja el projecte mdBook al teu repositori de GitHub.
2. Ves a la configuració del repositori (Settings > Pages).
3. Selecciona la branca `main` i la carpeta `/book` com a font de GitHub Pages.
4. Desa els canvis i espera uns minuts.
5. Accedeix a l'enllaç que et proporciona GitHub Pages per veure el llibre publicat.

### 7. Recomanacions

- Actualitza el contingut del llibre editant els fitxers Markdown i tornant a executar `mdbook build`.
- Pots personalitzar el tema i la configuració editant el fitxer `book.toml`.
