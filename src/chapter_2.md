# Diagram Herkansing

```plantuml

@startuml
state "Zin in koffie" as Gebruiker.Zin
state "Voorbereidingen treffen" as Gebruiker.Voorbereiden
state "Wachten op koffie" as Gebruiker.Wachten
state "Koffie drinken" as Gebruiker.Drinken

[*] --> Gebruiker.Zin : Geur van koffie
Gebruiker.Zin --> Gebruiker.Voorbereiden : 1
Gebruiker.Voorbereiden --> Gebruiker.Wachten : 2
Gebruiker.Wachten --> Gebruiker.Drinken : 3
Gebruiker.Voorbereiden -> Apparaat.Filter : Filter plaatsen
Gebruiker.Voorbereiden -> Apparaat.Maling : Filtermaling toevoegen 
Gebruiker.Voorbereiden -> Apparaat.Water : Water toevoegen
Gebruiker.Voorbereiden -> Apparaat.Aanzetten : Koffie zetten starten
Apparaat.Aanzetten -> Gebruiker.Wachten : Machine begint proces
Gebruiker.Drinken --> Gebruiker.Opruimen: 4
Gebruiker.Opruimen -> Apparaat.Leeg : Opruimen
@enduml


@startuml
state "Apparaat leeg" as Apparaat.Leeg
state "Koffiefilter geplaatst" as Apparaat.Filter
state "Filtermaling toegevoegd" as Apparaat.Maling
state "Water toegevoegd" as Apparaat.Water
state "Apparaat aan" as Apparaat.Aanzetten
state "Koffie is klaar!" as Apparaat.Klaar

Apparaat.Leeg --> Apparaat.Filter : 1
Apparaat.Filter --> Apparaat.Maling : 2
Apparaat.Maling --> Apparaat.Water : 3
Apparaat.Water --> Apparaat.Aanzetten : 4
Apparaat.Aanzetten --> Apparaat.Klaar : 5
Apparaat.Klaar -> Gebruiker.Drinken
Apparaat.Klaar --> Apparaat.Leeg : 6

@enduml

```
