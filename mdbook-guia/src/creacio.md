## Creació d'un nou mdBook

Ara que ja tens **mdBook** instal·lat, anem a crear el teu primer llibre.

---

## 1. Crear el projecte

Tria una carpeta del teu sistema on vulguis desar el projecte (per exemple, una carpeta `projectes/` o `documents/`).

A la terminal, situa't en aquesta carpeta i executa:

```bash
mdbook init el-meu-llibre
```

A continuació, entra dins la carpeta creada:

```bash
cd el-meu-llibre
```

## 2. Fitxers generats

Després de `mdbook init`, tindràs una estructura semblant a:

```
el-meu-llibre/
├── book.toml
└── src/
    ├── SUMMARY.md
    └── introduccio.md
    ...
```

## 3. Provar que tot funciona

Abans d'editar contingut, val la pena comprovar que el projecte funciona.

Encara dins la carpeta del projecte, executa:

```bash
mdbook serve
```

Si tot va bé, veuràs un missatge semblant a:

```
Serving on http://127.0.0.1:3000
```

Obre aquesta adreça al navegador i podràs veure el teu llibre amb l'estructura inicial.

Per aturar el servidor, torna a la terminal i prem `Ctrl + C`.

---

### `estructura.md`

```markdown
# Estructura d'un projecte mdBook

Un projecte creat amb **mdBook** té una estructura senzilla però molt potent.  
Conèixer-la t'ajudarà a organitzar bé el teu llibre.

---

## 1. Estructura bàsica

La forma bàsica d'un projecte és:

```text
el-meu-llibre/
├── book.toml
└── src/
    ├── SUMMARY.md
    ├── capítol1.md
    ├── capítol2.md
    └── ...
```
```
