# Instal·lació de mdBook

Abans de poder utilitzar **mdBook**, cal instal·lar-lo al teu sistema.  
mdBook es distribueix com una eina de línia de comandes que s'instal·la amb **cargo**, el gestor de paquets de Rust.

---

## 1. Instal·lar Rust i cargo

Si encara no tens **Rust** instal·lat, el més senzill és utilitzar l'script oficial d'instal·lació.

A la terminal, executa:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Quan acabi, tanca la terminal i obre'n una de nova, o bé carrega l'entorn amb:

```bash
source $HOME/.cargo/env
```

Ara comprova que tens Rust i cargo instal·lats:

```bash
rustc --version
cargo --version
```

## 2. Instal·lar mdBook

Amb cargo disponible, ja pots instal·lar mdBook:

```bash
cargo install mdbook
```

## 3. Problemes habituals

Alguns errors típics que et pots trobar:

- **Comanda no trobada (`cargo: command not found`)**  
    Vol dir que Rust/cargo no s'han instal·lat correctament o que no tens el PATH actualitzat.  
    Torna a executar:

    ```bash
    source $HOME/.cargo/env
    ```

- **`mdbook: command not found` després d'instal·lar-lo**  
    Pot ser pel mateix motiu: el PATH encara no té la carpeta de `cargo/bin`.  
    Torna a obrir la terminal o utilitza la comanda anterior.
