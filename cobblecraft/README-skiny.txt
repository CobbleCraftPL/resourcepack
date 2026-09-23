skiny — paczka skinow Cobblemon serwera CobbleCraft
====================================================

Skiny sa rozdzielone na dwa pliki:
  - CobbleCraft.zip  = CLIENT SIDE: resource pack serwera (resource-pack= w
                       server.properties). Modele, tekstury, animacje, dzwieki
                       i nazwy przedmiotow skinow (assets/).
  - skiny.zip        = SERVER SIDE: datapack do world/datapacks/. Definicje
                       aspektow cc_* (data/), bez nich /pokegive ich nie zna.
Po zmianie skinow podmien OBA pliki.

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

12) cc_ozis              Event (komisja ozis, ManiquesitoJR)
    garbodor, ludicolo, lugia, tyrantrum
    Czyste remodele na rigu Cobblemona - bez wlasnych poserow, dziedzicza
    vanillowe animacje. Tyrantrum: siedzenie przednie jak w Cobblemonie 1.8.1.
    Garbodor byl robiony pod rig 1.7.3 (w 1.8.1 doszly peleryna/uszy) -
    animacje z 1.8.1 dzialaja, ale moga wygladac troche inaczej.

Przyklady:
     /pokegive <gracz> garchomp cc_spectral=true shiny=true
     /pokegive <gracz> delphox cc_fnaf2toy=true
     /pokegive <gracz> rayquaza cc_sun=true
     /pokegive <gracz> vaporeon cc_summer=true

Na jednym pokemonie wlaczaj tylko JEDEN skin. Lopunny, Delphox, Ursaring,
Blaziken, Pikachu i Armarouge maja po kilka skinow — przy kilku naraz
wygrywa ten o wyzszym "order" w resolverze.


NAZWY SKINOW I PRZEDMIOTY (mod cobblecraftadditions)
----------------------------------------------------
Skin mozna dac na dwa sposoby:
  1) komenda z aspektem motywu (jak wyzej):  /pokegive <gracz> rayquaza cc_sun=true
  2) przedmiot kosmetyku zakladany pokemonowi (kolo interakcji -> "Change
     cosmetic item"). Przedmiot (cobblecraftadditions:cosmetic_common/rare/epic/
     mythic/legendary) trzyma tekst <gatunek>-<aspekt>, np. "rayquaza-cc_sun".
     Mod (wersja z 2026-09-23) nadaje aspekt cc_sun TYLKO gdy pokemon jest tego
     gatunku - na innym przedmiot nic nie robi. Gatunek to id Cobblemona bez formy
     (Alolan Raichu to "raichu").
Dodatkowe aspekty dla osobnych przedmiotow:
  cc_halloween_alolan  Szkielet Alolan Raichu (tylko forma Alolan)
  cc_fnaf1_golden      Golden Freddy (model FNAF1 ze zlota tekstura shiny)

Nazwa/opis przedmiotu: assets/skiny/lang/en_us.json + pl_pl.json (identyczne, po
polsku), klucze cobblecraftadditions.skin.<pokemon>-<aspekt>.name/.lore,
formatowanie MiniMessage. Nazwa BEZ koloru - kolor nadaje rzadkosc przedmiotu.
43 skiny. Lista z rzadkosciami i komendami /give: przedmioty-skinow.txt i .csv
(obok paczki w Desktop\txt).


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
Z komisji ozis wracaja garbodor, ludicolo, lugia, tyrantrum (Eevee NIE).
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

Summer bylo dostarczone jako .bbmodel (zrodla Blockbench). Geometria i tekstury
wyeksportowane skryptem, ktory na komisji ozis dawal wynik identyczny z eksportem
z Blockbencha (5 modeli, 4269 klatek).
- Wszystkie 6 modeli siedzi na NIETKNIETYM rigu Cobblemona 1.8.1 (komplet kosci
  i pivotow jak w vanilli, dolozone tylko akcesoria), wiec uzywaja vanillowych
  poserow i animacji. Wszystkie vanillowe lokatory sa na miejscu.
- Gardevoir (48) i Lopunny (12) mialy plaskie "kartki" (kwiatki, listki) z UV
  ustawianym per scianka. Cobblemon czyta TYLKO box UV — przez to paczka w ogole
  sie nie wczytywala ("Unable to load model"). Piksele tych kartek sa przeniesione
  do paska doklejonego na dole tekstury i przepisane na box UV. Wyglad bez zmian.
- Pikachu summer to model meski — samica tez go dostanie.
- Model Pikachu/Dugtrio summer nadpisuje tez warianty (czapki Pikachu,
  Alolan Dugtrio) — z aspektem cc_summer zawsze widac letni model.

Znane, niepoprawione (z oryginalnych paczek, nieszkodliwe):
- spectral_gible: q.look celuje w kosc "head", ktorej model nie ma —
  glowa nie sledzi gracza, Cobblemon to ignoruje.
- spectral_garchomp_mega nie ma kosci hand_right (brak trzymanego
  przedmiotu po prawej).
