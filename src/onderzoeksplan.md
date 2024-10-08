# Onderzoeksplan

Lees en volg de [workshop-prompt-engineering](https://minordevops.nl/week-5-slack-ops/workshop-onderzoeksplan-prompt-engineering.html).

Verzin o.a. een titel voor je blog, pas de folder naam hier op aan en gebruik [kebab-case](https://en.toolpage.org/tool/kebabcase).

## Hoofdvraag
Hoe kan ik Zabbix inzetten om mijn DevOps-processen te ondersteunen met efficiënte monitoring?

### Deelvragen

#### Wat is Zabbix en hoe ondersteunt het monitoring binnen een DevOps-omgeving? (Library: [Literature study](https://ictresearchmethods.nl/library/literature-study/))
Zabbix is een open-source monitoringtool die gebruikt kan worden om de prestaties, beschikbaarheid en gezondheid van IT-systemen te volgen. Het werkt zowel voor servers, netwerken, containers als applicaties, wat het perfect maakt voor een DevOps-omgeving. Door Zabbix te gebruiken, krijg je gemakkelijker inzicht in hoe goed bijvoorbeeld mijn infrastructuur presteert. Ik kan statistieken verzamelen zoals CPU-gebruik, geheugengebruik en netwerkverkeer, en deze visualiseren via dashboards.

Binnen DevOps is Zabbix cruciaal omdat het me in staat stelt om proactief te reageren op problemen. Stel dat er tijdens het uitvoeren van een nieuwe release ik een prestatieprobleem zie ontstaan, dan kan ik direct ingrijpen. Zo kan ik bijvoorbeeld een service herstarten of bijsturen in een CI/CD-pipeline zonder dat de eindgebruiker er last van kan krijgen. Monitoring is een kernactiviteit binnen DevOps, en Zabbix biedt de tools om dit efficiënt en automatisch uit te voeren.

#### Wat zijn de voor- en nadelen van Zabbix (Library: [Community Research](https://ictresearchmethods.nl/library/community-research/))
De voordelen van Zabbix zijn veelzijdig. Ten eerste is het gratis, wat voor mij belangrijk is als ik met open-source oplossingen werk. Daarnaast biedt Zabbix uitgebreide mogelijkheden om real-time gegevens te verzamelen en op maat gemaakte waarschuwingen in te stellen. Ik kan Zabbix zo configureren dat ik een melding krijg zodra er problemen ontstaan, zoals hoge CPU-belasting of netwerkproblemen. Dit stelt me in staat om snel te reageren voordat kleine problemen grote verstoringen worden.

Een ander voordeel is de schaalbaarheid. Of ik nu een klein aantal servers monitor of een hele cloudinfrastructuur, Zabbix groeit met mijn infrastructuur mee. Het biedt ook integratiemogelijkheden met verschillende DevOps-tools, zoals Jenkins, wat het veelzijdig maakt in verschillende werkprocessen.

Een nadeel kan zijn dat de initiële installatie en configuratie complex kunnen zijn, zeker als ik nog niet veel ervaring heb met monitoringtools. Het opzetten van Zabbix vereist wat technische kennis, en de leercurve kan steil zijn. Daarnaast kan de interface overweldigend zijn door het grote aantal beschikbare opties, wat het lastig maakt om meteen de juiste instellingen te vinden. Maar zodra ik het onder de knie heb, biedt Zabbix ontzettend veel waarde voor mijn DevOps-werkflow.

#### Hoe pas ik Zabbix toe in het klein & hoe stel ik dit goed in (Workshop: [Prototyping](https://ictresearchmethods.nl/workshop/prototyping/))
Om Zabbix in een kleinschalige omgeving toe te passen, begin ik met de basisinstallatie van de Zabbix-server op een enkele machine of container. Dit kan via Docker of door handmatig Zabbix te installeren op een Linux- of Windows-systeem. Vervolgens installeer ik Zabbix-agents op de systemen die ik wil monitoren. Deze agents sturen gegevens zoals CPU-gebruik, geheugengebruik en netwerkactiviteit naar de Zabbix-server.

In een kleinere opzet is het belangrijk om de configuratie zo simpel mogelijk te houden. Ik start met het monitoren van de meest essentiële systemen, zoals de belangrijkste servers of netwerken. Via de webinterface van Zabbix kan ik eenvoudig standaard templates gebruiken die al zijn geconfigureerd voor veelvoorkomende systemen. Zo hoef ik niet alles handmatig in te stellen, wat de drempel verlaagt om Zabbix snel te implementeren.

Daarnaast stel ik eenvoudige triggers in, bijvoorbeeld een melding als het CPU-gebruik van een server boven een bepaald percentage komt. Dit geeft mij een eerste indruk van hoe Zabbix meldingen stuurt en hoe ik snel kan reageren op incidenten. In de loop van de tijd kan ik de monitoring uitbreiden door meer systemen toe te voegen en de configuratie te verfijnen.

#### Hoe integreer ik Zabbix in mijn DevOps-werkflow? (Workshop: [Prototyping](https://ictresearchmethods.nl/workshop/prototyping/) OF Library: [Literature study](https://ictresearchmethods.nl/library/literature-study/)))
Om Zabbix te integreren in mijn DevOps-werkflow, begin ik met het installeren van de Zabbix-server en agents op de systemen die ik wil monitoren. Zabbix-agents sturen continu prestatiegegevens terug naar de Zabbix-server, waar ik deze informatie via een dashboard kan bekijken.

Een belangrijk onderdeel van mijn werkflow is het instellen van automatische triggers en meldingen. Ik configureer Zabbix om me te waarschuwen wanneer een bepaalde drempelwaarde wordt overschreden, bijvoorbeeld wanneer het CPU-gebruik boven 80% komt. Op die manier kan ik meteen reageren op problemen en deze oplossen voordat ze kritieke processen beïnvloeden.

Verder kan ik Zabbix integreren met andere tools die ik al gebruik, zoals Jenkins, Ansible of Slack. Door bijvoorbeeld Zabbix in te stellen om berichten te versturen naar Slack, krijg ik real-time meldingen in ons teamcommunicatiekanaal. Dit maakt het gemakkelijk om snel actie te ondernemen bij incidenten.

Tot slot stel ik Zabbix-dashboards in voor verschillende teamleden, zodat iedereen binnen mijn DevOps-team toegang heeft tot relevante informatie. Hiermee kan ik ervoor zorgen dat iedereen overzicht houdt over de status van de systemen, of dat nu ontwikkelaars zijn, systeembeheerders, of netwerkingenieurs.

