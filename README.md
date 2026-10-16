# Semafor (GitHub Pages, dočasná verzia)

Verejná tabuľa so štyrmi farbami. Dáta sú v `state.json` v tomto repozitári.

- **Verejnosť** len pozerá (stránka číta publikovaný `state.json`, obnovuje sa každých 30 s; zmena sa zobrazí do ~1 minúty po uložení).
- **Admin** sa prihlási vložením GitHub tokenu. Posun o jeden krok hore/dole, pridanie, premenovanie a mazanie mien zapisuje
  priamo do `state.json` cez GitHub API (každá zmena = jeden commit).

## Token pre admina

GitHub → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token:

- Repository access: **Only select repositories** → `semafor-pages`
- Permissions → Repository permissions → **Contents: Read and write**
- Expiration: napr. 30 dní

Token sa ukladá len v prehliadači admina (localStorage). Po odhlásení sa zmaže. Kedykoľvek ho možno zrušiť v GitHub nastaveniach.

## Doména

`CNAME` súbor obsahuje `semafor.z3d.sk`. V DNS treba záznam `semafor` typu `CNAME` na `mi-zel.github.io`.
Potom v Settings → Pages zapnúť „Enforce HTTPS" (certifikát vydá GitHub po overení DNS).

## Upozornenie

Repozitár je verejný, preto sú v ňom aj krstné mená detí zo `state.json`. Je to len dočasné riešenie;
trvalá verzia (Node server + Docker) je v súkromnom repozitári `semafor`.
