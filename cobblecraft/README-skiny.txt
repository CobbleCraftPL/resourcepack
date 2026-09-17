skiny — paczka skinow Cobblemon serwera CobbleCraft
====================================================

Ten ZIP jest jednoczesnie RESOURCE PACKIEM (assets/) i DATAPACKIEM (data/).
Wrzuc go w OBA miejsca:
  - serwer:  world/datapacks/          (zeby dzialaly aspekty i komendy)
  - klient:  resourcepacks/            (zeby bylo widac modele)

Wszystkie aspekty maja prefiks "cc_" — nie koliduja z innymi paczkami
skinow, ktore czesto uzywaja nazw typu "halloween" czy "dragon".

Wszystkie skiny sa flagami (flag species feature) z default=false:
NIE spawnuja sie w naturze i nie da sie ich zlapac. Jedyny sposob
zdobycia = komenda.

Kazdy skin wlacza sie tak samo:
     /pokegive <gracz> <pokemon> <aspekt>=true
     /pokeedit <gracz> <slot> <aspekt>=true
Wylaczenie:
     /pokeedit <gracz> <slot> <aspekt>=false
Wersja shiny: doloz shiny=true.


SKINY
-----

 1) cc_halloween         Halloween 2025 Skeleton
    pikachu, raichu, dragonite, umbreon
    Dziala tez z region-bias-alola (Alolan Raichu / Pikachu):
      /pokegive <gracz> raichu cc_halloween=true region-bias-alola=true

 2) cc_fastfood          Armarouge Fastfood (Biggdr)
    armarouge

 3) cc_sugar             Ceruledge Sugar (Biggdr)
    ceruledge

 4) cc_skeleton_overlord Skeleton Overlord Armarouge
    armarouge
    (Armarouge ma dwa skiny — nie wlaczaj obu naraz, wygra overlord)

 5) cc_dragon            Haxorus Dragon line (JuanO_204)
    axew, fraxure, haxorus

 6) cc_spectral          Spectral Garchomp line + mega (JuanO_204)
    gible, gabite, garchomp  (mega forma z Mega Showdown tez ma model)

 7) cc_fnaf1             Midnight Show — FNAF 1 (Darzoth)
    lopunny (Bonnie), delphox (Foxy), ursaring (Freddy), blaziken (Chica)

 8) cc_fnaf2             Midnight Show — FNAF 2 (Darzoth)
    lopunny, delphox, ursaring, blaziken, meowscarada (Puppet)

 9) cc_fnaf2toy          Midnight Show — FNAF 2 Toy (Darzoth)
    lopunny (Toy Bonnie), delphox (Mangle), ursaring (Toy Freddy),
    blaziken (Toy Chica)
    FNAF ma wlasne dzwieki (krzyk, kroki, muzyczka) — sa w paczce.

10) cc_sun               Sun Gods (Zak)
    rayquaza, tyranitar, excadrill, skarmory, gengar

11) cc_summer            Summer (stroje letnie)
    blastoise, dugtrio, gardevoir, lopunny, pikachu, vaporeon

Przyklady:
     /pokegive <gracz> garchomp cc_spectral=true shiny=true
     /pokegive <gracz> delphox cc_fnaf2toy=true
     /pokegive <gracz> rayquaza cc_sun=true
     /pokegive <gracz> vaporeon cc_summer=true

Na jednym pokemonie wlaczaj tylko JEDEN skin. Lopunny, Delphox, Ursaring,
Blaziken, Pikachu i Armarouge maja po kilka skinow — przy kilku naraz
wygrywa ten o wyzszym "order" w resolverze.


LICENCJE
--------
- Biggdr (fastfood, sugar): LICENSE-biggdr.txt — tylko wlasny serwer,
  bez odsprzedazy i redystrybucji.
- Darzoth (FNAF): LICENSE-darzoth.txt — uzycie na JAKIMKOLWIEK serwerze
  (takze darmowym) wymaga wykupionej licencji u autora. Credits:
  CREDITS-fnaf.txt.


JAK ZBUDOWANA JEST PAKA
-----------------------
Zrodla: Desktop\txt\skiny  +  z poprzedniej paczki (Desktop\skiny\CobbleCraft.zip)
tylko: halloween, fastfood, sugar, dragon, spectral.
Komisja ozis (eevee, garbodor, ludicolo, lugia, tyrantrum) NIE jest juz w paczce.
Komunikaty Lootr przeniesione do paczki CobbleCraft (Desktop\txt).

Zmiany wzgledem oryginalow:
- Aspekty przemianowane na cc_*: fnaf1, fnaf2, fnaf2toy, sun,
  skeleton_overlord_armarouge -> cc_skeleton_overlord.
- Pominiete species_additions:
    FNAF: wlaczaly spanie WSZYSTKIM Blazikenom i Delphoxom (nie tylko skinom)
    Skeleton Overlord: dodawaly Armarouge nowa forme (zmiana danych gatunku)
- Sun Gods: stara struktura folderow (bedrock/species, bedrock/models...)
  przeniesiona do bedrock/pokemon/... jak reszta.
- Skeleton Overlord: resolver mial order 0 (tyle co bazowy resolver
  Armarouge — skin mogl sie nie pokazywac) -> 6. rootBone posera wskazywal
  na nieistniejaca kosc -> "armarouge". Usuniete przejscie do walki
  z animacja battle_intro, ktorej nie ma.
- Halloween: poser raichu_alolan_halloween mial literowke "hallowen"
  w 5 animacjach (omdlenie, odrzut, krzyk, ataki) — nie odpalaly sie.
  Usuniety posers/0025_pikachu/pikachu_alolan.json — byl identyczna kopia
  vanillowego posera i niepotrzebnie go przeslanial.
- Spectral Garchomp (+mega): poser szukal animacji "sleep", autor nazwal
  ja "sleep_WIP" — podpieta.

Summer bylo dostarczone jako .bbmodel (zrodla Blockbench). Geometria,
tekstury i animacje wyeksportowane skryptem, ktory na komisji ozis dawal
wynik identyczny z eksportem z Blockbencha (5 modeli, 4269 klatek).
- blastoise, dugtrio, gardevoir, pikachu, vaporeon: zbudowane na
  NIETKNIETYM rigu Cobblemona (wszystkie kosci i pivoty jak w vanilli,
  dolozone tylko akcesoria). Uzywaja vanillowego posera i animacji.
  Wszystkie vanillowe lokatory sa na miejscu.
- lopunny: zbudowany na innym, nowszym rigu (65 kosci z innym pivotem),
  wiec ma WLASNE animacje (summer_lopunny) i wlasny poser.
- Pikachu summer to model meski — samica tez go dostanie.
- Model Pikachu/Dugtrio summer nadpisuje tez warianty (czapki Pikachu,
  Alolan Dugtrio) — z aspektem cc_summer zawsze widac letni model.

Znane, niepoprawione (z oryginalnych paczek, nieszkodliwe):
- spectral_gible: q.look celuje w kosc "head", ktorej model nie ma —
  glowa nie sledzi gracza, Cobblemon to ignoruje.
- spectral_garchomp_mega nie ma kosci hand_right (brak trzymanego
  przedmiotu po prawej).
