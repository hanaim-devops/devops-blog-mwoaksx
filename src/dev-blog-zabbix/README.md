# Hier komt de titel van je blog

<img src="plaatjes/Zabbix_logo_square.svg.png" width="250" align="right" alt="Zabbix Logo" title="Zabbix Logo">

*[Max van Oostwaard, oktober 2024.](https://github.com/hanaim-devops/devops-blog-mwoaksx)*
<hr/>

Monitoring is een van de cornerstones van een succesvol DevOps-proces. Zonder goede monitoring is het lastig om de prestaties en beschikbaarheid van systemen te waarborgen, wat kan leiden tot downtime of prestatieproblemen die de eindgebruiker direct beïnvloeden. 

Monitoring en de tools hiervan bieden realtime controle aan, van planning tot productie, en helpt teams snel te reageren op problemen door middel van geautomatiseerde waarschuwingen en geavanceerde visualisaties om zo het hierboven gestelde probleem te voorkomen. Het stelt developmentteams in staat om tijdig fouten te detecteren en te behandelen, wat grote problemen op omgevingen vermindert en de gebruikerservaring verhoogt (Sai, z.d.).

In deze blogpost neem ik je mee in een diepere duik op een specifieke monitoringtools genaamt Zabbix en wat deze is, hoe het je kan helpen om je systemen effectief te monitoren, en hoe je het kunt integreren in je DevOps-werkflow. Of je nu servers, databases, applicaties of netwerken moet monitoren, Zabbix biedt een veelzijdige oplossing die je processen slimmer en efficiënter maakt.

## Kort over Zabbix
Zabbix is een krachtige, open-source monitoringtool die wordt gebruikt om de prestaties, beschikbaarheid en veiligheid van IT-infrastructuren te bewaken. Of je nu de gezondheid van servers, netwerken, containers, databases of applicaties wilt monitoren, Zabbix biedt de benodigde tools om dit te doen.

Een van de belangrijkste voordelen van Zabbix is dat het gegevens in real-time kan verzamelen. Dit betekent dat zodra een bepaalde drempelwaarde (bijvoorbeeld CPU-gebruik) wordt overschreden, Zabbix meteen een melding kan sturen. Je kunt dashboards configureren waarin je de verzamelde statistieken kunt visualiseren en bekijken. Zo kun je bijvoorbeeld in één oogopslag zien hoe goed je infrastructuur presteert en snel ingrijpen als er problemen of fouten zijn.

Zabbix ondersteunt niet alleen standaard IT-componenten zoals CPU, geheugen en netwerkverkeer, maar kan ook worden uitgebreid om applicatiespecifieke metrics te monitoren. Denk aan databasequery's of het gedrag van een specifieke microservice binnen een grotere applicatie.

In een DevOps-omgeving is Zabbix een cruciale tool omdat het je de mogelijkheid geeft om proactief te handelen. Stel dat je in het midden van een nieuwe release zit en ziet dat het geheugenverbruik te hoog wordt, dan kun je onmiddellijk actie ondernemen. Dit soort problemen vroegtijdig detecteren helpt bij het voorkomen van downtime en prestatieproblemen, wat essentieel is voor het behouden van een soepele gebruikerservaring.

Concrete monitoringtoepassingen in Zabbix:

- Servers (CPU-gebruik, geheugengebruik, schijf I/O, etc.)
- Netwerken (verkeersanalyse, pakketverlies)
- Applicaties (beschikbaarheid en prestaties van services)
- Databases (query-latenties, connecties, opslaggebruik)

## Voor- en nadelen van Zabbix
Nu we weten wat Zabbix is, is het belangrijk om te kijken naar de voor- en nadelen van deze tool, en hoe het zich verhoudt tot andere monitoringtools.

De voordelen van Zabbix:

- Gratis en Open-source: Zabbix is volledig gratis en open-source, wat betekent dat je geen licentiekosten hoeft te betalen. Dit is ideaal voor kleine bedrijven of teams met een beperkt budget die toch een robuuste oplossing nodig hebben.

- Schaalbaarheid: Zabbix is zeer schaalbaar, waardoor het geschikt is voor zowel kleine IT-infrastructuren als grote ondernemingen. Het kan kleine tot aan grootschalige systemen/applicaties monitoren en kan er tot duizenden tegelijk doen zonder dat de prestaties er aan lijden.

- Real-time Monitoring: Met Zabbix kun je real-time gegevens verzamelen en analyseren, wat je de mogelijkheid geeft om direct in te grijpen bij problemen.

- Extreem aanpasbaar: Of je nu rapportages, dashboards of meldingen wilt aanpassen, Zabbix biedt een hoge mate van flexibiliteit. Je kunt triggers instellen die specifieke acties uitvoeren wanneer bepaalde drempelwaarden worden overschreden.

- Integraties met andere tools: Zabbix integreert goed met andere tools die veel worden gebruikt in DevOps, zoals Jenkins, Ansible, en Slack. Hierdoor kun je meldingen ontvangen, automatisch tests starten, of bepaalde taken automatiseren.

Zabbix kan bijvoorbeeld vergeleken worden met tools als Nagios, Prometheus of Datadog. Waar Nagios ook een populaire tool is voor monitoring, is het meer gericht op eenvoudige setups en heeft het minder aanpassingsmogelijkheden dan Zabbix. Prometheus, daarentegen, wordt vaak geprezen om zijn eenvoud en focus op metrics, maar het mist de geavanceerde triggers en meldingen van Zabbix. Datadog is een commerciële oplossing die zich richt op grote bedrijven, maar de kosten kunnen snel oplopen, terwijl Zabbix een gratis alternatief biedt met vergelijkbare functies.

De nadelen van Zabbix:

- Complexe Configuratie: Zabbix is voor een beginner erg lastig op te pakken. Zabbix is over het algemeen moeilijk op te zetten, vooral als je niet veel ervaring hebt met monitoringtools. Het installeren en configureren van Zabbix vereist technische kennis en een goed begrip van je infrastructuur.

- Steile leercurve: De vele opties en functies in Zabbix maken het een krachtig platform, maar dat betekent ook dat de leercurve steil kan zijn, vooral voor beginners. Het kan even duren voordat je gewent raakt & voldoende kennis hebt over alle opties, functies en instellingen.

- Interface: De interface van Zabbix is functioneel maar minder intuïtief dan die van commerciële oplossingen zoals Datadog of Grafana, vooral voor gebruikers die gewend zijn aan meer moderne UI’s.

## Monitoren met Zabbix

Zabbix biedt dus mogelijkheid om infrastructuren en systemen erg breetd te monitoren. Om hier een kleine visualisatie van te geven, geef ik een praktisch voorbeeld over hoe je Zabbix kunt inzetten om je localhost te monitoren.

Maar waarom localhost? Een monitoringtool zoals Zabbix draait eigenlijk altijd op een server en kan vanaf daar verschillende infrastructuren & systemen in de gaten houden. Maar wat als je, net zoals ik, geen toegang hebt tot een server? Dan wordt het lastig om de gezondheid en prestaties van deze systemen bij te houden. Gelukkig kun je ook je localhost monitoren met Zabbix! Aangezien elk apparaat over een localhost beschikt, is dit een ideale vervanging voor een echte server. Dit is ook een eenvoudige manier om kort in aanraking te komen met Zabbix

### Zabbix opzetten

Om te beginnen, heb ik voor het gemak er voor gekozen om Zabbix te runne via Docker Compose. Dit zorgt er voor dat je Zabbix niet lokaal hoeft te instaleren. 

Clone repo: git clone https://github.com/zabbix/zabbix-docker.git
Als het goed is, zit je al in de juiste en de nieuwste versie (7.0). Maar laten we toch even er naartoe switchen: git checkout 7.0

Wat je zojuist hebt binnengehaald is de github repository van Zabbix waar alle Docker Compose files, dockerfiles en enviroment variabele staan. Deze zijn kant en klaar voor gebruik waardoor we zelf niks meer hoeven te doen! Natuurlijk als je dit wel zelf zou willen aanpassen, dan zal je de juiste Docker Compose file & de bijbehorende dockerfiles & enviroment variabele moeten kopieëren naar je eigen project.
Zoals je ook kan zien zijn er aardig wat Docker Compose bestanden aanwezig. Deze bestanden zijn allemaal gemaakt om Zabbix net weer wat anders te runnen. Dit kan je ook zien aan de bestandsnamen. De naamgeving van de bestandsnamen bestaan uit 4 onderdelen. Deze zullen we even ontleden om het wat duidelijker te laten zien. Laten we als voorbeeld de Compose file ontleden die we ook gaan gebruiken dadelijk:
`docker-compose_v3_alpine_mysql_latest` bestaat uit de volgende 4 onderdelen:
- `docker-compose_v3`: Dit is de versie van de Docker Compose waarvan gebruikt gemaakt wordt, in dit geval Docker Compose 3
- `alpine`: De linux versie van de container waarop de docker-services gaan draaien. In dit geval is dit Alpine-linux
- `mysql`: Welke database geondersteund wordt & wordt gekoppeld aan Zabbix om data van Zabbix op te slaan. In dit geval wordt er gebruikt gemaakt van een MySQL database
- `latest`: Welke versie alle servies moeten zijn, dit zal hier dus altijd de laatste en nieuwste versie zijn. De andere optie is `local`. [Leg uit wat dit doet]

Daarna gebruik je dit Docker Compose commando om Zabbix op te starten:
docker compose -f ./docker-compose_v3_alpine_mysql_latest.yaml --profile full up

Dit Docker Compose commando heeft 2 opties waar we vooral op moeten letten:
- `-f` optie: Hier geef je de gewenste Docker Compose file mee
- `--profile` optie: Kan niks, `full` of `all` zijn. [Korte uitleg over docker profiles]

Het pullen, builden, runnen en initaliseren van deze images kan eventjes duren aangezien je nu best aardig wat binnenhaalt. Als eenmaal alles is binnengehaald kan je even snel checken of alles is goedgegaan via Docker Desktop. Het moet er dan ongeveer als volgend uit moeten zien:

[Screenshot van Docker Desktop wanneer alles runt]

De containers die je hier allemaal ziet zijn niet allemaal even belangrijk voor dit voorbeeld. Daarom hieronder even een korte uitleg van de containers die voor ons van belang zijn:
- [Uitleg van containers (Optioneel)]

Ga naar localhost:80 en zie hiet het hoofdscherm van Zabbix. Gefeliciteerd, je bent voor het eerst in aanraking gekomen met Zabbix! Er staat al van alles op je scherm, gelukkig hoef je hier (nog) niet aan te komen.

### Aanmaken van een Hosts
We moeten er nu eerst voor zorgen dat Zabbix ook echt wat gaat doen, wat in dit voorbeeld dis het monitoren van de localhost is. Een infrastructuur, systeem, applicatie, etc. binnen in Zabbix heet een host. Deze moeten we eerst aanmaken voordat we uberhaubt wat kunnen doen. Via de zijbalk gaan we naar `Datacollection` -> `Hosts`. Dit scherm is er voor om al je hosts te kunnen bewerken, aanmaken en verwijderen.

Zoals je kan zien staat er al een hosts ingestelt. Dit is een host die automatisch staat ingestelt met Zabbix. Deze mag je negeren of zelfs verwijderen. Een nieuwe host aanmaken kan via de knop rechtsboven in het scherm

[Uitleg over hoe je de host instelt & dat ie kijkt naar de Zaabbix-agent]

Het kan een tijdje duren voordat de host is opgepikt door Zabbix, maar uiteindelijk moet het `Availability` vakje groen zijn, dit kan dus even duren. Als dit zo is, kan je navigeren naar `Monitoring` -> `Hosts` en klik je daar op de zojuist aangemaakte hosts en kies je de optie `Graphs`. Hier zie je veel verschillende grafieken waar gebeurtenissen bijgehouden worden van je localhost. Een goed voorbeeld om te kunnen zien of het werkt is de grafiek `CPU usage`. Dit is de grafiek om het CPU gebruik van de host te zien. Start bijvoorbeeld eens een paar nieuwe docker containers op terwijl je Zabbix draait. Dan zul je zien dat de grafiek op het moment wanneer de containers gebuild en gerunt worden een stuk omhoog schiet. Natuurlijk is dit een voorbeeld en kan je ook kijken naar de vele andere grafieken die Zabbix toont.

[Kleine afsluiting met wat je zojuist gedaan hebt. Sammenvatting soort van]

## Waarom Zabbix binnen DevOps workflow's
[Uitleggen waarom je Zabbix zou willen intregregen in je DevOps workflow en welke opties je hebt om dit voor elkaar te krijgen]

## Conclusie (optioneel)
[Conclusie geven over de tool Zabbix]

## Bronnen
- Sai, K. S. (z.d.). DevOps-Monitoring | Atlassian. Atlassian. https://www.atlassian.com/nl/devops/devops-tools/devops-monitoring

https://www.zabbix.com/documentation/current/en/manual/introduction/features (voor voor & nadelen)

https://docs.docker.com/compose/how-tos/profiles/ (Kort vertellen over profiles in docker)

https://github.com/zabbix/zabbix-docker/blob/7.0/docker-compose_v3_alpine_mysql_latest.yaml (Link naar github docker compose)

<!-- Installeer de aangeraden [mdlint](https://github.com/DavidAnson/markdownlint). Voeg je eerste plaatje en bronnen in.  -->