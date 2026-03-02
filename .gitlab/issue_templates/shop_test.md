### Voor de ontwikkelaar
* [ ]  Zet de betalingsmethode op test, zodat de klant een order kan plaatsen met alle betalingsmethoden
* [ ]  Speciale coupon code toevoegen voor het testen (10% korting)
* [ ]  Controleer dat de Innosend API Token correct is ingesteld
* [ ]  Controleer dat de Innosend Pickup Points module actief is

### Review omgeving
- Review omgeving locatie: {URL_REVIEW_OMGEVING}

---

### Beveiligingslogin
De review omgeving is afgeschermd met een inlog (htaccess).

Voer de onderstaande username en wachtwoord in om de test omgeving te bekijken:
- Username: falconmedia
- Password: falconmedia

---

### Login Magento admin / beheeromgeving
- Admin url: {URL_REVIEW_OMGEVING}/beheer
- Admin gebruiker: {REVIEW_ADMIN_USER}
- Admin wachtwoord: {REVIEW_ADMIN_PASSWORD}

---

### Wat genegeerd mag worden
- SSL waarschuwingen.
- Producten die recent zijn toegevoegd. Er wordt niet altijd gebruik gemaakt van een meest recente databasekopie bij het klaarzetten van de review omgeving.
- Productafbeeldingen die missen. Omdat het vaak om grote hoeveelheden afbeeldingen gaat, migreren we deze niet mee. Daarom kan het voorkomen dat *productafbeeldingen* niet altijd zichtbaar zijn.
- De snelheid van de website. De review draait op een vele malen lichtere serveromgeving dan de productiewebsite.

---

### De testlijst

**Algemeen**
* [ ]  Wordt de website in het algemeen nog correct weergegeven?
* [ ]  Wordt de header correct weergegeven?
* [ ]  Wordt de footer nog correct weergegeven?
* [ ]  Worden informatiepagina's nog correct weergegeven?
* [ ]  Werken alle links in de footer nog?
* [ ]  Ziet de homepage er goed uit?

**Zoeken / Categoriepagina**
* [ ]  Kan er gezocht worden naar producten in de zoekbalk?
* [ ]  Worden dezelfde zoekresultaten weergegeven op productie als op de review met dezelfde zoekterm?
* [ ]  Worden zoeksuggesties weergegeven bij het invoeren van een gedeelte van de zoekterm?
* [ ]  Kan er gefilterd worden op attributen van een product?
* [ ]  Werkt de sortering naar behoren?
* [ ]  Worden alle selectieverfeningsopties weergegeven die verwacht worden?
* [ ]  Worden categorieteksten / -afbeeldingen correct weergegeven?

**Productdetailpagina (controleer 10 artikelen in verschillende categorieën)**
* [ ]  Worden teksten correct weergegeven?
* [ ]  Worden afbeeldingen correct weergegeven?
* [ ]  Indien er reviews zijn: staan deze erbij?
* [ ]  Werkt de image cropping?
* [ ]  Wordt de BTW correct weergegeven?
* [ ]  Worden vergelijkbare producten / cross-sells correct weergegeven?

**Winkelwagen**
* [ ]  Is de weergave van de winkelwagen correct?
* [ ]  Kunnen artikelen toegevoegd worden aan het mandje?
* [ ]  Werkt het toevoegen van een couponcode? (indien van toepassing)
* [ ]  Worden prijzen correct weergegeven? (in geval van meerdere landen, klopt de btw dan ook?)
* [ ]  Wordt de cropped image goed weergegeven?

**Checkout**
* [ ]  Kan er een bestelling geplaatst worden met `iDeal` (hier is een test voor nodig)
* [ ]  Kan er een bestelling geplaatst worden met `Creditcard` (hier is een test voor nodig)
* [ ]  Kan er een bestelling geplaatst worden met `CheckMo`
* [ ]  Komt er een bevestigingsmail binnen?
* [ ]  Als de betaling binnen is, wordt er dan ook een factuur verstuurd?
* [ ]  Worden er shipping updates verstuurd?
* [ ]  Kun je een bestelling plaatsen als je ingelogd bent met verschillende betalingsmethoden?

