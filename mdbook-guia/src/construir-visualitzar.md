## Construir i visualitzar el llibre

Un cop tinguis creada l’estructura del projecte mdBook, pots generar i visualitzar el llibre utilitzant les eines incloses a mdBook.

### Construir el llibre

Per generar la versió HTML del llibre, executa:

```bash
mdbook build
```

Aquest comandament crearà una carpeta de sortida (per defecte `book/`) amb els fitxers HTML generats:

```text
projecte/
├── book.toml
├── src/
└── book/
    ├── index.html
    ├── css/
    ├── js/
    └── ...
```

Aquesta carpeta conté el llibre preparat per publicar-lo, per exemple, a GitHub Pages.

### Visualitzar el llibre localment

Per veure el llibre en el teu navegador mentre el desenvolupes, utilitza:

```bash
mdbook serve
```

Aquest comandament:

- construeix el llibre
- crea un servidor web local
- actualitza automàticament la pàgina quan facis canvis

Una vegada en execució, obre el navegador i ves a:

```
http://localhost:3000
```

Cada vegada que modifiquis un fitxer `.md`, la pàgina es refrescarà automàticament.
