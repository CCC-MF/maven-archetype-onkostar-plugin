# Maven Archetype 'onkostar-plugin'

Dieses Projekt enthält einen Maven Archetype für Onkostar plugins.

## Eigenschaften der erstellten Plugins

* Es wird Java 11 verwendet
* Die erstellte POM Datei beinhaltet initiale Spring-, Logging- und Testabhängigkeiten.
* Die Onkostar-API wird nicht mitgeliefert.
  Es wird davon ausgegangen, dass die passende JAR-Datei in das erstellte Verzeichnis `libs` kopiert wird. 
* Das Plugin enthält eine Vorlage für eine Pluginklasse mit einigen Beschreibungen.
* Die Pluginklasse wird in der Datei `moduleContext.xml` mit korrektem Paketnamen verwendet.
* Die minimale Version der Onkostar-API wird entsprechend der Vorgaben in der Datei `onkostar-config.properties` gesetzt.

## Verwendung des Maven Archetypes

Vor Verwendung muss das Projekt gebaut und in das lokale Maven Repository installiert werden.

Installation Linux und macOS

```
./mvnw install
```

Installation Windows

```
mvnw.exe install
```

Im Anschluss kann es zum Erstellen einer Pluginvorlage verwendet werden.

```
mvn archetype:generate \
    -DarchetypeGroupId=de.ukw.onkostar \
    -DarchetypeArtifactId=maven-archetype-onkostar-plugin \
    -DarchetypeVersion=1.0.0 \
    -DgroupId=org.example \
    -DartifactId=my-plugin \
    -Dversion=1.0.0 \
    -DonkostarVersion=2.8.3 \
    -Dpackage=org.example.myplugin
```

Dabei sollen die Werte für die folgenden Parameter auf einen eigenen Wert geändert werden:

* `groupId`: GroupID des zu erstellenden Plugins, z.B. entsprechend der Web-Adresse der Organisation gewählt
* `artifctId`: ArtifactID und damit Name des Plugins
* `version`: Erste Version des zu erstellenden Plugins. z.B. `1.0.0`
* `onkostarVersion`: Überschreibt die zu verwendende Version der Onkostar-API. Standardwert: `2.11.1.3` 
* `package`: Überschreibt den verwendeten Java-Paketnamen. Standardwert: `package`

### Weitere Informationen

Weitere Informationen sind im [Confluence von IT-Choice](https://confluence.it-choice.de/display/KBOSTARAPI/Erstellen+eines+Onkostar-Plugins+mit+Maven) verfügbar.