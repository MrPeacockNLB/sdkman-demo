# sdkman-demo

In dem Repo zeige ich den Umgang mit SDKMAN in GitPod

# Print Version

```bash
$ sdk versions

SDKMAN 5.16.0
```

# Let's switch to terminal

Wir öffnen folgenden Link [workspaces](https://gitpod.io/workspaces) und kopieren den SSH Zugang per Accesstoken.

![](/assets/screenshot.png)

Nachdem wir nun das Kommando kopiert haben, können wir uns mit dem Terminalemulator unser Wahl mit dem GitPod Workspace verbinden.

```
ssh 'mrpeacocknlb-sdkmandemo-8gfjnptonye#8-Y67ATtxhKPoLG9pTmpUyllpEizv7Ae@mrpeacocknlb-sdkmandemo-8gfjnptonye.ssh.ws-eu69.gitpod.io'
```

# Welche Java Version läuft gerade?

```
$ java -version
Picked up JAVA_TOOL_OPTIONS:  -Xmx3489m
openjdk version "11.0.16" 2022-07-19 LTS
OpenJDK Runtime Environment Zulu11.58+15-CA (build 11.0.16+8-LTS)
OpenJDK 64-Bit Server VM Zulu11.58+15-CA (build 11.0.16+8-LTS, mixed mode)
```

Ups das Feature XY wird ja von der LTS Version 11 noch nicht unterstützt!

# Welche Distributionen und Versionen stehen uns zur Verfügung?

Mit `sdk list java` können wir uns die aktuelle Liste der zur Verfügung stehenden Java Versionen der verschiedenen Distributioen anzeigen lassen:

```
================================================================================
Available Java Versions for Linux 64bit
================================================================================
 Vendor        | Use | Version      | Dist    | Status     | Identifier
--------------------------------------------------------------------------------
 Corretto      |     | 19           | amzn    |            | 19-amzn
               |     | 17.0.4       | amzn    |            | 17.0.4-amzn
               |     | 17.0.0.35.1  | amzn    |            | 17.0.0.35.1-amzn
               |     | 11.0.16      | amzn    |            | 11.0.16-amzn
               |     | 11.0.12.7.1  | amzn    |            | 11.0.12.7.1-amzn
               |     | 8.0.342      | amzn    |            | 8.0.342-amzn
...
```

# Wie kann ich nun eine ausgewählte Distribution nutzen?

Am einfachsten geht es über die Autovervollständigung. Geben wir `sdk install java` ein und drücken die `TAB`-Taste, dann werden uns auch alle Varianten angezeigt. Wir nehmen hier mal eine schnell VM von Zulu in diesem Beispiel. Aktuell ist **19-zulu** die letzte Verision die angeboten wird.

```
sdk install java 19-zulu
```

Die anschließende Frage

```
Do you want java 19-zulu to be set as default? (Y/n):
```

beantworten wir mit Enter und setzen die neue Version als Default. Überprüfen wir nun kurz die Version von Java noch...

```
$ java -version
Picked up JAVA_TOOL_OPTIONS:  -Xmx3489m
openjdk version "19" 2022-09-20
OpenJDK Runtime Environment Zulu19.28+81-CA (build 19+36)
OpenJDK 64-Bit Server VM Zulu19.28+81-CA (build 19+36, mixed mode, sharing
```

# Anzeigen der aktuellen installierten Versionen

Die aktuell installierten Versionen kann man natürlich auch mit `sdk surrent` anzeigen lassen.

```
$ sdk c

Using:

gradle: 7.5.1
java: 11.0.16.fx-zulu
maven: 3.8.6
```

# Shortcuts der Befehle anwenden

Das Programm `sdk` versteht auch gekürzte Befehle. Gibt nur `sdk` ein, dann erhält man die Hilfe und hier kann man auch die
möglichen Shortcuts für die einzelnen Befehle sich anschauen.
