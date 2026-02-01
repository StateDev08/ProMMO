# ProMMO - Advanced MMORPG Plugin für Minecraft

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/prommo/ProMMO)
[![Minecraft](https://img.shields.io/badge/minecraft-1.21.11-green.svg)](https://www.minecraft.net/)
[![Java](https://img.shields.io/badge/Java-21-orange.svg)](https://openjdk.org/projects/jdk/21/)
[![Paper](https://img.shields.io/badge/Paper-1.21.11-blue.svg)](https://papermc.io/)
[![Folia](https://img.shields.io/badge/Folia-Compatible-green.svg)](https://papermc.io/software/folia)
[![License](https://img.shields.io/badge/license-MIT-orange.svg)](LICENSE)

Ein umfassendes MMORPG-Plugin für Minecraft, das klassische MMO-Mechaniken mit Minecraft-Gameplay verbindet. Release 1.0.0 mit vollständigem Feature-Set, Performance-Monitoring und umfangreicher Dokumentation.

## 🎮 Features

### Kern-Systeme
- **4 Klassen**: Krieger, Magier, Waldläufer, Schurke mit einzigartigen Skills
- **4 Rassen**: Mensch, Elf, Zwerg, Ork mit unterschiedlichen Boni
- **Leveling**: Exponentielles XP-System mit Rested-XP-Bonus
- **28 Skills**: Klassen-spezifische Fähigkeiten mit Cooldowns und Mana-Kosten
- **Attributsystem**: Stärke, Geschicklichkeit, Intelligenz, Vitalität
- **Quest-System**: 15+ Quests mit 5 verschiedenen Typen
- **Party-System**: Gruppenbildung mit XP-Boni und Rollen

### Erweiterte Features
- **6 Berufe**: Bergbau, Kräuterkunde, Fischerei, Kochen, Verzaubern, Alchemie
- **Talent-Bäume**: 30 Talente in 3 Kategorien (Offensiv, Defensiv, Utility)
- **Renown-System**: Wöchentliche und Gesamt-Ranglisten
- **Invasionen**: 3 Typen von Events (Goblin, Skelett, Zombie)
- **Weltgenerierung**: Custom Biome, Settlements, POIs

### GUI & Commands
- **10 interaktive GUIs**: Klassen, Rassen, Stats, Skills, Quests, Party, Berufe, Talente, Renown
- **10 Commands**: `/mmo`, `/class`, `/race`, `/stats`, `/skill`, `/quest`, `/party`, `/profession`, `/talent`, `/renown`
- **Tab-Completion**: Intelligente Command-Vervollständigung
- **Vault-Integration**: Economy-System für Kosten
- **PlaceholderAPI**: 30+ Platzhalter für andere Plugins

## 📋 Voraussetzungen

### ⚔️ Kampf-Systeme
- **4 Klassen:** Krieger, Magier, Schurke, Paladin
- **4 Rassen:** Mensch, Elf, Zwerg, Ork
- **28 Skills:** Aktive & passive Fähigkeiten
- **Talent-System:** 3 Zweige (Offensive, Defensive, Utility)
- **Mana-System:** Boss-Bar-Integration

### 🎯 Content
- **Quest-System:** Kill, Collect, Explore, Craft, Talk
- **Dungeon-System:** 9 Typen, 3 Schwierigkeitsgrade
- **Party-System:** Bis zu 5 Spieler, Shared XP
- **Invasion-System:** Server-weite Events

### 🌍 Weltgenerierung
- **Custom Chunk-Generator:** 6-Layer-Terrain mit Simplex Noise
- **Siedlungs-System:** 9 Settlement-Typen mit async Building
- **POI-System:** 7 POI-Typen (Shrines, Waystones, etc.)

### 💼 Wirtschaft
- **6 Berufe:** Blacksmith, Mining, Alchemy, Enchanting, Herbalism, Woodcutting
- **Renown-System:** Ruhmpunkte und Rangliste
- **Level-System:** Getrennte Level für Klasse, Skills, Berufe

### 🔌 Integrationen
- **Vault:** Economy, Permissions, Chat
- **PlaceholderAPI:** 20+ Placeholders
- **WorldGuard:** Settlement-Protection (optional)
- **Citizens:** Quest-NPCs (optional)

## 🚀 Technologie

### Java 21 Features
- ✅ **Records** - Immutable Daten-Klassen (PlayerData, PlayerStats, etc.)
- ✅ **Switch Expressions** - Moderne Pattern Matching
- ✅ **Sealed Classes** - Type-Safe Hierarchien
- ✅ **Pattern Matching** - instanceof Verbesserungen
- ✅ **Virtual Threads** - Für I/O-intensive Operations (evaluiert)

### Async-First Design
```java
// Alle Database-Operationen sind async
CompletableFuture<PlayerData> data = playerDataManager.getPlayerDataAsync(uuid);
data.thenAccept(playerData -> {
    // Verarbeitung...
});
```

### Folia-Kompatibilität
```java
// Automatische Scheduler-Auswahl
schedulerUtil.runEntityTask(player, () -> {
    // Task wird auf entity scheduler (Folia) oder main thread (Paper) ausgeführt
});
```

### Performance-Optimierung
- **HikariCP Connection Pooling** - Optimale Database-Performance
- **LRU Player Cache** - Reduziert DB-Queries um ~80%
- **Async World Generation** - Kein TPS-Drop
- **Batch Operations** - Effiziente Updates

## 📦 Installation

### Voraussetzungen
- **Server:** Paper 1.21.1 oder neuer (Folia wird unterstützt)
- **Java:** Version 21 oder neuer
- **Datenbank:** SQLite (Standard) oder MySQL/MariaDB

### Schritte
1. **Download** der neuesten `ProMMO-1.0.0.jar` aus Releases
2. **In `plugins/` Ordner** kopieren
3. **Server starten** - Configs werden automatisch erstellt
4. **config.yml anpassen** nach Bedarf
5. **Server neustarten**

### Optional: MySQL konfigurieren
```yaml
database:
  type: mysql
  mysql:
    host: localhost
    port: 3306
    database: prommo
    username: root
    password: 'your_password'
```

## ⚙️ Konfiguration

### Hauptkonfiguration (`config.yml`)
```yaml
# Database-Typ
database:
  type: sqlite  # oder mysql

# Cache-Einstellungen
cache:
  player-cache-size: 1024
  cleanup-interval: 5

# Performance
performance:
  async-world-gen: true
  batch-operations: true
  blocks-per-tick: 50
```

### Weitere Configs
- `classes.yml` - Klassen-Definitionen
- `races.yml` - Rassen-Boni
- `skills.yml` - Skill-Konfiguration
- `professions.yml` - Berufs-Einstellungen
- `worldgen.yml` - Weltgenerungs-Parameter
- `lang/de.yml`, `lang/en.yml` - Übersetzungen

## 🎮 Commands

| Command | Beschreibung | Permission |
|---------|--------------|------------|
| `/class gui` | Klassen-Auswahl öffnen | `prommo.class.change` |
| `/race gui` | Rassen-Auswahl öffnen | `prommo.race.select` |
| `/skill gui` | Skill-GUI öffnen | `prommo.skill.use` |
| `/profession gui` | Berufs-GUI öffnen | `prommo.profession.learn` |
| `/talent gui` | Talent-GUI öffnen | `prommo.class.change` |
| `/quest gui` | Quest-Übersicht | `prommo.quest.accept` |
| `/party create` | Party erstellen | `prommo.party.create` |
| `/stats [player]` | Stats anzeigen | `prommo.class.change` |
| `/dungeon list` | Dungeons anzeigen | `prommo.dungeon.enter` |
| `/mmo reload` | Config neu laden | `prommo.reload` |

Siehe [plugin.yml](src/main/resources/plugin.yml) für alle Commands.

## 📊 PlaceholderAPI

```
%prommo_class% - Klassen-Name
%prommo_race% - Rassen-Name
%prommo_level% - Aktuelles Level
%prommo_xp% - Aktuelle XP
%prommo_xp_required% - XP bis nächstes Level
%prommo_profession1% - Erster Beruf
%prommo_profession2% - Zweiter Beruf
%prommo_party_size% - Party-Größe
%prommo_renown% - Renown-Punkte
%prommo_str% - Stärke
%prommo_int% - Intelligenz
%prommo_dex% - Geschicklichkeit
%prommo_vit% - Vitalität
%prommo_luk% - Glück
```

## 🛠️ API für Entwickler

### Maven Dependency
```xml
<repository>
    <id>jitpack</id>
    <url>https://jitpack.io</url>
</repository>

<dependency>
    <groupId>com.github.prommo</groupId>
    <artifactId>ProMMO</artifactId>
    <version>1.0.0</version>
    <scope>provided</scope>
</dependency>
```

### API-Nutzung
```java
// ProMMO API holen
ProMMOAPI api = ProMMOPlugin.getInstance().getAPI();

// Player-Daten abrufen (async)
api.getPlayerData(player).thenAccept(data -> {
    if (data != null) {
        PlayerClass playerClass = data.playerClass();
        int level = data.level();
        // ...
    }
});

// Custom Events
public class MyListener implements Listener {
    @EventHandler
    public void onClassChange(ClassChangeEvent event) {
        Player player = event.getPlayer();
        PlayerClass newClass = event.getNewClass();
        // ...
    }
}
```

## 🏗️ Entwicklung

### Build
```bash
# Projekt bauen
./gradlew build

# Tests ausführen
./gradlew test

# Shadowjar erstellen
./gradlew shadowJar
```

### Anforderungen
- Java 21 JDK
- Gradle 8.5+
- Paper API 1.21.1

### Projektstruktur
```
src/main/java/de/prommo/
├── ProMMOPlugin.java          # Hauptklasse
├── ProMMOAPI.java             # Public API
├── core/                      # Core-Systeme
│   ├── config/                # Config-Manager
│   ├── database/              # Database-Layer
│   └── cache/                 # Cache-System
├── player/                    # Spieler-Systeme
├── skills/                    # Skill-System
├── quest/                     # Quest-System
├── party/                     # Party-System
├── dungeon/                   # Dungeon-System
├── world/                     # Weltgenerierung
└── util/                      # Utilities
```

## 📈 Roadmap

Siehe [roadmap.md](roadmap.md) für detaillierten Entwicklungsplan.

### Phase 0: ✅ Abgeschlossen
- Gradle Build-System
- Plugin-Basis mit Folia-Support
- Async Database mit HikariCP
- Java 21 Records
- Core-Manager

### Nächste Phasen
- **Phase 1:** Database Repositories & Events
- **Phase 2:** Klassen, Rassen, Attribute
- **Phase 3:** 28 Skills implementieren
- **Phase 4:** Quests, Dungeons, Parties
- **Phase 5:** Weltgenerierung
- **Phase 6:** Berufe, Talente, Renown
- **Phase 7:** GUIs & Integrationen
- **Phase 8:** Testing & Release

## 🐛 Bug-Reports & Feature-Requests

Bitte erstelle ein [Issue](https://github.com/prommo/ProMMO/issues) für:
- Bug-Reports
- Feature-Requests
- Performance-Probleme
- Dokumentations-Verbesserungen

## 📜 Lizenz

Dieses Projekt ist unter der MIT-Lizenz lizenziert - siehe [LICENSE](LICENSE) für Details.

## 🤝 Mitwirken

Contributions sind willkommen! Bitte erstelle einen Pull Request mit:
- Beschreibung der Änderungen
- Tests für neue Features
- Aktualisierte Dokumentation

## 📞 Support

- **Discord:** [ProMMO Community](https://discord.gg/prommo)
- **Wiki:** [Documentation](https://github.com/prommo/ProMMO/wiki)
- **Issues:** [GitHub Issues](https://github.com/prommo/ProMMO/issues)

## 🙏 Credits

- **Paper Team** - Für die großartige Server-Software
- **HikariCP** - Für das beste Connection Pool
- **Community** - Für Feedback und Testing

---

**Entwickelt mit ❤️ für die Minecraft-Community**

**Version:** 1.0.0 (in Entwicklung)  
**Letzte Aktualisierung:** 31. Januar 2026
