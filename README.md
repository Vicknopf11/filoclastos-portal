# Filoclastos — portale

Sito statico a pagina singola per `filoclastos.it`, l'indice dei progetti
del dominio. Nessuna dipendenza, nessun build step: `index.html` +
`assets/css/main.css`.

Per aggiungere un progetto futuro, copia un blocco `<li class="fascicolo">`
in `index.html` e aggiorna il numero di fascicolo e lo stato
(`stato--attivo` o `stato--dev`).

## Pubblicazione su GitHub Pages

1. Crea un nuovo repository GitHub pubblico, chiamato `filoclastos-portal`.
2. Da questa cartella:

   ```bash
   cd filoclastos-portal
   git init
   git add .
   git commit -m "Portale iniziale"
   git branch -M main
   git remote add origin https://github.com/Vicknopf11/filoclastos-portal.git
   git push -u origin main
   ```

3. Su GitHub: **Settings → Pages** → Source: `Deploy from a branch`,
   branch `main`, cartella `/ (root)`. Sotto **Custom domain**, inserisci
   `filoclastos.it` e salva (il file `CNAME` è già nel repository).
   Spunta **Enforce HTTPS** dopo che il DNS è verificato.

## DNS su Aruba

Questo repository gestisce il **dominio nudo** e `www`. Gli altri
sottodomini (`osservatorio.`, `corrispondente.`, `complottista.`) sono
repository separati con le proprie istruzioni.

**Dominio nudo `filoclastos.it`** — quattro record A verso GitHub Pages:

```
A    @    185.199.108.153
A    @    185.199.109.153
A    @    185.199.110.153
A    @    185.199.111.153
```

**`www.filoclastos.it`** — record CNAME:

```
CNAME    www    Vicknopf11.github.io.
```

Con questi due insieme al Custom domain impostato su GitHub, sia
`filoclastos.it` che `www.filoclastos.it` serviranno il portale.
