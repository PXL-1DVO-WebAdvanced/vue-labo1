# Vue.js - Labo 1
- Basis functionaliteiten
- Events
- Formulieren
- Componenten
- Sass

## Intro
In deze oefening maken we een Vue applicatie waarmee de gebruiker producten kan aanduiden om een vergelijking te maken. Er kan gebruik gemaakt worden van een filter om eenvoudig te zoeken en elke gebruiker moet zich kenbaar maken vooraleer de producten getoond worden.

Onderaan deze pagina vind je enkele screenshots ter verduidelijking!

## Login
Werk het *LoginComponent* verder af en gebruik dit in de Vue applicatie wanneer deze voor de eerste keer getoond wordt.

- Gebruik hiervoor een *username* data-eigenschap. Wanneer deze variabele de waarde *null* heeft toon je het LoginComponent, anders toon je het div-element met id *main*
- Zorg ervoor dat de gebruikersnaam en het wachtwoord verplicht in te vullen zijn door middel van de standaard formulier validatie
- Controleer, wanneer de gebruiker op de *Sign in*-knop klikt of op enter drukt, of het wachtwoord overeen komt met de tekst "wachtwoord". Gebruik hiervoor de method *login()* 
    - Indien dit klopt, communiceer dan de gebruikersnaam naar het App component, gebruik hiervoor een event emit *userLogin*
    - Indien het wachtwoord fout is toon je een error onderaan het login-formulier
- De *remember-me*-checkbox heeft geen functionaliteit is deze applicatie

## NavBar
Wanneer de gebruikers zich correct heeft aangemeld wordt de container met id *main* getoond. Voeg bovenaan in deze container het NavBarComponent toe.
- Zorg ervoor dat de gebruikersnaam die werd gebruikt om aan te melden als inhoud/tekst van de knop (helemaal rechts in de navigatiebalk) getoond wordt.
- Wanneer de gebruiker op deze knop klikt zal hij worden afgemeld (username = null) en dient het LoginComponent opnieuw getoond te worden.
    - Gebruik hiervoor een event emit *userLogout*

## Products
Het App component bevat reeds een lijst van producten: *this.products*. De namen en prijzen hiervan worden random gegenereerd bij het renderen van de template zodat de functionaliteit van de filter later uitgebreid getest kan worden. 

## ProductCard
- Voeg in de container met de klasse *product-list* het *ProductCardComponent* toe voor elk product in de productenlijst.
- Werk het ProductCardComponent af zodat het product in zijn geheel als attribuut kan worden meegegeven.
- Zorg ervoor dat product eigenschappen op de juiste plek worden weergegeven, gebruik hiervoor databinding.
- Zorg voor de nodige functionaliteit waardoor het aan- en uitvinken  van de checkbox ervoor zorgt dat de compare-eigenschap van het desbetreffende product gewijzigd wordt. Gebruik hiervoor het event emit *changeCompare*. Voorzie zowel het product-id als de nieuwe *compare*-waarde als argument van deze emit.

## Filter
Gebruik onderstaande template om de filter te implementeren. Definieer een variabele *searchText* en bind deze aan het input-element. 


    <form>
        <fieldset>
            <caption>Filter</caption>
            <input type="text" class="form-control" placeholder="Zoek op titel">
        </fieldset>
    </form>

- Maak een eigenschap *filteredProducts* die afhankelijk is van de variabele *searchText*
    - Indien *searchText* een waarde bevat gaan we deze waarde vergelijken met de titel van de producten. Enkel producten waarbij een match wordt gevonden worden geretourneerd
    - Wanneer *searchText* **geen** waarde bevat wordt de volledige productlijst geretourneerd
- Zorg er nu voor dat deze *filteredProducts* worden getoond (via ProductCardComponent) in de *product-list*-container en niet de volledige productenlijst.

## Vergelijking
- Maak een eigenschap *comparedProducts* die afhankelijk is van de productenlijst en een gefilterde lijst retourneerd van producten waarvan de *compare*-eigenschap de waarde *true* heeft
- Werk het *ComparisonListComponent* af zodat de producten uit de *comparedProducts*-eigenschap worden getoond in de ongeordende 
- Toon het fieldset-element met id *comparison* enkel wanneer er reeds producten in *comparedProducts*-lijst aanwezig zijn! 
- Zorg ervoor dat wanneer de gebruiker op het *trash*-icoontje klikt het betreffende product uit de vergelijking wordt gehaald. Hiervoor moet dus de *compare*-eigenschap van het product op *false* worden gezet. Gebruik hiervoor een event emit *removeFromComparison* die het product-id als argument voorziet.

