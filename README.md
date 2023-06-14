# praatPDF App


## Inleiding
------------
Deze Python applicatie stelt je in staat om vragen beantwoord te krijgen over de inhoud van 1 of meerdere PDF documenten. Het is ontstaan vanuit de behoefte om zelf de brongegevens aan te leveren op basis waarvan het antwoord moet worden gegenereerd. In tegenstelling dus waarbij een AI dienst het antwoord samenstelt op basis van haar eigen kennisbank.


## Globale werking van de applicatie
------------

![MultiPDF Chat App Diagram](./img/PDF-LangChain.jpg)

The application follows these steps to provide responses to your questions:

1. PDF documenten worden ingelezen, en de tekst wordt gextraheerd.

2. Daarna wordt de tekst in blokken gehakt (chunks), om hier vervolgens embeddings van te maken. Deze woorden in een Vector DB opgeslagen.

3. Als de gebruiker een vraag stelt, wordt dit ook omgezet naar een embedding. Deze wordt vergeleken met de embeddings in de Vector DB. De embeddings met de beste overeenkomsten worden geranked, en de daarbij behorende tekstblokken (chunks) worden doorgestuurd naar het Large Language Model (LLM).

4. Het LLM stuurt een antwoord terug dat aan de gebruiker getoond wordt. 

## Installatie
----------------------------

1. Kloon de repo naar jouw eigen machine.

2. Gebruik onderstaande commando om benodigde Python packages te instaleren:
   ```
   pip install -r requirements.txt
   ```

3. Vraag een API key aan bij OpenAI en/of Huggingface. Maak een `.env` bestand aan en plaats hierin de API keys. Gebruik `.env.example` als voorbeeld. Let op! De naamsgeving van de variablene voor de API keys ligt vast. Deze kun je niet zelf verzinnen.


## Gebruik
-----

1. Zorg dat je de installatie hebt uitgevoerd.

2. De applicatie gebruikt Streamlit, zodat je het vanuit je browser kunt bedienen. Start de applicatie op met het volgende commando:
   ```
   streamlit run praatPDF.py
   ```

3. Als de applicatie gestart is, wordt de gebruikersinterface vanzelf geopend in jouw als standaard ingestelde web browser.

4. Laadt 1 of meerdere PDF bestanden en druk op de knop `Verwerk`.

5. Nu kun je je vraag stellen.


## Licentie
-------
Op deze praatPDF applicatie is de volgende licentie van toepassing: [MIT License](https://opensource.org/licenses/MIT).


## Tot slot
-----
Deze applicatie is door mij ontwikkeld als oefening ter kennismaking met generatieve AI. Het is niet mijn bedoeling om hier een serieuze/zakelijke toepassing van te maken. 
Ik verplicht mijzelf niet tot onderhoud en ondersteuning van deze applicatie. Ik zal daarom ook geen bijdragen/suggesties/verbeteringen in behandeling nemen. Voel je vrij om een kopie van de code te gebruiken om zelf uitbreidingen/verbeteringen aan de brengen.
