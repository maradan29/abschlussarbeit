
# Abschlussarbeit - CAS in Datenjournalismus - Nicolas Maradan




## Checklist

- [x] Ausgangsthese
- [x] Einschätzung von Aufwand/Ertrag vor Beginn des Projektes 
- [x] Bezeichnung des Knackpunkts des Projektes
- [x] Kurze Zusammenfassung des Gesprächs mit einer Briefing Person 
- [x] Datensatz
- [x] Programmiercode
- [x] Arbeitsprotokoll



## Der publizierte Artikel

[Des musées encore trop inaccessibles](https://www.laliberte.ch/news/regions/canton/des-musees-encore-trop-inaccessibles-590958)

Um den Artikel zu lesen, müssen sie [hier](https://www.laliberte.ch/abos/espace-clients/creer-compte/) ein kostenloses Konto erstellen.



## Ausgangsthese

Kultur muss für alle zugänglich sein. Aber ist es wirklich so? In der Schweiz sind viele Museen nicht oder nur teilweise für Personen mit eingeschränkter Mobilität geeignet. Das Ziel unserer Analyse ist es, genau herauszufinden, wie viel Prozent und warum.



## Idee

Für unsere Analyse verwenden wir die [Suchmaschine](https://www.museums.ch/fr/au-musee/recherche-de-mus%C3%A9es/), die auf der Website des Verband der Museen der Schweiz verfügbar ist. Mit diesem Tool können wir alle Museen in der Schweiz nach Kanton durchsuchen. Es ist möglich, nach verschiedenen Kriterien zu suchen, zum Beispiel nach der Rollstuhlgängigkeit. Wir werden die Informationen mit BeautifulSoup und Selenium sammeln. Laut **Isabelle Raboud-Schüle** (Präsidentin des Verbands der Museen der Schweiz) ist die Datenbank  zuverlässig und vollständig. Ziel ist es herauszufinden, wie viel Prozent der Museen für Rollstuhlfahrer völlig zugänglich sind. Unser erster Eindruck ist, dass diese Rate sehr niedrig ist. Aber wieso? Offensichtlich befinden sich einige Museen in alten Gebäuden wie ein Schloss, in denen es nicht möglich ist, Zugangsrampen bereitzustellen. Aber könnten zusätzliche Anstrengungen unternommen werden? Dies ist eine der Fragen, die wir stellen müssen. Nach meinen Recherchen wurde zu diesem Thema (aus statistischer Sicht) noch kein Artikel verfasst, zumindest nicht in der Romandie. 



## Einschätzung von Aufwand / Ertrag

Auf den ersten Blick sollte das Sammeln der Daten kein Problem sein, da die Website des Verbandes der Museen der Schweiz gut strukturiert zu sein scheint. Wir sollten jedoch ein wenig Arbeit erwarten, um die Daten zu bereinigen. Es wird auch Zeit für die Datenarbeit mit Pandas brauchen, aber auch für die Arbeit mit Geodaten (mit dem Google API-Schlüssel und Geopandas). Wir sollten auch nicht vergessen, Zeit für die grafische Visualisierung aufzuwenden, um die Daten und insbesondere die Geodaten so klar wie möglich darstellen zu können. Es ist eine Herausforderung, weil ich noch nie zuvor Geodaten verwendet habe! Meine Idee ist es, einen Teil der Daten auf einer Karte mit präziser Geolokalisierung darstellen zu können. Angesichts der grossen Anzahl von Museen in der Schweiz erscheint es mir jedoch nicht relevant, sie alle auf einer Landkarte zu platzieren. Es würde zu viele Punkte auf der Karte geben und es wäre nicht lesbar. Bei dieser Grafik werde ich mich daher auf die Museen des Kantons Freiburg konzentrieren. Aber ich werde natürlich andere Grafiken erstellen, die die Daten für die gesamte Schweiz nach Kanton darstellen. Die erste Briefingperson, die ich kontaktieren möchte, ist **Isabelle Raboud-Schüle**. Sie ist Direktorin von dem Musée gruérien in Bulle (Kanton Freiburg) und seit 2019 Präsidentin des Verbands der Museen der Schweiz. Dann muss ich Direktoren (ein oder zwei) von Museen kontaktieren, die nicht Rollstuhlzugänglich sind. Ich werde besonders Briefingpersonen im Kanton Freiburg suchen, da dieser Kanton mein Zielpublikum ist, als Journalist für "La Liberté". Aber es wäre auch interessant sein, die Fachstelle "Kultur inklusiv" von **Pro Infirmis** zu kontaktieren. Diese Arbeit scheint innerhalb der Frist von fünf Tagen (40 Stunden) erreichbar zu sein.

![](diverses/spider.png)



## Knackpunkte

1. Die Suchmaschine bietet zwei Kategorien: "Vollständige Rollstuhlgängigkeit" und "Teilweise Rollstuhlzugänglich". Kategorie "Vollständige Rollstuhlgängigkeit" funktioniert sehr gut. Es gibt jedoch ein Problem mit der Kategorie "Teilweise Rollstuhlzugänglich". In einigen Kantonen wie Appenzell Innerrhoden umfasst diese Kategorie nur die Museen, die teilweise Rollstuhlzugänglich sind. Aber in anderen Kantonen wie Basel-Landschaft umfasst diese Kategorie sowohl die Museen, die vollständig zugänglich sind, als auch solche, die nur teilweise zugänglich sind. Es verzerrt die Berechnungen. Und die Tatsache, dass ein Museum für Rollstühle nur teilweise zugänglich ist, kann von Museum zu Museum unterschiedlich sein. Deshalb habe ich mich entschieden, nur die Kategorie "Vollständige Rollstuhlgängigkeit" zu verwenden. Meiner Meinung nach ist dies gerechtfertigt, da es für eine Person, die sich im Rollstuhl bewegen muss, wichtig ist, vollen und nicht nur teilweisen Zugang zu haben.

2. Die Suchmaschine auf Museums.ch listet alle Schweizer Museen auf, die sich registrieren wollten. Also habe ich natürlich zuerst Daten aus allen Museen gesammelt. Aber während meines Interviews mit Isabelle Raboud-Schüle erzählte sie mir, dass er ist auch möglich, nur nach Museen suchen, die Mitglieder des Verbandes der Museen der Schweiz sind. Dies repräsentiert alle Museen, die den Standards des International Council of Museums (ICOM) entsprechen. Es erschien mir daher relevanter, für meine Analyse nur die "offiziellen" Museen beizubehalten, die Teil des Vereins sind. In der Tat, wie **Isabelle Raboud-Schüle** sagt: "In der Schweiz ist die Definition von Museum sehr weit gefasst, da dieses Wort nicht geschützt ist. Jeder kann ein Museum eröffnen, wenn er möchte". Das Sortieren erscheint mir daher wichtig. 

3. Für die grafische Darstellung der Daten sind mehrere Lösungen möglich. Dank Modulen wie **Matplotlib** oder **Plotly** können wir direkt mit Python arbeiten. Wir können auch Schnittstellen wie **Datawrapper**, **Infogram** oder **Flourish** verwenden. Also, welche Lösung sollen wir wählen? Um dies herauszufinden, ist es ideal, beide Lösungen testen zu können. Deshalb habe ich sowohl mit Plotly als auch mit Datawrapper Grafiken erstellt. Ich habe etwas länger gebraucht, aber es hat sich gelohnt. Beide Lösungen sind interessant. In beiden Fällen sind die Grafiken lesbar und effizient. Es war daher sehr schwer zu wählen. Am Ende habe ich mich für die mit **Datawrapper** erstellten grafischen Darstellungen entschieden, da diese interaktiver sind. Ich möchte klarstellen, dass ich nur drei grafische Visualisierungen gemacht habe, weil ich denke, dass es für den Leser komplizierter wird, wenn es mehr Grafiken gibt.

###### Hier sind die grafischen Visualisierungen, die direkt mit **Plotly** und **Geopandas** gemacht werden

![](graphics/accessibilite.png)

![](graphics/densite.png)

![](graphics/fribourg.jpg)

###### Und hier sind die grafischen Visualisierungen, die mit **Datawrapper** erstellt wurden

![](graphics/accessibilite2.png)

![](graphics/densite2.png)

![](graphics/fribourg2.png)



## Briefingperson

###### Interview mit Isabelle Raboud-Schüle, Direktorin von dem Musée gruérien in Bulle (FR) und Präsidentin des Verbands der Museen der Schweiz

**Welche Museen sind auf Ihrer Website aufgeführt?**

Die Suchmaschine listet alle Schweizer Museen auf, die sich registrieren wollten. Der Benutzer kann auch nur Museen auswählen, die Mitglieder des Verbandes der Museen der Schweiz sind. Um Mitglied unserer Vereinigung zu werden, ein Museum muss die ethischen Regeln von dem International Council of Museums (ICOM) einhalten und insbesondere eine stabile und eindeutig gemeinnützige institutionelle Basis haben. Er muss ein aktuelles Inventar seiner Sammlungen führen, in der Lage sein, die von ihm hergestellten Werke und Objekte zu erhalten und angemessen auszustellen. All dies setzt ein langfristiges Engagement voraus. Vor allem aber hat das Museum eine Mission gegenüber der Gesellschaft, indem es die Erforschung seiner Sammlungen ermöglicht, qualitativ hochwertige Dokumentationen bereitstellt und regelmäßig der Öffentlichkeit zugänglich ist.

**In der Schweiz ist der Prozentsatz der Museen mit vollständige Rollstuhlgängigkeit sehr gering. Was denken Sie?**

Viele Museen befinden sich in historischen Gebäuden, die oft geschützt sind. Es ist daher sehr schwierig, wenn nicht unmöglich, eine vollständige Zugänglichkeit für Rollstuhlfahrer zu gewährleisten. Zum Beispiel müsste viel Geld investiert werden, um Außenaufzüge zu bauen. Und dies ist nicht immer mit der Erhaltung des erbauten Erbes vereinbar. Museen, die vollständig zugänglich sind, sind solche, die in speziell für sie errichteten Gebäuden untergebracht sind. Heute geschieht dies immer mehr, wie in Lausanne mit dem Kunstviertel Plateforme 10, aber die meisten Museen befinden sich in Gebäuden, die nicht dafür konzipiert wurden, wie Häuser, Werkstätten oder ländliche Gebäude.

**Sollten Anstrengungen unternommen werden, um Museen zugänglicher zu machen?**

Zugänglichkeitsprobleme betreffen nicht nur Menschen mit eingeschränkter Mobilität, sondern auch Familien mit Kinderwagen. Es gibt auch Zugänglichkeitsprobleme für Leute mit sensorischen Schwierigkeiten, zum Beispiel visuell oder hörend. Die Museen haben bereits erhebliche Anstrengungen unternommen, aber wir müssen noch große Fortschritte erzielen.



## Inputs

[Karte der Schweiz für Geodaten](inputs/g1g17.shp)

[Bevölkerung nach Kanton (Bundesamt für Statistik)](inputs/je-d-01.02.03.04.xlsx)


## Outputs

[Daten mit dem Prozentsatz der Rollstuhlgängigkeit nach Kanton](outputs/accessibilite.csv)

[Daten mit der Anzahl der Museen nach Bevölkerung](outputs/densite.csv)

[Daten für die Karte des Kantons Freiburg](outputs/adresses.csv)

[Backup mit allen Daten](outputs/sauvegarde.csv)


## Programmiercode

[Mein Notebook Museen.ipynb](Museen.ipynb)


## Arbeitsprotokoll

| Datum  | Aufwand | Tätigkeit |
| ------------- | ------------- | ------------- |
| 28.12.2020  | 2h  | Idee entwickeln, Ausgangsthese ausarbeiten.  |
| 29.12.2020  | 4h  | Scraper für Museen schreiben (in meinem Notebook **Museen.ipynb**). |
| 30.12.2020  | 1h30  | Google API-Schlüssel erstellen. Ich brauche es, um die Postanschriften den Museen in geografische Koordinaten umzuwandeln. Beachten Sie, dass mein Google API-Schlüssel aus Gründen der Vertraulichkeit nicht im Code angegeben ist. Es wird Ihnen jedoch per E-Mail zugeschickt, damit Sie das Notebook benutzen können. |
| 30.12.2020  | 7h  | Mit den Geodaten arbeiten (in meinem Notebook **Museen.ipynb**). Die Idee ist, eine grafische Darstellung von geografischen Daten auf einer Karte zu erstellen. |
| 31.12.2020  | 1h  | Notebook **Museen.ipynb** kommentieren (es ist sehr wichtig, dass mein Code so klar wie möglich ist. Es muss nicht nur für andere verständlich sein, sondern auch für mich selbst, wenn ich es in einigen Monaten oder Jahren wieder verwenden muss). |
| 31.12.2020  | 0h30  | Repository auf Github erstellen. |
| 31.12.2020  | 1h30  | Github-Repository ausfüllen, mit Informationen wie die Ausgangsthese, die Einschätzung von Aufwand/Ertrag, die Bezeichnung des Knackpunkts des Projektes. |
| 01.01.2021  | 4h  | Grafischer Darstellungen mit **Datawrapper** und **Plotly** testen. Ich benutze beide Methoden, um die Ergebnisse vergleichen zu können. |
| 02.01.2021  | 0h30  | Spider für Einschätzung von Aufwand / Ertrag erstellen. |
| 02.01.2021  | 0h30  | Github-Repository weiter ausfüllen. |
| 03.01.2021  | 2h  | Scraper für Museen verbessern. |
| 04.01.2021  | 1h30  | Kontakt mit **Isabelle Raboud-Schüle**. Als Präsidentin des Verbands der Museen der Schweiz ist sie die wichtigste Briefingperson für meine Analyse. Deshalb ist sie die erste Briefingperson, die ich kontaktiert habe. |
| 04.01.2021  | 2h  | Scraper für Museen noch verbessern. |
| 04.01.2021  | 0h30  | Github-Repository weiter ausfüllen. Insbesondere muss ich mein Arbeitsprotokoll aktualisieren. |
| 06.01.2021  | 1h30  | Kontakt mit **Elise Meyer**. Sie ist Kuratorin bei Museum Charmey, im Kanton Freiburg. Mein Ziel ist es, das Beispiel eines Museums zu zeigen, das sich in einem alten Gebäude befindet.  |
| 06.01.2021  | 1h30  | Kontakt mit **Nicole Grieve**. Sie arbeitet für die Fachstelle Kultur inklusiv von Pro Infirmis. Ich habe sie kontaktiert, weil sie die Problematik meines Artikels (Zugänglichkeit der Kultur) sehr gut kennt. |
| 08.01.2021  | 1h30  | Schreiben des Unterartikels. Es handelt sich um die Gesamtzahl der Museen pro Kanton. Ich finde dieses Thema ist eine interessante Ergänzung zum Hauptthema. |
| 10.01.2021  | 1h30  | Datenüberprüfung. Meiner Meinung nach ist es wichtig, nicht nur Ihren Code zu überprüfen, sondern auch die Output, um sicherzustellen, dass alle gesammelten Daten sinnvoll sind. |
| 12.01.2021  | 5h  | Schreiben des Hauptartikels. |
| 12.01.2021  | 1h  | Mein Repository auf Github vervollständigen. |
| 13.01.2021  | 0h30  | Deckblatt ausfüllen. |
