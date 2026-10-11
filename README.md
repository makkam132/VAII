# KitchenCraft – Správa receptov a nákupov

Matej Keblušek
5ZYI32

## Stručný opis projektu
Aplikácia **KitchenCraft** slúži na ukladanie receptov, ich kategórií a plánovanie nákupov surovín. Umožňuje používateľom spravovať vlastné recepty a vygenerovať súhrnný nákupný zoznam pre vybrané jedlá.

## Role v projekte
* **Návštevník:** Prehliadanie verejných receptov a vyhľadávanie.
* **Registrovaný používateľ:** Vytváranie, úprava a mazanie vlastných receptov (CRUD), nahrávanie fotiek, tvorba nákupného zoznamu.
* **Správca:** Moderovanie obsahu a používateľov, správa globálneho zoznamu ingrediencií.

## Prípady použitia podľa rolí
* **Návštevník:** Vyhľadanie receptu, zobrazenie detailu, registrácia.
* **Registrovaný používateľ:** Prihlásenie, pridanie/úprava receptu s fotkou a ingredienciami, vygenerovanie nákupného zoznamu.
* **Správca:** Mazanie nevhodných receptov, úprava ingrediencií.

## Plánované entity
* **User:** `id`, `username`, `email`, `password_hash`, `role`.
* **Recipe:** `id`, `user_id`, `title`, `instructions`, `prep_time`, `image_path`.
* **Ingredient:** `id`, `name`, `default_unit`.
* **RecipeIngredient (M:N):** `id`, `recipe_id`, `ingredient_id`, `amount`, `unit`.

## Vzťahy medzi entitami
* **User – Recipe (1:N):** Používateľ môže vytvoriť viacero receptov.
* **Recipe – Ingredient (M:N):** Recept obsahuje viacero ingrediencií a ingrediencia sa používa vo viacerých receptoch (dekompozícia cez `RecipeIngredient`).

## Hlavné stránky aplikácie
1. **Domovská stránka:** Prehľad najnovších receptov.
2. **Katalóg receptov:** Zoznam s filtrovaním podľa kategórií.
3. **Detail receptu:** Zobrazenie postupu, ingrediencií a fotky.
4. **Pridanie / úprava receptu:** Formulár s pridávaním ingrediencií a uploadom obrázka.
5. **Prihlásenie a registrácia:** Formuláre na autentifikáciu.

## Rozdelenie funkcionality
* **Základné funkcie:** Prihlasovanie a roly, CRUD pre recepty a ingrediencie, upload fotiek, 2x AJAX (filtrovanie, dynamický formulár ingrediencií), validácia vstupov, responzívny dizajn.
* **Rozširujúce funkcie:** Export nákupného zoznamu do PDF, hodnotenie receptov, režim varenia pre mobily.