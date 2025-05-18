---
title: Info
layout: page
permalink: /info
store: false
---

{%- assign utils = false -%}
{%- assign lootboxes = false -%}
{%- assign puppeteer = false -%}
{%- for mod in site.data.modlist -%}
    {%- case mod.name -%}
        {%- when 'ToolkitUtils' %}
            {%- assign utils = true -%}
        {%- when 'ToolkitUtils - Testing' -%}
            {%- assign utils = true -%}
        {%- when 'Puppeteer' -%}
            {%- assign puppeteer = true -%}
        {%- when 'TwitchToolkit - Lootboxes' -%}
            {%- assign lootboxes = true -%}
    {%- endcase -%}
{%- endfor -%}


{%- assign bal = '!bal' -%}
{%- assign buy = '!buy' -%}
{%- for command in site.data.commands -%}
    {%- if command.data.isBal -%}
        {%- assign bal = command.usage -%}
        {%- continue -%}
    {%- endif -%}

    {%- if command.data.isBuy -%}
        {%- assign buy = command.usage -%}
        {%- continue -%}
    {%- endif -%}
{%- endfor -%}

# Bienvenue

Bienvenue sur le stream d'[{{ site.data.social.twitch }}](https://twitch.tv/{{ site.data.social.twitch }}).
Le Stream utilise le mod
[Twitch Toolkit](https://steamcommunity.com/sharedfiles/filedetails/?id=1718525787) qui propose une expérienceinteractive..
Il y a beaucoup de choses dans ce mod qui peuvent sembler compliquées, même pour les utilisateurs expérimentés, mais ce petit guide va t'aider à t'y retrouver.

## Qu'est ce que Twitch Toolkit?

Twitch Toolkit est un mod créé par hodlhodl qui permet aux spectateurs d’interagir avec le jeu de plusieurs façons.
La plus connue est sa [store]({{- "/" | relative_url -}}), qui permet d’acheter différents éléments choisis par le streamer.
Selon l’achat, ces éléments apparaissent dans le jeu ou influencent le déroulement de la partie d'une manière ou d'une autre.
Une autre façon pour les spectateurs d’interagir est via les sondages proposés par le mod.
Les choix dans ces sondages dépendent fortement des options activées dans le mod.
## Que sont les pièces (Coins) ?

Les pièces sont la monnaie utilisée par le mod. Tu peux voir ton solde en utilisant la commande `{{ bal }}` command. 

{% if utils == true %}
You'll notice the balance command may have some new emojis. If that's the case, here is an overview
of the emojis as follows:

- 💰 represents the amount of coins you current have.
- ⚖ represents your current karma.
- 📈 represents the amount of coins you gain everytime the mod awards coins.
- 📉 represents the amount of coins you lose everytime to mod awards coins.

{% endif %}


{%- if lootboxes == true -%}
You'll also notice that you'll get a message from the bot about a lootbox. You can open this lootbox
by using the `!openlootbox` command, as well as check the number of lootboxes you have with `!lootboxes`.
You'll always get a new lootbox everyday.
{%- endif -%}


<br/>
## Qu'est ce que le Karme?

Le karma est un système intégré au mod qui vise à limiter la quantité d’événements négatifs qu’un spectateur peut acheter en même temps.
Ce système fonctionne en modifiant directement la quantité de pièces que les spectateurs reçoivent à chaque distribution automatique de pièces par le mod.
Autrement dit, plus ton karma est bas, moins tu gagnes de pièces.
L’objectif est de répartir les événements négatifs dans le temps, afin que la colonie puisse se remettre entre deux attaques ou malus.

## Comment utiliser Twitch Toolkit ?

u peux utiliser Twitch Toolkit de plusieurs façons — la principale est via ses
[commands]({{- "/commands" | relative_url -}}). La commande la plus importante est `{{- buy -}}`
, qui permet d’acheter des objets ou événements dans la boutique du mod.
Parmi les autres commandes utiles, il y a `!mypawn`, qui te permet de consulter différentes informations sur ton colon (le personnage que tu contrôles). Nous ne couvrirons pas ici toutes les commandes, mais en général, elles sont assez explicites ou bien décrites sur la page des  [commands]({{- "/commands" | relative_url -}}).


{%- if puppeteer -%}
<br/>
## What is Puppeteer?

[Puppeteer](https://steamcommunity.com/sharedfiles/filedetails/?id=2057192142) is a mod by Brrainz that
allows viewers to directly control their pawns, and even view a number of information about your pawn in
a graphical way. It also redirects some of the responses from Twitch Toolkit to its website to clean up
chat a bit. So, if you're logged into Puppeeter and you're wondering why the bot isn't responding to you,
you should check the `TT` tab on the website first.
{%- endif -%}
