# Schlüssel zu China

Wie man es benutzt

Da es sich um eine einzelne, in sich geschlossene HTML-Datei handelt, ist keine Installation oder ein Webserver erforderlich.

    Laden Sie die Datei Sinarum_Clavis_visualisation.html herunter.

    Öffnen Sie die Datei in einem modernen Webbrowser (z.B. Chrome, Firefox, Edge).

XML Relations Netzwerkvisualisierung

Dieses Projekt ist eine interaktive, webbasierte Visualisierung eines Beziehungsnetzwerks, das aus XML-Daten extrahiert wurde. Es stellt bibliografische Einträge und Personen als Knoten dar und visualisiert die verschiedenen Arten von Beziehungen (Zitate, Referenzen etc.) zwischen ihnen als Kanten. Die Anwendung ist in einer einzigen, eigenständigen HTML-Datei implementiert und nutzt die JavaScript-Bibliothek vis.js für die Darstellung des Netzwerks.


    Interaktiver Graph: Knoten können verschoben, ausgewählt und inspiziert werden. Das Netzwerk-Layout wird dynamisch berechnet.

    Hierarchie-Filter: Filtern Sie die angezeigten Beziehungen nach ihrer hierarchischen Ebene (z.B. nur primäre Zitate, nur sekundäre etc.). Niedrigere Ebenen werden als graue "Grundstruktur" beibehalten, um den Kontext zu wahren.

    Filter nach Relationstyp: Schalten Sie einzelne Beziehungstypen (z.B. CitOf, SecCit) über Checkboxen ein oder aus.

    Knoten-Fokus: Wählen Sie einen bestimmten Knoten aus einer Dropdown-Liste aus, um ihn im Netzwerk zu zentrieren und seine direkten Verbindungen hervorzuheben.

    Detaillierte Tooltips: Fahren Sie mit der Maus über einen Knoten oder eine Kante, um detaillierte Informationen anzuzeigen.

    Legende: Eine feste Legende am unteren Rand erklärt die Farbcodierung für die verschiedenen Hierarchien und Knotentypen.

    
Das Netzwerk wird geladen und Sie können sofort mit den Steuerelementen interagieren.
Steuerelemente erklärt

    Hierarchie-Filter:

        Alle Relationen: Zeigt alle aktiven Beziehungen in ihrer jeweiligen Farbe an.

        1. Grad (Primäre): Hebt primäre Beziehungen (CitOf, CitIn) hervor.

        2. Grad (Sekundäre): Hebt sekundäre Beziehungen (SecCit) hervor und stellt primäre Beziehungen als graue Basis dar.

        3. Grad (Tertiäre): Hebt tertiäre Beziehungen (ThirdCit) hervor und stellt niedrigere Ebenen als graue Basis dar.

        Mögliche Neue Relationen: Isoliert potenziell neue, noch nicht bestätigte Beziehungen (PotCit).

        Bestätigte Neue Relationen: Isoliert neu entdeckte und bestätigte Beziehungen (NewCit).

    Relations-Typen:
    Mit diesen Checkboxen können Sie gezielt Typen von Kanten ein- und ausblenden. Die Farben entsprechen denen in der Legende:

        CitOf, CitIn (Primär, Rot)

        SecCit (Sekundär, Grün)

        ThirdCit (Tertiär, Blau)

        PotCit (Potenziell, Braun)

        NewCit (Neu & Bestätigt, Violett)

    Knoten fokussieren:
    Wählen Sie einen bibliografischen Eintrag aus der Liste, um das Netzwerk auf diesen Knoten zu zentrieren und ihn zu vergrößern.

    Zurücksetzen:
    Setzt die Fokussierung zurück und wendet die aktuellen Filter auf das gesamte Netzwerk an.

Technische Details
Verwendete Technologien

    HTML5: Grundstruktur der Seite.

    CSS3: Styling der Benutzeroberfläche.

    Bootstrap 5: CSS-Framework für ein responsives und sauberes Layout der Steuerelemente.

    JavaScript (ES6): Anwendungslogik für Filterung und Interaktion.

    vis.js (vis-network): Die Kernbibliothek zur Erstellung und Manipulation der interaktiven Netzwerkvisualisierung.

Datenstruktur

Die Netzwerkdaten (Knoten und Kanten) sind direkt als JavaScript-Arrays (nodeData, edgeData) in die HTML-Datei eingebettet.
Knoten (nodeData)

Jeder Knoten repräsentiert eine Entität (z.B. eine bibliografische Quelle) und hat folgende Struktur:

      
{
  "id": "bibl00023",
  "label": "A Madman's Diary",
  "type": "bibliography",
  "color": "#FFA500",
  "title": "ID: bibl00023\\nTyp: bibliography\\nTitel: A Madman's Diary...",
  "shape": "square",
  "size": 20
}

    

Jede Kante repräsentiert eine Beziehung zwischen zwei Knoten und hat folgende Struktur:

      
{
  "from": "bibl00021",
  "to": "bibl00023",
  "type": "CitOf",
  "hierarchy": "primary",
  "color": "#FF4444",
  "date": "",
  "desc": "",
  "width": 2
}

