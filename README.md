M254 - Geschäftsprozesse beschreiben

# M254 - Geschäftsprozesse beschreiben

Im ganzen Modul werden wir uns mit der **GLB**  **Genossenschaft** auseinandersetzen.

**Autoren:** Lino Steffen &amp; Linus Moser

**Klasse:** Inf2021c

Version 5



**Table of Contents**

Block 1 - Aufbauorganisation

Block 2 - Ablauforganisation

Block 3 - Grundlagen Geschäftsprozesse

Block 4 - Prozessarten und ihre Abhängigkeit

Block 5 - BPMN

Block 6 -

Block 7 -



# Block 1 - Aufbauorganisation

## Organigramm GLB Gruppe KR1.1

![](https://slabstatic.com/prod/uploads/8q5jdj6q/posts/images/J8LnIVGeimdInLtVDUNVbaTX.png)

# Block 2 - Ablauforganisation

Bei diesem Block behandeln wir den Ticketprozess der GLB Informatik

## Karteikartenmethode KR.1.2

Ticket vom Kunden kommt rein.

1st. Level nimmt das Ticket an.

Kann das Ticket in unter 10 Minuten bearbeitet werden, muss dies gemacht werden.

Ansonsten gibt man es dem 2nd Level weiter. Löst er(2nd, 3rd, Entwickler) das, gibt er dem 1st Level Supporter das Ticket zurück und der schaut mit dem Kunden. Dies ist in jedem Fall (3rd,Entwickler) so. Kann der 2nd das Ticket nicht lösen, bekommt es der 3rd Level Supporter. Kann dieser das Ticket nicht lösen, muss der 3rd Level Supporter Kontakt mit den Entwickler aufnehmen.

```mermaid
flowchart LR
id2 & id3 & id4 --> id6[Lösung gefunden/Angewendet]; 

 Ticket--> id1[1st Level Support] --> id7[Kann der 1st Level das Problem unter 10 min lösen] -->|Nein| id2[2nd Level Support] --> id3[3rd Level Support] --> id4[Entwickler]
 id5[1st Level Support] --> id10[Mit Kunde Kontakt aufnehmen];
id6 --> id5;
id7 -->|Ja| id11[Problem lösen] --> id10

```



## Bildkartenmethode KR.1.2

```mermaid
flowchart TD
  A1><b>Aktivität</b>\nTicket entgegennehmen]              --> M1[<b>Mitarbeiter</b>\nFirst Level Support] --> EX1[<b>Externe</b>\nKunde];
  A2><b>Aktivität</b>\nProblemlösung suchen 5-10 Min]      --> M2[<b>Mitarbeiter</b>\nFirst Level Support] --> EX2[<b>Externe</b>\nKunde];
  A3><b>Aktivität</b>\nAbgabe an second level Support]     --> M3[<b>Mitarbeiter</b>\nFirst Level Support] --> M3.2[<b>Mitarbeiter</b>\nSecond Level Support];
  A4><b>Aktivität</b>\nRückmeldung an first level Support] --> M4[<b>Mitarbeiter</b>\nSecond Level Support] --> M4.2[<b>Mitarbeiter</b>\nFirst Level Support];
  A5><b>Aktivität</b>\nRückmeldung an Kunden]              --> M5[<b>Mitarbeiter</b>\nFirst Level Support] --> EX3[<b>Externe</b>\nKunde];;
 
  class A1,A2,A3,A4,A5 blue
  class M1,M2,M3,M4,M5,M3.2,M4.2 yellow
  class EX1,EX2,EX3,EX4 green

classDef blue fill:#2E8BC0,color:white;
classDef yellow fill:#FFFF2E,color:black;
classDef green fill:#008000, color:white;

```



# Block 3 - Grundlagen Geschäftsprozesse

## Kernprozess Zimmermann KR1.3

1. Planen
1. Vorstellen
1. Anpassen
1. Kaufen
1. Teile bauen
1. Zu Baustelle liefern
1. Zusammenbauen
1. weiter z. B. zu Dachdecker

![](https://slabstatic.com/prod/uploads/8q5jdj6q/posts/images/elhOGTs17rpy2E_BggYQ3hpN.png)

# Block 4 - Prozessarten und ihre Abhängigkeit

## Prozesslandkarte KR1.4

![](https://slabstatic.com/prod/uploads/8q5jdj6q/posts/images/nlM5s_xcUk0mptW3MmPd39iP.png)

### Lieferobjekte der Prozesslandkarte

```mermaid
flowchart LR
    id1>Führungsprozesse];
    id1.1(Vertriebsstrategie)-- Auslösendes Ereignis --> t1.1.1(Erzielen von Gewinn)-- Weg zum Ergebnis --> t1.1.3(Strategie wird definiert)-- Output --> t1.1.2(Strategie festgelegt)-- Wer? --> Geschäftsleitung
    id1.2(Produkte festlegen)-- Auslösendes Ereignis --> t1.2.1(Vertriebsstrategie wurde festgelegt)-- Weg zum Ergebnis --> t1.2.3(Es müssen Sinnvolle Produkte für den Vertrieb festgelegt werden)-- Output --> t1.2.2(Produkte wurden festgelegt)-- Wer? --> Geschäftsleitung
    id1.3(Produktionsstrategie)-- Auslösendes Ereignis --> t1.3.1(Produkte wurden festgelegt)-- Weg zum Ergebnis --> t1.3.3(Produktionsstrategie muss sinnvoll ausgearbeitet werden)-- Output --> t1.3.2(Produketionsstrategie wurde festgelegt)-- Wer? --> Geschäftsleitung

```

```mermaid
flowchart LR
    id2>Kernprozesse];
    id2.1(Planung)-- Auslösendes Ereignis --> t2.1.1(Auftrag von Kunden)-- Weg zum Ergebnis --> t2.1.2(planen)-- Output --> t2.1.3(fertiger Bauplan)-- Wer? --> Planer_in
    id2.2(Maurer_in)-- Auslösendes Ereignis --> t2.2.1(Auftrag von Projektleiter_in)-- Weg zum Ergebnis --> t2.2.2(mauern)-- Output --> t2.2.3(fertiges Objekt)-- Wer? --> Maurer_in
    id2.3(Innenbau)-- Auslösendes Ereignis --> t2.3.1(Auftrag von Projektleiter_in)-- Weg zum Ergebnis --> t2.3.2(bauen)-- Output --> t2.3.3(fertiges Objekt)-- Wer? --> Schreiner_in
    id2.4(Sarnierung)-- Auslösendes Ereignis --> t2.4.1(Auftrag vom Kunden)-- Weg zum Ergebnis --> t2.4.2(sanieren)-- Output --> t2.4.3(fertig saniertes Objekt)-- Wer? --> t2.4.4(Projektleiter_in, alle Bauberufe etc.)
    id2.5(Holzbau)-- Auslösendes Ereignis --> t2.5.1(Auftrag von Projektleiter_in)-- Weg zum Ergebnis --> t2.5.2(erstellen und aufbauen)-- Output --> t2.5.3(fertiges Objekt)-- Wer? --> Zimmermann
    id2.6(Küchenbau)-- Auslösendes Ereignis --> t2.6.1(Auftrag von Projektleiter_in)-- Weg zum Ergebnis --> t2.6.2(planen, erstellen und aufbauen)-- Output --> t2.6.3(fertige Küche)-- Wer? --> Küchenbauer_in
    id2.7(Maler_in)-- Auslösendes Ereignis --> t2.7.1(Auftrag von Projektleiter_in)-- Weg zum Ergebnis --> t2.7.2(malen)-- Output --> t2.7.3(fertiges Objekt)-- Wer? --> Maler_in
  id2.8(Dachdecker_in)-- Auslösendes Ereignis --> t2.8.1(Auftrag von Projektleiter_in)-- Weg zum Ergebnis --> t2.8.2(Dach decken)-- Output --> t2.8.3(fertiges Dach)-- Wer? --> Dachdecker_in
  id2.9(Qualitätskontrolle)-- Auslösendes Ereignis --> t2.9.1(Auftrag von Projektleiter_in)-- Weg zum Ergebnis --> t2.9.2(Projekt kontrollieren)-- Output --> t2.9.3(Fazit aus Objekt)-- Wer? --> t2.9.4(Bauherr_in und Projektleiter_in)


```

```mermaid
flowchart LR
    id3>Führungsprozesse];
    id3.1(Informatik)-- Auslösendes Ereignis --> t3.1.1(Probleme mit der IT-Infrastruktur)-- Weg zum Ergebnis --> t3.1.3(Lösen des Problemes)-- Output --> t3.1.2(Problem wurde gelöst)-- Wer? --> Informatiker
    id3.2(Dokumentationen/Anleitungen)-- Auslösendes Ereignis --> t3.2.1(Problem in der Informatik wurde gelöst)-- Weg zum Ergebnis --> t3.2.3(Anleitung/Dokumentation erstellen)-- Output --> t3.2.2(Anleitung wurde erstellt und kann verwendet werden)-- Wer? --> Informatiker
    id3.3(HR)-- Auslösendes Ereignis --> t3.3.1(Personal wird gesucht)-- Weg zum Ergebnis --> t3.3.3(Stellen ausschreiben, Bewerbungsgespräch, Anstellung)-- Output --> t3.3.2(Personal wurde angestellt)-- Wer?--> HR
    id3.4(Inkasso)-- Auslösendes Ereignis --> t3.4.1(Auftrag vom Kunden)-- Weg zum Ergebnis --> t3.4.3(Überprüfen der Bonität)-- Output --> t3.4.2(Kreditwürdig oder nicht)-- Wer? --> Finanzabteilung
    id3.5(Finanzen)-- Auslösendes Ereignis --> t3.5.1(Finanzen müssen verwaltet werden)-- Weg zum Ergebnis --> t3.5.3(Finanzen werden mit Software wie Abacus verwaltet)-- Output --> t3.5.2(Finanzen wurden verwaltet)-- Wer? --> Finanzabteilung

```

## Prozesslandkarte mit Verbindungen KR1.5

![](https://slabstatic.com/prod/uploads/8q5jdj6q/posts/images/DbbDRSraP83T78zgWcdVxXN3.png)

# Block 5 - BPMN

## BPMN Supportprozess - Ticket bearbeiten (KR2.1 und KR2.2)

![](https://slabstatic.com/prod/uploads/8q5jdj6q/posts/images/cIkTb4T97sTdgrV30ar3QsqA.png)

## BPMN Kernprozess - Zimmermann (KR2.3)

![](https://slabstatic.com/prod/uploads/8q5jdj6q/posts/images/Za0ohAwaYQfjCLP9CKTtTxRq.png)

## BPMN Führungsprozess - Produkte definieren (KR2.3)
