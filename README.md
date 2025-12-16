# Hur jag kommer att testa ert hotell

Jag skriver här ner stegen jag kommer att köra när jag klonar era repon och kör apparna på min dator.

1. Jag klonar ert repo till en mapp, delete_me, på mitt skrivbord
2. Jag skapar en virtuell miljö
3. Jag aktiverar den virtuella miljön och kör pip install -r requirements.txt. Se till att alla bibliotek finns i textfilen.
4. Jag skapar en helt ny databas i MySQL Workbench, delete_me_hotel
5. Jag byter connection string i er app så att den stämmer överens med databasen
6. Jag kör alembic stamp base = ställer mig på första migrationen
7. Jag kör alembic upgrade head = kör alla migrationer fram till den sista
8. När jag trycker på "play" från main.py/app.py eller motsvarande ska det seedas enligt spec i uppgiften
9. Jag bör nu se en meny i terminalfönstret i VSCode. Er app måste hantera fel input utan att krascha.

>[!TIP]
>Kika gärna på den inspelade videon på sharepoint så kan ni se de exakta stegen jag kör.


## Vanliga källor till kraschar

1. Dålig felhantering av input("ange id: "). Ni måste hantera int och str korrekt!
1. Ni hanterar inte None korrekt. Tänk på att session.query().first() returnerar ditt tabellobjekt eller None.
1. Brist på try: except: i koden.

>[!TIP]
>Hanterar ni dessa tre källor till fel har ni täckts 95 %+ av alla problem.
>Ni bör alltid anta att jag som ska rätta er app skriver in "fel" input och ni ska täcka upp för detta.
