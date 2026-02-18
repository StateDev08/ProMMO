# ProMMO - Advanced MMORPG Plugin für Minecraft

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/prommo/ProMMO)
[![Minecraft](https://img.shields.io/badge/minecraft-1.21.11-green.svg)](https://www.minecraft.net/)
[![Java](https://img.shields.io/badge/Java-21-orange.svg)](https://openjdk.org/projects/jdk/21/)
[![Paper](https://img.shields.io/badge/Paper-1.21.11-blue.svg)](https://papermc.io/)
[![Folia](https://img.shields.io/badge/Folia-Compatible-green.svg)](https://papermc.io/software/folia)
[![License](https://img.shields.io/badge/license-MIT-orange.svg)](LICENSE)

# ProMMO - Pro MMO Paper Plugin

Ein professionelles MMO-Framework für Paper-Server (Minecraft 1.21.1), das klassische Rollenspielelemente mit der modernen Engine verbindet.

## Inhaltsverzeichnis
- [Features](#features)
- [Installation](#installation)
- [Konfiguration](#konfiguration)
- [Systeme](#systeme)
  - [Rassen](#rassen)
  - [Klassen](#klassen)
  - [Berufe](#berufe)
  - [Skills](#skills)
  - [Combat (1.8 Style)](#combat-18-style)
  - [Weltgenerator](#weltgenerator)
- [Befehle & Berechtigungen](#befehle--berechtigungen)
- [Abhängigkeiten](#abhängigkeiten)
- [Entwickler-Informationen](#entwickler-informationen)

---

## Features

- **Multi-Rassen & Klassen-System:** 15 Rassen und 15 Klassen zur Auswahl beim ersten Join.
- **Berufe & Skills:** 8 Berufe und 25 verschiedene Skills für tiefgreifende Charakterentwicklung.
- **Combat 1.8 Emulation:** Deaktivierter Attack-Cooldown und Sweeping-Effekte für das klassische Kampfgefühl.
- **Weltgenerator:** Einzigartiger Generator, der das Terrain-Feeling von Minecraft 1.8 reproduziert und nahezu ALLE modernen Biome (inkl. 1.21 Biome) unterstützt.
    - **Städte & Dörfer:** Automatische Generierung von großen Städten, kleinen Städten und riesigen Dörfern.
    - **NPCs:** Dorfbewohner in Städten weisen Spielern spezielle MMO-Aufgaben und Quests zu.
- **Timber-Funktion:**
    - Erlaube das Fällen ganzer Bäume (inkl. Blätter), wenn während des Abbauens eines Baumstamms die **Sneak-Taste** gedrückt gehalten wird.
- **Gilden & Quests:**
    - **Gilden-System:** Umfassende Gildenverwaltung mit Rängen (Leader, Officer, Member), Gilden-Tresor (`/prommo guild deposit`), Gilden-Chat (`/prommo guild chat`) und Gilden-Logs.
    - **Quests:** Absolviere über 35 verschiedene Quests (z.B. Boss-Jagden, Ressourcen-Sammeln), um XP und Gold zu verdienen.
    - **Tägliche Aufgaben:** Interaktive Village NPCs in Städten bieten nun 5 täglich rotierende Aufgaben aus einem Pool von 10 Spezial-Quests an.
- **Crafting & Workbench:**
    - **ProMMO Werkbank:** Eine spezialisierte Arbeitsstation (Rezept: 4x Eichenholz im Quadrat), die als Hub für alle RPG-Gegenstände dient.
    - **Interaktives Crafting-GUI:** Stelle mächtige Ausrüstung und Survival-Gegenstände direkt über ein intuitives Menü her.
- **Levelsystem:**
    - Globales Charakter-Level mit progressiven XP-Anforderungen.
    - Belohnungen wie zusätzliche Lebenspunkte (+2 HP alle 5 Level) und Skillpunkte (2 SP pro Level-Up).
    - XP-Gewinn durch Kampf, Berufe und Quests.
- **Shopsystem:** Integrierter Shop (`/prommo shop`) basierend auf Vault für den Handel mit Items.
- **Dungeon-Generator:** Erstelle spezialisierte Dungeon-Welten mit Multiverse-Integration (`/prommo dungeon create <name>`).
- **Custom Items & Rezepte:**
    - **Vielseitige Ausrüstung:** Über 30 neue Custom Items und 3 vollständige Sets:
        - **Kupfer-Set:** Einsteiger-Ausrüstung (Level 10).
        - **Smaragd-Set:** Fortgeschrittene Ausrüstung (Level 40).
        - **Obsidian-Set:** High-End-Ausrüstung (Level 60).
    - **Magie-System & Bücher:** Ein brandneues Magiesystem mit sammelbaren Büchern:
        - **Buch des Feuers:** Schieße Feuerbälle.
        - **Buch des Lebens:** Heile dich selbst und erhalte Regeneration.
        - **Buch des Windes:** Erhalte einen Geschwindigkeitsschub und einen Vorwärtssprung.
        - **Buch der Erde:** Erhalte massiven Schutz durch Resistenz und Absorption.
    - **Beschaffung:** Magiebücher können teuer in der **ProMMO Werkbank** hergestellt werden (erfordert Netherite) oder als seltene Beute von **Bossen** in Dungeons fallen gelassen werden.
    - **Magische Artefakte:** Einzigartige Items wie der **Magische Zauberstab**, **Drachen-Essenz**, **Mana-Kristalle** und **Schatten-Juwele**.
    - **Survival-Nahrung:** Gereinigtes Wasser, Reise-Rationen und Energie-Riegel zur Unterstützung des Hunger- und Durst-Systems.
    - **Eigene Crafting-Rezepte:** Alle Items sind über die ProMMO Werkbank oder das mitgelieferte Datapack craftbar.
- **Welt-Ereignisse:** Seltene Ereignisse wie der **Blutmond** oder zufällige Welt-Events (XP-Boost, Gold Rush), die vom `WorldEventManager` gesteuert werden.
- **Ausdauersystem:** Dynamischer Verbrauch beim Rennen und Schwimmen, Regeneration im Stehen/Schleichen, levelbar über den Skill "Ausdauervorrat".
- **Survival-Mechaniken:** Dynamische Hunger-, Durst- und Temperatur-Systeme, die vom Biom und der Ausrüstung beeinflusst werden.
    - **Soziale Features:** Freundes-System (`/prommo friends`) und sicheres Handels-System (`/prommo trade <Spieler>`).
- **Administrations-Interface (Admin GUI):**
    - Verwalte Kernsysteme (Survival, Invasionen) direkt im Spiel.
    - Dynamische Anpassung des Weltgenerators (Noise Scale, Dorf-Dichte).
    - Verfügbar über `/prommo admin` für berechtigte Spieler.
- **MASSIVES SYSTEM-UPDATE (25 FUNKTIONALE SYSTEME):**
    - **Party-System:** Bilde Gruppen und teile XP mit einem **20% Bonus** (`/prommo party`).
    - **Auktionshaus:** Globaler Marktplatz mit GUI zum Kaufen/Verkaufen von Items (`/prommo auction`).
    - **Bank:** Persistentes Lager für Items mit Datenbank-Anbindung (`/prommo bank`).
    - **Mail-System:** Sende Nachrichten an andere Spieler (`/prommo mail`).
    - **Achievements:** Über 50 Meilensteine (z.B. "Dragon Slayer", "Diamond Miner").
    - **Titel-System:** Schalte Titel frei, die als Präfix im Chat erscheinen (`/prommo title`).
    - **Mounts & Pets:** Funktionale Reittiere (Pferde) und Begleiter (`/prommo mount`, `/prommo pet`).
    - **Territorien:** Beanspruche Chunks und schütze dein Land (Gilden-Integration).
    - **Arena:** PvP-Warteschlange für Duelle mit Belohnungen.
    - **Boss-System:** Epische Bosse mit 10x HP und Spezial-Loot (Admin-Spawn).
    - **Reputation:** Ruf-System bei Fraktionen mit Rängen (Neutral bis Ehrwürdig).
    - **Wegpunkte:** Persönliche Schnellreisepunkte mit Teleportation (`/prommo waypoint`).
    - **Kopfgelder:** Setze Goldbelohnungen auf Spieler aus (`/prommo bounty`).
    - **Talentbaum:** Spezialisiere deinen Charakter mit Skillpunkten (`/prommo talent`).
    - **Seasons:** Saisonale Progression mit Punkten und Belohnungen (`/prommo season`).
    - **Matchmaking:** Gruppen-Warteschlangen für Dungeons (`/prommo mm`).
    - **Item-Raritäten:** Farbliche Einstufung von Gewöhnlich bis Legendär.
    - **Sockel-System:** Werte Items mit Edelsteinen auf.
    - **Mehrsprachigkeit:** 100% Lokalisierung aller Texte für EN, DE, ES, FR, IT und RU.
- **Flexible Datenspeicherung:** Unterstützung für SQLite (lokal) und MySQL.
- **Mythic Integration:**
    - **MythicMobs:** Ermöglicht das Spawnen spezialisierter Mobs in Dungeons.
    - **MythicLib (MMOLib):** Synchronisiert ProMMO-Attribute (Stärke, Leben) automatisch mit dem Mythic-Stat-System.
    - **Soft-Depend-Architektur:** Das Plugin bleibt voll funktionsfähig, auch wenn die Mythic-Plugins nicht installiert sind.
- **MMOItems & CoreTools:**
    - **MMOItems:** API-Integration zum Abrufen von hochqualitativen Custom-Items direkt in ProMMO-Menüs (z.B. Werkbank).
    - **CoreTools:** Vorbereitete Integration für systemübergreifende Utilities.

## Installation

1. Lade die `ProMMO.jar` herunter.
2. Schiebe die Datei in deinen `plugins`-Ordner deines Paper 1.21.1 Servers.
3. Starte den Server neu.
4. Konfiguriere die Datenbankverbindung in der `config.yml` (Standard ist SQLite).

## Konfiguration

Die `config.yml` befindet sich im Ordner `plugins/ProMMO/`.

```yaml
storage:
  type: sqlite # sqlite | mysql
  sqlite:
    file: data.db
  mysql:
    host: localhost
    port: 3306
    database: prommo
    user: root
    password: secret
    useSSL: false
locale:
  default: en_US
  enabled:
    - en_US
    - de_DE
    - fr_FR
    - es_ES
    - it_IT
    - ru_RU
firstJoin:
  requireRaceAndClass: true
```

## Systeme

### Rassen
Beim ersten Beitritt muss der Spieler eine der 15 Rassen wählen. Jede Rasse hat spezifische Attribute und Effekte (positiv & negativ):

| Rasse | HP | Schaden | Speed | Besonderheiten & Effekte |
| :--- | :--- | :--- | :--- | :--- |
| Mensch | 20 | x1.0 | 0.2 | Vielseitig, keine permanenten Vor-/Nachteile |
| Elf | 18 | x0.8 | 0.25 | **Speed I**, flink aber zerbrechlich |
| Zwerg | 24 | x1.2 | 0.15 | **Haste I** (unter Y=40), zäh und stark |
| Ork | 22 | x1.5 | 0.18 | **Strength I**, brutal und kraftvoll |
| Untoter | 20 | x1.1 | 0.18 | Unnachgiebig, furchtlos |
| Engel | 20 | x0.9 | 0.22 | Himmlische Präsenz, schnell |
| Dämon | 20 | x1.3 | 0.19 | Höllische Macht |
| Gnom | 16 | x0.7 | 0.28 | Klein, extrem schnell |
| Troll | 26 | x1.2 | 0.14 | Regenerativ, sehr zäh |
| Vampir | 18 | x1.4 | 0.23 | **Sonnenschaden** (brennt bei Tag unter freiem Himmel) |
| Werwolf | 22 | x1.4 | 0.24 | Wilde Bestie, hoher Schaden und Speed |
| Meervolk | 20 | x1.0 | 0.21 | **Wasserreich** (Conduit Power + Dolphin's Grace in Wasser, **Slowness I** an Land) |
| Drakonisch | 28 | x1.6 | 0.16 | Drachenerbe, massiver Schaden |
| Fee | 14 | x0.5 | 0.3 | **Jump Boost II**, winzig und magisch |
| Riese | 40 | x2.0 | 0.1 | **Slowness I**, kolossal und extrem stark |

### Klassen
Die gewählte Klasse gewährt zusätzliche Boni und spezialisierte Effekte:

| Klasse | HP Bonus | DMG Bonus | Mana Bonus | Spezial-Effekte |
| :--- | :--- | :--- | :--- | :--- |
| Krieger | +2 | +20% | 0 | Klassischer Nahkämpfer |
| Magier | 0 | +50% | 50 | **Night Vision**, -10% Nahkampfschaden (Malus) |
| Schurke | 0 | +30% | 20 | **Speed I**, tödlich aus dem Hinterhalt |
| Waldläufer | 0 | +10% | 10 | Präzisionsschütze |
| Priester | 0 | 0% | 60 | Heiler |
| Paladin | +4 | +10% | 30 | Heiliger Krieger |
| Nekromant | 0 | +40% | 70 | Gebieter über den Tod |
| Berserker | 0 | +60% | 0 | **Strength I**, pure Zerstörung |
| Mönch | 0 | +20% | 40 | Ausgeglichen |
| Druide | +2 | +10% | 50 | Wächter der Natur |
| Assassine | 0 | +40% | 15 | Schattenhafter Meuchelmörder |
| Barde | 0 | 0% | 45 | Musikalische Unterstützung |
| Schamane | 0 | +20% | 55 | Geisterbeschwörer |
| Beschwörer | 0 | +30% | 65 | Ruft Diener |
| Ingenieur | 0 | +10% | 25 | Techniker |

### Berufe
Es stehen 8 Berufe zur Verfügung:
`Bergbau, Schmied, Holzfäller, Alchemist, Fischer, Bauer, Baumeister, Jäger`.

Jeder Beruf ermöglicht es, spezifische Skills schneller zu leveln und gewährt Zugang zu besonderen Fähigkeiten.

#### Berufs-Level & Item-Anforderungen
Spieler sammeln Berufs-XP parallel zur Skill-XP. Ein höheres Berufs-Level ist erforderlich, um bessere Ausrüstung zu nutzen.

| Material Tier | Level-Anforderung (Werkzeuge/Waffen) | Level-Anforderung (Rüstung) |
| :--- | :--- | :--- |
| Holz / Leder | 1 | 1 |
| Stein | 5 | - |
| **Kupfer (Custom)** | **10** | **10** |
| Gold | 10 | 15 |
| Kettenrüstung | - | 10 |
| Eisen | 15 | 20 |
| Diamant | 30 | 35 |
| **Smaragd (Custom)** | **40** | **40** |
| Netherite | 50 | 50 |
| **Obsidian (Custom)** | **60** | **60** |

### Skills
Das System umfasst 25 Skills, die durch Aktivitäten in den Berufen oder im Kampf verbessert werden können:

**Progression:**
- **Skill-XP:** Jede Aktion (Abbauen, Jagen, Craften) gewährt XP für den relevanten Skill.
- **Level-Up:** Alle 100 XP steigt ein Skill im Level.
- **Skill-Punkte (SP):** Jeder Level-Aufstieg eines Skills gewährt 1 Skill-Punkt.
- **Upgrades:** Im `/prommo` Menü können SP ausgegeben werden, um Skills gezielt zu verbessern.

**Kategorien & Effekte:**

| Kategorie | Skills | Effekt-Details (pro Level) |
| :--- | :--- | :--- |
| **Kampf** | Stärke, Beweglichkeit, Ausdauer, Kritisch, Lebensraub, Parieren, Bogenschießen, Seelenbindung, Berserkerwut | Parieren (Chance DMG zu halbieren), Seelenbindung (Mana-Schild), Berserkerwut (Bonus DMG bei niedrigen HP) |
| **Magie** | Intelligenz, Mana-Regeneration, Zauberkraft, Magieresistenz | Magieresistenz (-2% Schaden durch Magie) |
| **Utility** | Glück, Eile, Erholung, Schnelligkeit | Haste (Passive Eile-Buffs beim Abbauen) |
| **Berufe** | Doppelter Ertrag, Schnelles Minen, Reparaturglück, Braumeister, Fischerglück, Erntemeister, Bautempo, Monsterjäger, Auto-Schmelzen, Wildwuchs | Auto-Schmelzen (für Miner), Wildwuchs (für Farmer) |
| **Survival** | Wintermantel, Meisterkoch, Ausdauervorrat | Wintermantel (Kälteresistenz), Meisterkoch (Bessere Nahrung), Ausdauervorrat (+10 Max Ausdauer pro Level) |
| **Misc** | Feilschen, Überzeugungskraft, Schleichen, Zähigkeit | Zähigkeit (-1% erlittener Schaden) |

Skills können im `/prommo` Menü eingesehen und gegen Skillpunkte gesteigert werden.

### Combat (1.8 Style)
- **Attack Speed:** Der Cooldown zwischen Angriffen wurde entfernt (`GENERIC_ATTACK_SPEED` auf 1024 gesetzt).
- **Sweeping:** Rundumschläge sind deaktiviert, um präzise Einzelziel-Kämpfe wie in 1.8 zu ermöglichen.

### Weltgenerator
Das Plugin enthält einen stark verbesserten `OldWorldGenerator`, der das Terrain-Feeling von Minecraft 1.8 reproduziert.

**Features des Generators:**
- **Biome-Größe:** Optimierte Noise-Skalierung für extrem große, zusammenhängende Biome.
- **Landmassen-Fokus:** Reduziertes Wasser-Vorkommen für riesige Kontinente.
- **Gezielte Strände:** Strände werden nur noch an echten Übergängen zu Ozeanen generiert.
- **Temperatur-Balancing:** Reduziertes Schnee-Vorkommen durch angepasste Schwellenwerte.
- **Biome-System:** Zufällige Verteilung ALLER Biome basierend auf Temperatur- und Feuchtigkeitsrauschen.
- **Spezielle Vegetation:** Kirschbäume, Mangroven, Riesenpilze, sowie biom-spezifische Blumen.
- **Erz-Cluster:** Klassische Erzverteilung für Diamanten, Gold, Eisen etc.
- **Meereshöhe:** Klassische Wasserlevel (Y=63).

Um ihn für eine Welt zu nutzen, füge dies in deine `bukkit.yml` ein:

```yaml
worlds:
  world_name:
    generator: ProMMO
```

### Custom Items & Rezepte
Das Plugin bietet ein flexibles System für eigene Items und Rezepte.

- **Vordefinierte Items:** Magischer Zauberstab, Zwergen-Axt, Mana-Trank.
- **Rezepte:** Alle Custom Items haben eigene In-Game Rezepte.
- **Datapack-Support:** Einfache Erweiterung über das mitgelieferte `prommo_pack`.
- **Befehl:** `/prommo give <item_id>` für Admins.

### Dungeon-System
Spezialisierter Weltgenerator für unterirdische Abenteuer.
- **Generator-ID:** `ProMMO:dungeon`
- **Dungeon Loot:** Automatische Bestückung von Truhen mit Golderzen, Diamanten, Mana-Tränken und Erfahrung.
- **Gefahren:** Funktionale Monster-Spawner mit Zombies, Skeletten und Spinnen.
- **Dungeon Guide (NPC):** Ein spezialisierter NPC, der Spieler direkt in die Dungeon-Welt teleportiert.
- **Befehle:**
    - `/prommo dungeon create <Name>`: Neue Dungeonwelt erstellen (erfordert Multiverse).
    - `/prommo dungeon npc`: Dungeon Guide NPC am aktuellen Standort spawnen (Admin).

### HUD & Scoreboard
Das Plugin bietet ein dynamisches Informationssystem für Spieler:

- **HUD (Action Bar):** Zeigt permanent das globale Level, Lebenspunkte (HP), Mana, Hunger, Durst und Temperatur an.
- **Scoreboard:** Eine Seitenleiste zeigt wichtige Charakter-Statistiken auf einen Blick:
    - Aktueller Name und globales Level
    - Aktuelle Rasse & Klasse (lokalisiert)
    - Gewählter Beruf & Berufs-Level (lokalisiert)
    - Verfügbare Skillpunkte (SP)
    - Gilden-Zugehörigkeit
    - Menü-Hinweis (`/prommo`)

### Administrations-Werkzeuge
Administratoren verfügen über mächtige Werkzeuge zur Steuerung des Servers:
- **Admin GUI:** Ein interaktives Menü (`/prommo admin`), um Systeme ein-/auszuschalten und Generatoren zu konfigurieren.
- **Spieler-Inspektion:** Einblick in Profile anderer Spieler (`/prommo admin inspect <Spieler>`).
- **Level-Manipulation:** Direktes Setzen von Leveln (`/prommo admin setlevel <Spieler> <Typ> <Level>`).
- **Konfigurations-Reload:** Neuladen der Einstellungen ohne Server-Neustart (`/prommo reload`).

---

## Befehle & Berechtigungen

- `/prommo`: Hauptmenü öffnen.
- `/prommo admin`: Admin GUI öffnen (erfordert `prommo.admin`).
- `/prommo reload`: Konfiguration neu laden (Admin).
- `/prommo guild [invite|join|leave|sethome|home|chat|deposit]`: Gildenverwaltung.
- `/prommo friends [add|remove|list]`: Freundesliste.
- `/prommo trade <Spieler>`: Handeln.
- `/prommo shop`: Shop öffnen.
- `/prommo dungeon create <Name>`: Dungeonwelt erstellen.
- `/prommo dungeon npc`: Dungeon Guide NPC spawnen (Admin).
- `/prommo give <item_id>`: Custom Item erhalten.
- `/prommo party [create|invite|join]`: Partyverwaltung.
- `/prommo auction [sell|list]`: Auktionshaus.
- `/prommo bank`: Persönliche Bank öffnen.
- `/prommo mail [send|list]`: Postfach.
- `/prommo title [set]`: Titel verwalten.
- `/prommo waypoint [set|list|tp]`: Schnellreise.
- `/prommo bounty <Spieler> <Betrag>`: Kopfgeld aussetzen.
- `/prommo mount [summon|despawn]`: Reittiere.
- `/prommo pet [summon|remove]`: Begleiter.
- `/prommo mm`: Matchmaking-Warteschlange beitreten (Dungeon 1).
- `/prommo rep`: Ruf bei Fraktionen einsehen.
- `/prommo talent`: Talentbaum öffnen.
- `/prommo season`: Saison-Menü öffnen.
- `/prommo level`: Eigenen XP-Fortschritt anzeigen.
- `/prommo admin boss <Name>`: Boss am Standort spawnen (Admin).
- `/prommo admin inspect <Spieler>`: Spielerprofil einsehen.
- `/prommo admin setlevel <Spieler> <MAIN|PROFESSION|SKILL> <Level>`: Level setzen.

**Berechtigungen:**
- `prommo.player`: Zugriff auf Basis-Befehle (Standard).
- `prommo.admin`: Zugriff auf Admin-Befehle.

## Abhängigkeiten

Das Plugin erfordert oder unterstützt folgende Plugins:
- **Vault:** Erforderlich für Economy & Shop.
- **LuckPerms:** Berechtigungsverwaltung.
- **Multiverse-Core:** Empfohlen für Dungeon-Welten.
- **PlaceholderAPI:** Platzhalter-Unterstützung.
- **Citizens:** NPC-Integration.
- **WorldEdit / WorldGuard:** Schutz-Tools.
- **MythicMobs / MythicLib / MythicRPG:** Optionale Integration für Custom Mobs und RPG-Stats.

## Entwickler-Informationen

### Java Version
Das Plugin erfordert **Java 21**.

### API Zugriff
Die Kernkomponenten sind über die `ProMMOPlugin` Instanz erreichbar:
- `getProfileService()`: Zugriff auf Spielerdaten.
- `getLocaleManager()`: Zugriff auf Übersetzungen.
- `getStorage()`: Direkter Datenbankzugriff.