**Mijn account**
* [ ]  Kan er een account aangemaakt worden?
* [ ]  Ziet het hoofdmenu van de mijn-accountpagina er netjes uit?
* [ ]  Ziet het kopje `Recente orders` er correct uit op de mijn-accountpagina?
* [ ]  Werkt de pagina `Mijn account` nog naar behoren?
* [ ]  Werkt de pagina `Downloads` nog naar behoren?
* [ ]  Werkt de pagina `Mijn verlanglijst` nog naar behoren?
* [ ]  Werkt de pagina `Adresboek` nog naar behoren? (kan er een adres aangemaakt / verwijderd worden?)
* [ ]  Werkt de pagina `Accountgegevens` nog naar behoren? (kan een wachtwoord worden aangepast?)

---

### Innosend – API configuratie

**Admin: Stores → Configuration → Innosend → API Configuration**
* [ ]  Is de module ingeschakeld (Enable API connection = Yes)?
* [ ]  Staat de mode correct ingesteld (Test of Live)?
* [ ]  Is het API Token ingevuld?
* [ ]  Geeft de knop **Test API Token Connection** een succesmelding?

---

### Innosend – Pickup Points in de checkout

**Verzendmethode**
* [ ]  Is de verzendmethode "Innosend Pickup Points" zichtbaar in de checkout?
* [ ]  Worden er afhaalpunten geladen nadat het verzendadres is ingevuld?
* [ ]  Wordt er automatisch een afhaalpunt geselecteerd (dichtstbijzijnde)?
* [ ]  Wordt de naam en het adres van het geselecteerde afhaalpunt getoond?

**Modal**
* [ ]  Opent de modal bij het klikken op "Wijzigen" / "Selecteer afhaalpunt"?
* [ ]  Worden er meerdere afhaalpunten in de lijst weergegeven?
* [ ]  Wordt de afstand tot elk afhaalpunt getoond?
* [ ]  Worden de openingstijden per afhaalpunt getoond?
* [ ]  Worden de carrier-logo's correct weergegeven?

**Kaart (indien ingeschakeld)**
* [ ]  Wordt de kaart correct geladen (geen lege of geblokkeerde kaart)?
* [ ]  Zijn er markers zichtbaar op de kaart voor de afhaalpunten?
* [ ]  Opent er een popup bij het klikken op een marker?
* [ ]  Past de kaart zich aan bij het selecteren van een ander afhaalpunt?

**Selectie**
* [ ]  Kan een klant een ander afhaalpunt selecteren in de lijst?
* [ ]  Kan een klant een afhaalpunt selecteren via de kaart?
* [ ]  Wordt de selectie opgeslagen na het sluiten van de modal?
* [ ]  Wordt het geselecteerde afhaalpunt meegenomen in de orderbevestiging?

**Meerdere carriers (indien geconfigureerd)**
* [ ]  Worden afhaalpunten van alle geconfigureerde carriers getoond (bijv. DHL, PostNL)?
* [ ]  Kan er gefilterd worden per carrier?

---

### Innosend – Pickup Point na bestelling

**Bevestigingsmail**
* [ ]  Staat het afhaalpunt vermeld in de orderbevestigingsmail aan de klant?
* [ ]  Worden de naam en het adres van het afhaalpunt correct weergegeven in de mail?

**Admin – orderoverzicht**
* [ ]  Is het geselecteerde afhaalpunt zichtbaar in de orderdetailpagina in de admin?
* [ ]  Worden de naam, carrier en het adres van het afhaalpunt correct weergegeven?

**Factuur / pakbon**
* [ ]  Staat het afhaalpunt vermeld op de PDF-factuur?
* [ ]  Staat het afhaalpunt vermeld op de pakbon?

---

### Innosend – Order synchronisatie

* [ ]  Verschijnt de testbestelling in het [Innosend Dashboard](https://dashboard.innosend.eu)?
* [ ]  Zijn de ordergegevens correct (klantgegevens, producten, bedrag)?
* [ ]  Is het geselecteerde afhaalpunt zichtbaar bij de order in het dashboard?
* [ ]  Wordt de orderstatus bijgewerkt in Magento nadat deze in Innosend is verwerkt?
* [ ]  Worden er trackinggegevens gesynchroniseerd nadat het pakket is verzonden?

---

### Admin

**Bestellingen**
* [ ]  Wordt de bestelling goed weergegeven?
* [ ]  Kun je de Cropped Image ophalen in de bestelling?
* [ ]  Staat het Innosend-afhaalpunt zichtbaar in de orderdetails?
* [ ]  Worden Innosend-gerelateerde gegevens correct meegenomen in de factuur?
