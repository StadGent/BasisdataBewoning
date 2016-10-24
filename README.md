# BASISDATA BEWONING
This repository contains a series of FME workspaces for the data processing of the authentic data sources Belgian Cadastre, Central Reference Address Database (CRAB) and the Civil registry of a municipality. This data processing results in a set of secondary data sources which can be used by Flemish local governments to conduct (geographical) analyses on habitation, construction and property in the municipality. 

Het dataproces Basisdata Bewoning bestaat uit opeenvolgende FME-processen die lokale besturen toelaten uit de basisdata van het Kadaster, het Centraal Referentie Adressenbestand (CRAB) en het gemeentelijk Bevolkingsregister, afgeleide datasets te genereren die informatie bevatten in verband met bewoning, bebouwing en eigendommen.  Het resultaat van het dataproces bestaat uit 7 afgeleide databronnen die via unieke sleutels aan elkaar kunnen worden gekoppeld.  Deze afgeleide datasets kunnen worden gebruikt voor (geografische) analyses en het genereren van statistieken en tabellen die een antwoord geven op vragen zoals "hoeveel kinderen van 6 t.e.m. 12 jaar wonen in een huis in open bebouwing?", "hoeveel wooneenheden in flatgebouwen of buildings bevinden zich binnen 400m loopafstand van een bepaalde voorziening (bvb. park)?", "hoeveel woningen in een bepaalde wijk dateren van voor 1960 en worden bewoond door de eigenaar(s)?". 

## Privacy
Zowel de originele databronnen als de resulterende datasets kunnen vertrouwelijke informatie bevatten. Bij gebruik van dit dataproces en de resulterende datasets moet worden rekening gehouden met de geldende wetgeving en de vereiste bevoegdheden m.b.t. de bescherming van de privacy.

## Hergebruik
<p xmlns:dct="http://purl.org/dc/terms/">
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">
<img alt="Creative Commons-Licentie" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a>
<br />
Dit werk (<span property="dct:title">Dataproces Basisdata Bewoning</span>, by <span resource="[_:creator]" rel="dct:creator"><span property="dct:title">Stad Gent</span></span>) valt onder een <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Naamsvermelding-NietCommercieel-GelijkDelen 4.0 Internationaal-licentie</a>.
</p>

## Werkwijze
1.	Zorg dat je beschikt over een recente versie van FME (2016.1.1 of later). Een gratis 1 maand testlicentie kan je downloaden via <http://www.safe.com/>
2.	Cre&euml;er een folder waarin het dataproces kan worden geplaatst (bvb . *C:\mijnfoldernaam*). Cre&euml;er in deze folder twee subdirectory&apos;s *fme* en *data*. Cre&euml;er binnen de folder data nog een subdirectory *input*. 
3.	Download alle FME workspaces (.fmw) en plaats ze in de folder *\fme*. 
4.	Verzamel de bronbestanden en schrijf ze naar de folder *\data\input*. Gebruik hiervoor de FME workspace 000_BEW_InputDataMapping.fmw. Op die manier bevatten de bronbestanden de juiste namen en datastructuren die noodzakelijk zijn voor het verdere proces. In [ExampleData_fictive.zip](ExampleData_fictive.zip) vind je fictieve voorbeelddata met de gebruikte datastructuren. Meer info over de bronbestanden vind je onder Bronbestanden in [DOCUMENTATIE_BasisdataBewoning.pdf](DOCUMENTATIE_BasisdataBewoning.pdf). Houd steeds rekening met de toestandsdatum van de bronbestanden. 
 * BevReg_extr.csv
 * CRAB_RijksregisterStraat.shp
 * CRAB_Percelen_Centerpoints.shp
 * huisnummer.csv
 * subadres.csv
 * adrespositie.csv
 * straatnaam.csv
 * postkantoncode.csv
 * B_CaPa.shp
 * KADlegger_owner.csv
 * KADlegger_parcel.csv
5.	Open de FME workspace BATCH_BEW.fmw. 
6.	Bepaal parameters:
 * Toestand: geef de toestandsdatum (%Y%m%d)
 * GeolocatorRequestURL (optioneel): geef hier de url van de geolocator request (samenstelling volledige request, zie 001_BEW_BevolkingsReg_CRAB.fmw)
 * municipality: geef hier de naam van de gemeente (zoals weergegeven in de eigenaarsadressen in KADlegger_owner.csv)
 * language: geef hier de taal van de gemeentenaam 
7.	Start het proces. De resultaten bevinden zich na afloop in de folder *\data\output*. 

##Metadata
Uitgebreide informatie over de databronnen, dataprocessen, resulterende datasets en variabelen vind je in [DOCUMENTATIE_BasisdataBewoning.pdf](DOCUMENTATIE_BasisdataBewoning.pdf)
