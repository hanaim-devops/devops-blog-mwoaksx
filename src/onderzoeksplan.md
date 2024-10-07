# Onderzoeksplan

Lees en volg de [workshop-prompt-engineering](https://minordevops.nl/week-5-slack-ops/workshop-onderzoeksplan-prompt-engineering.html).

Verzin o.a. een titel voor je blog, pas de folder naam hier op aan en gebruik [kebab-case](https://en.toolpage.org/tool/kebabcase).

## Hoofdvraag
Hoe kan ik Zabbix inzetten om mijn DevOps-processen te ondersteunen met efficiënte monitoring?

### Deelvragen

#### Wat is Zabbix en hoe ondersteunt het monitoring binnen een DevOps-omgeving? (Library: [Literature study](https://ictresearchmethods.nl/library/literature-study/))
Zabbix is een open-source monitoringtool die gebruikt kan worden om de prestaties, beschikbaarheid en gezondheid van IT-systemen te volgen. Het werkt zowel voor servers, netwerken, containers als applicaties, wat het perfect maakt voor een DevOps-omgeving. Door Zabbix te gebruiken, krijg je gemakkelijker inzicht in hoe goed bijvoorbeeld mijn infrastructuur presteert. Ik kan statistieken verzamelen zoals CPU-gebruik, geheugengebruik en netwerkverkeer, en deze visualiseren via dashboards.

Binnen DevOps is Zabbix cruciaal omdat het me in staat stelt om proactief te reageren op problemen. Stel dat er tijdens het uitvoeren van een nieuwe release ik een prestatieprobleem zie ontstaan, dan kan ik direct ingrijpen. Zo kan ik bijvoorbeeld een service herstarten of bijsturen in een CI/CD-pipeline zonder dat de eindgebruiker er last van kan krijgen. Monitoring is een kernactiviteit binnen DevOps, en Zabbix biedt de tools om dit efficiënt en automatisch uit te voeren.

#### Wat zijn de voor- en nadelen van Zabbix ([Library: Community Research](https://ictresearchmethods.nl/library/community-research/))
De voordelen van Zabbix zijn veelzijdig. Ten eerste is het gratis, wat voor mij belangrijk is als ik met open-source oplossingen werk. Daarnaast biedt Zabbix uitgebreide mogelijkheden om real-time gegevens te verzamelen en op maat gemaakte waarschuwingen in te stellen. Ik kan Zabbix zo configureren dat ik een melding krijg zodra er problemen ontstaan, zoals hoge CPU-belasting of netwerkproblemen. Dit stelt me in staat om snel te reageren voordat kleine problemen grote verstoringen worden.

Een ander voordeel is de schaalbaarheid. Of ik nu een klein aantal servers monitor of een hele cloudinfrastructuur, Zabbix groeit met mijn infrastructuur mee. Het biedt ook integratiemogelijkheden met verschillende DevOps-tools, zoals Jenkins, wat het veelzijdig maakt in verschillende werkprocessen.

Een nadeel kan zijn dat de initiële installatie en configuratie complex kunnen zijn, zeker als ik nog niet veel ervaring heb met monitoringtools. Het opzetten van Zabbix vereist wat technische kennis, en de leercurve kan steil zijn. Daarnaast kan de interface overweldigend zijn door het grote aantal beschikbare opties, wat het lastig maakt om meteen de juiste instellingen te vinden. Maar zodra ik het onder de knie heb, biedt Zabbix ontzettend veel waarde voor mijn DevOps-werkflow.

#### Hoe integreer ik Zabbix in mijn DevOps-werkflow en hoe stel ik dit in/pas ik dit toe? ([Workshop: Prototyping](https://ictresearchmethods.nl/workshop/prototyping/))
Om Zabbix te integreren in mijn DevOps-werkflow, begin ik met het installeren van de Zabbix-server en agents op de systemen die ik wil monitoren. Zabbix-agents sturen continu prestatiegegevens terug naar de Zabbix-server, waar ik deze informatie via een dashboard kan bekijken.

Een belangrijk onderdeel van mijn werkflow is het instellen van automatische triggers en meldingen. Ik configureer Zabbix om me te waarschuwen wanneer een bepaalde drempelwaarde wordt overschreden, bijvoorbeeld wanneer het CPU-gebruik boven 80% komt. Op die manier kan ik meteen reageren op problemen en deze oplossen voordat ze kritieke processen beïnvloeden.

Verder kan ik Zabbix integreren met andere tools die ik al gebruik, zoals Jenkins, Ansible of Slack. Door bijvoorbeeld Zabbix in te stellen om berichten te versturen naar Slack, krijg ik real-time meldingen in ons teamcommunicatiekanaal. Dit maakt het gemakkelijk om snel actie te ondernemen bij incidenten.

Tot slot stel ik Zabbix-dashboards in voor verschillende teamleden, zodat iedereen binnen mijn DevOps-team toegang heeft tot relevante informatie. Hiermee kan ik ervoor zorgen dat iedereen overzicht houdt over de status van de systemen, of dat nu ontwikkelaars zijn, systeembeheerders, of netwerkingenieurs.

<!-- #### Hoe helpt Zabbix mij bij het automatiseren van monitoring in een DevOps-omgeving? (Library: [Literature study](https://ictresearchmethods.nl/library/literature-study/))
Zabbix helpt me door vrijwel alles te automatiseren wat betreft monitoring. Zodra ik Zabbix heb ingesteld, verzamelt het constant gegevens zonder dat ik handmatig hoef in te grijpen. Ik kan automatische triggers instellen die meldingen sturen bij problemen, zodat ik altijd op de hoogte ben van afwijkingen.

Daarnaast biedt Zabbix automatische escalaties. Dit betekent dat als een probleem niet binnen een bepaalde tijd wordt opgelost, het systeem automatisch een tweede waarschuwing naar een hoger niveau stuurt. Dit voorkomt dat belangrijke issues ongezien blijven. Ook helpt Zabbix me door historische data te verzamelen. Hierdoor kan ik trends analyseren en afwijkingen in patronen identificeren, wat bijdraagt aan het voorspellend vermogen van mijn monitoringproces.

Deze automatisering zorgt ervoor dat ik mijn tijd en aandacht kan richten op andere taken binnen de DevOps-cyclus, zoals het optimaliseren van de infrastructuur of het doorvoeren van nieuwe releases, terwijl Zabbix op de achtergrond de prestaties van mijn systemen in de gaten houdt. -->

#### Hoe kan Zabbix worden geïntegreerd in CI/CD-pipelines om incidentbeheer te verbeteren? (Library: [Literature study](https://ictresearchmethods.nl/library/literature-study/) & [Workshop: Prototyping](https://ictresearchmethods.nl/workshop/prototyping/))
Ik kan Zabbix integreren in mijn CI/CD-pipelines om de stabiliteit en betrouwbaarheid van mijn deployments te waarborgen. Wanneer ik een nieuwe release uitvoer, kan Zabbix continu monitoren of alle systemen goed presteren. Ik stel Zabbix zo in dat het tijdens en na de deployment controleert op problemen zoals verhoogde responstijden of uitval van services.

Bovendien kan ik Zabbix gebruiken om feedback te geven aan de pipeline zelf. Stel dat er tijdens een deployment een prestatieprobleem optreedt, dan kan Zabbix automatisch een rollback starten of een melding sturen naar de verantwoordelijke persoon. Dit maakt incidentbeheer veel efficiënter, omdat problemen tijdens de release direct worden opgespoord en opgelost.

Door Zabbix te koppelen aan tools zoals Jenkins, kan ik bijvoorbeeld een build laten falen als Zabbix detecteert dat er een probleem is met de prestaties van de applicatie in productie. Hierdoor worden fouten snel gecorrigeerd voordat ze impact hebben op de eindgebruiker. Deze integratie helpt mij om de kwaliteit van mijn applicaties hoog te houden, zelfs bij frequente releases.