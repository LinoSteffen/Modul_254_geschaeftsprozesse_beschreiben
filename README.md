# M254 - Geschäftsprozesse beschreiben

Im ganzen Modul werden wir uns mit der GLB Genossenschaft auseinandersetzen.

**Table of Contents**

Block 1 - Aufbauorganisation

Block 2 - Ablauforganisation

Block 3 - Grundlagen Geschäftsprozesse

# Block 1 - Aufbauorganisation

## Organigramm GLB Gruppe:

![](https://slabstatic.com/prod/uploads/8q5jdj6q/posts/images/J8LnIVGeimdInLtVDUNVbaTX.png)

# Block 2 - Ablauforganisation

Bei diesem Block behandeln wir den Ticketprozess der GLB Informatik

## Karteikartenmethode

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



## Bildkartenmethode

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

## Kernprozess Zimmermann

1. Planen
1. Vorstellen
1. Anpassen
1. Kaufen
1. Teile bauen
1. Zu Baustelle liefern
1. Zusammenbauen
1. weiter z. B. zu Dachdecker

![](https://slabstatic.com/prod/uploads/8q5jdj6q/posts/images/Mf1yrIuHgYbJp0SOJ0wm5Kz2.png)
