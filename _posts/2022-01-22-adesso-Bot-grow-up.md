---
layout: [post, post-xml]
title:  "adesso goes Discord"
date:   2022-01-22 12:06              # Pflichtfeld. Format "YYYY-MM-DD HH:MM". Muss für Veröffentlichung in der Vergangenheit liegen. (Für Preview egal)
author_ids: [bolsei]
categories: [Softwareentwicklung]
tags: [Discord, Java, Discord Bot, CDI]
---

In dem Beitrag [adesso goes Discord](https://www.adesso.de/de/news/blog/index.jsp) wurden die ersten Schritte aufgezeigt um einen Discord Bot in Java zu programmieren.
Dieser Bot soll in diesem Artikel erweitert werden.
Am Ende kann der Bot über eine Eingabe beendet werden und somit richtig abgeschaltet werden.
Für die Erweiterung wird die CDI Referenz Implementierung Weld für Java SE genutzt.

# Konfigurations Erweiterung 
Um CDI nutzen zu können müssen zuvor die pom.xml und die module-info.java erweitert werden.
In die pom.xml muss die Abhängigkeit zur CDI-Implementierung aufgenommen werden:

```xml
<dependency>
	CDI
</dependency>
```

In der module-info.java muss die CDI Implementierung ebenfalls aufgenommen werden.

```java
module de.adesso.discordbot { 
  requires net.dv8tion.jda;
  cdi
}
```

Nach diesen Anpassungen kann in der Anwendung jetzt Context and Dependency Injection genutzt werden.

# Der Container
Im Gegensatz zu Java EE Anwendung gibt es im Java SE Umfeld keinen Application Server der einen Container für die Nutzung von CDi bereitstellt.
Daher muss als erstes ein Container gestartet werden.
Dafür wird eine neue Klasse benötigt BotContainer.java.
Die neue Klasse erhält eine main-Methode in der, der benötigte CDI-Container gestartet wird.

```java

}
```
# Anpassung der BotStartUp Klasse

# Erweiterung zum Beenden

# Input Producer

# Der Fertige Bot