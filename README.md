# ePaper display
ePaper apparaat voor de bar van Youri!  

# Eerste keer starten
Als het apparaatje de eerste keer start en natuurlijk nog geen WiFi heeft, zal deze na ongeveer 1 minuut proberen zelf een hotspot starten met de naam "Youri's Bar Display Setup". Het wachtwoord om daarmee te verbinden is "fallback". Hier kun je vervolgens je eigen WiFi configereren zodat het apparaatje in ieder geval WiFi heeft en dus ESPHome opgenomen kan worden zodat o.a. de quotes aangepast kunnen worden.  

# Opnemen in ESPHome

> [!WARNING]
> Goed om te weten, bij 15 minuten inactiviteit schakelt het display al zijn power-saving-mode in. Mocht het apparaatje in de onderstaande stappen ineens niet meer te bereiken zijn is deze waarschijnlijk in slaap gevallen. Keer aan en uit zetten en je hebt weer 15 minuten om de configuratie af te ronden!

Kan op twee manieren. Eerst de makkelijkste manier:  Vraag Jeffrey  
Als je toch eerst zelf wil proberen dien je onderstaande stappen te doen

1. ESPHome in je HomeAssistant installeren, volg hiervoor instructies op [de ESPHome website](https://esphome.io/install/)
Voeg daarna de waardes toe uit [het voorbeeld secrets.yaml bestand](docs/secrets.yaml.example) of doe het zelf handmatig aan je **secrets.yaml** in ESPHome:
    - wifi_ssid: "Vul hier je wifi naam in"
    - wifi_password: "Vul hier je wifi wachtwoord in"
    - epaper_display_ota_password: "verander-dit-alsjeblieft-in-een-lang-iets"
    - epaper_display_api_key: "verander-dit-ook-is-nodig-voor-de-tijd"

2. In ESPHome een nieuw apparaat maken, voor de geavanceerde opties kiezen en een lege configuratie aanmaken. Kopieer daarna alles uit [het voorbeeld voorbeeld overnemen](docs/epaper.yaml.example) en plak dat in je lege configuratie.  Verander desnoods de waardes achter `!secret` als je die waardes zelf anders hebt genoemd.

3. Klik als alles er staat op `install` rechts onderin. Kies daarna voor onder **geavanceerd** voor de optie *download binary*. Wacht ongeveer 10 minuten en als het goed is staat er vanzelf een keer dat het compileren en uploaden klaar is.

4. Zoek in je router naar het IP adres van de display en browse dan naar: http://ip-adres-hier  Om in te loggen gebruik je als gebruikersnaam `admin` en als wachtwoord `nietmoeilijkdoen`. Daarna kun je het gedownloade .bin bestand uploaden bij de knop **Upload firmware**
> [!WARNING]
> Echt http, niet https. Browsers doen dat standaard vaak al voor je https maken ondanks dat je echt http:// doet. Ook kan het zijn dat het apparaatje intussen in slaapstand gevallen is. Zet 'm dan uit en aan.
5. Daarna moet het apparaat in HomeAssistant staan onder **Appararaten > ESPHome > Bar Display**. Hier kun je nu makkelijk de waardes van de quotes enzo aanpassen zolang het apparaat niet in slaapstand staat. Hiervoor dient het apparaat ook niet in slaapstand te staan. Mocht het dus niet werken, even uit en aan :) 


> [!TIP]
> De ververs knop zorgt ervoor dat het apparaatje 5 minuten aan blijft staan om even vlug nieuwe quotes erin te zetten, zonder dat deze helemaal uit en aan moet.
