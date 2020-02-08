# distant viewing page layout

![distant viwing DTA Kernkorpus](Alle_Bilder_Animation.gif)

A project, that appropriates a method called "distant viewing" for the analysis of typographic page layouts. In this example with the data from the 'Deutsches Textarchiv'.

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

![distant viwing DTA Kernkorpus](Alle_Bilder_Montage.jpg)
