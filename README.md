# distant viewing page layouts

![distant viwing DTA Kernkorpus](Alle_Bilder_Montage.jpg)

A project, that appropriates a method called "distant viewing" from the fields of picture-analysis, which itself is an appropriation of "distant reading", back to from the literary studies, for the analysis of typographic page layouts. This first step towards such distant viewing uses data from the [Deutsches Textarchiv](https://github.com/deutschestextarchiv).

## Seitenspiegel-Analyse am DTA OCR Korpus

Ziel des vorliegenden Projekts ist es, das [DTA-Kernkorpus](https://deutschestextarchiv.de) für typographische Analysen zu nutzen. Im Spezifischen geht es um den Satzspiegel: *Wohin wurden auf einer Buchseite die Buchstaben gedruckt?* In Anlehnung an den Begriff des *distant reading* kann hier von *distant viewing* gesprochen werden.

Datengrundlage sind die XML-Daten aus dem OCR-Workflow der ersten Projektphase des DTA (2007–2010), die mit OCR erfasst, nachkorrigiert und in TEI P5 kodiert wurden. Es handelt sich um 199 Texte des *Kernkorpus*. Da das DTA seinen "Fokus", wie das Projektteam schreibt, auf die "Textdaten" legen möchte ("und die Verknüpfung zu den Faksimiledaten über die Seitenzuordnung ausreichend ist"), wurde dieser arbeitsaufwändige Workflow nicht mehr weiter geführt. Die entsprechenden Daten werden auf deren [Website](https://deutschestextarchiv.de/download#ocr) zur Verfügung gestellt. Die von mir am 30.1.2020 heruntergeladenen Daten datieren auf den 6.11.2013.

In den TEI-Daten des DTA werden jedem Buchstaben konkrete Koordinate nach folgendem Schema zugewiesen:

```xml
	<pb facs="#f0001"/>
	[…]
	<c ulx="44" uly="954" lrx="103" lry="1030" rendition="#c #b" xml:id="c1">R</c>
	<c ulx="102" uly="974" lrx="139" lry="1030" rendition="#c #b" xml:id="c2">u</c>
    <lb/>
	[…]
```

Ausgezeichnet sind in diesen Daten die TEI-*front*-, -*body*- und -*back*-Umgebungen (hier kommt nur der *body* in den Blick) und *framework*-Bereiche, das heißt beispielsweise Seitenzahlen, die hier nicht berücksichtigt werden.

Nota bene: Die Koordinaten beziehen sich weder auf die online dargestellten Faksimiles noch auf die Bilddaten der jeweiligen Urheber-Institution.

![distant viwing DTA Kernkorpus](Alle_Bilder_Animation.gif)

## To do's

Das Skript hier stellt nur einen ersten Schritt dar um die Methode einem ersten Versuch zu unterziehen. Zu entwickeln bleibt dabei noch u.a. (1.) an welche andere, ähnliche bereits entwickelt Methoden angeschlossen werden kann (beispielsweise im Bereich der Kodikologie von Swati Chandna et al.: "[Quantitative Exploration of Large Medieval Manuscripts Data for the Codicological Research](http://doi.org/10.1109/ldav.2016.7874306)", danke Hannah Busch für den Hinweis!); (2.) eine Verbesserung der Datengrundlage (denn die DTA-Bilddaten sind nicht offen zugänglich und so können die Ergebnisse nicht zufriedenstellend mit abgeglichen werden); (3.) eine Auflösung der einseitigen Bilder in eine **Doppelseiten-Ansicht**, wie es für typographische Analysen notwendig wäre; (4.) nicht schwarze, sondern **semi-transparente Blöcke** übereinander legen wodurch häufiger bedruckte Stellen schwärzer ercheinen als seltener bedruckte (das würde auch auf den Hinweis von Frederike Neuber reagieren, dass bestimmte Layouts in einer überlagernden Darstellung nicht sichtbar werden) und die Anzahl der Seiten würde dadurch kenntlicher werden; …


## Erläuterung

Mit diesem Prozedere werden im Grunde die (bereits als verfügbar angenommenen) OCR-Koordinaten genommen und übereinander gelegt, wie im folgenden Bild von links nach rechts lesend dargestellt sein soll:

![How to](howto.jpg)

Das ergibt bei den DTA-OCR-Workflow-Daten folgende grobe Auswertung (per `grep`): Viele Werte liegen in unrealisitisch zu niedrigen (negativen) oder in zu hohen Bereichen, die im Skript auch nicht berücksichtigt werden.

![grobe Auswertung, statistisch per grep](auswertunggrep.jpg)

