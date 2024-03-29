# GraphQL-Bib

- [GraphQL-Bib](#graphql-bib)
    - [Bauen des Projekts:](#bauen-des-projekts)
    - [Starten des Projekts:](#starten-des-projekts)
    - [Abfragen mittels Query:](#abfragen-mittels-query)
    - [Schema:](#schema)
    - [Docker:](#docker)

Dieses Repository dient dem Aufsetzen eines GraphQL Hello-Worlds.

### Bauen des Projekts:
```
gradle build
```

---

### Starten des Projekts:
```
gradle bootRun
```
Sollte der Port bereits belegt sein kann dieser in `src/main/resources/application.properties` geändert werden.

Standardmäßig lautet der Port `8090`.

---

### Abfragen mittels Query:
+ Tools die genutzt werden können:
  + GraphQL Playground (https://github.com/graphql/graphql-playground)
  + Postman (https://www.postman.com/downloads/)
  + GraphiQL (https://github.com/graphql/graphiql)
  

+ Für `graphql-playground` folgenden Link verwenden:

  + http://localhost:8090/graphql

+ `GraphIQL` kann im Web-Browser aufgerufen werden:

  + http://localhost:8090/graphiql

**Test Query**:
```
@Todo: Muss eingefügt werden!!
```

**Ausgabe**: 
```
@Todo: Muss eingefügt werden!!
````

---

### Schema:

Das Schema wird in einer Datei `schema.graphql` gespeichert.
Diese befindet sich im Ordner `src/main/resources`.

---

### Docker:

Die Docker-Images werden durch das Gradle Jib Plugin erstellt.

#### Lokales erstellen eines Docker Images:

**Vorraussetzung**:
+ Docker ist installiert
+ Docker Desktop ist am lausten

```
gradle jibDockerBuild
```

Das Docker Image wird daraufhin gebaut und kann via 
cli gestartet werden.

#### Automatische Docker Image Builds:

Das bauen der Docker Images kann optional über eine 
GitHub Action erfolgen. 
Hierbei wird ein Image erstellt und automatisch in die 
GitHub Registry gepusht.

#### Starten des Docker Images:

Das Docker Image kann über die Compose Datei gestartet werden.

Hier für folgenden Befehl im Ordner der Datei (/deploy) ausführen:

```
docker-compose up
```
