In diesem Projekt geht es darum, die Qualität der Adressdaten zu checken und bereinigen, da in einigen Fällen die Daten in unseren Adress-Buckets unvollständig oder fehlerhaft sind.
Wir haben uns auf zwei wesentliche Bestandteile von Adressen konzentriert: die Postleitzahl (PLZ) und die Hausnummer.

1. Postleitzahl

Für die PLZ haben wir versucht, problematische Muster zu identifizieren, die häufig in unserem Datensatz vorkommen. Diese Muster werden identifiziert, gezählt und am Ende durch ein Plot visuell dargestellt.
Typische PLZ-Probleme:

    na: Fehlender Wert
    unbekannt: Unbekannte PLZ
    komma: Enthält Komma
    nicht_digit: Nicht numerische Zeichen in der PLZ
    anfang_zero: PLZ beginnt mit einer Null(>5)
    leerzeichen: Enthält Leerzeichen
    zero: PLZ besteht nur aus Nullen
    vier_stellig: PLZ hat nur vier Ziffern
    ungültige_länge: PLZ hat eine ungültige Länge

2. Hausnummer

Für die Hausnummern wurden mehrere Funktionen implementiert, um die Daten zu bereinigen. Dabei konzentrieren wir uns auf die Trennung der Hausnummer von der Straße und die Korrektur fehlerhafter Hausnummern.
Vorgehensweise:

    Trennung von Hausnummer und Straße: Die Hausnummer wird von der Straße getrennt, um eine saubere Spalte für Hausnummern zu erhalten.
    Bereinigung der Hausnummern: Verschiedene Bereinigungsregeln wurden angewendet, um problematische Einträge zu korrigieren.

Typische Hausnummer-Probleme:

    Hausnummer enthält nur Nullen zb. 05 oder 0000
    Hausnummer enthält den Wert "nr." oder "unbekannt"
    Hausnummer besteht ausschließlich aus Sonderzeichen

Zusätzlich wurde eine Funktion implementiert, die Hausnummern miteinander vergleicht, die möglicherweise unterschiedlich geschrieben sind, 
aber zur gleichen realen Entität gehören könnten (z. B. "12a" vs. "12a-b"). 
Diese Funktion berechnet die Ähnlichkeit der Hausnummern, um potenziell gleiche Adressen zu identifizieren.


