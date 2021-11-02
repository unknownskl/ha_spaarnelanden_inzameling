Een sensor component voor het ophalen (scrapen) van informatie van https://inzameling.spaarnelanden.nl/, voor Home Assistant.

Handleiding:
- Zoek je container nummer op op https://inzameling.spaarnelanden.nl/ en vul deze in tussen de quotes achter CONTAINER_NUMBER in sensor.py
- Kopieer const.py, manifest.json en sensor.py naar een directory spaarnelanden_inzameling in de custom_components directory van Home Assistant
- Zet in de Home Assistant configuration.yaml, onder sensor: "- platform: spaarnelanden_inzameling" (of in bijvoorbeeld sensor.yaml)
- Herstart Home Assistant
- Win?

Opmerkingen:
- Dit is het eerste en enige wat ik ooit in elkaar heb geklust in Python. *Alle verbeteringen zijn welkom, deel ze hier met mij!*
- In sensor.py staat een variabele CONTAINER_NUMBER, dis is het nummer wat je kunt vinden als 'Nummer' van jouw container op https://inzameling.spaarnelanden.nl/
- De webpagina die wordt opgehaald is groot (10MB ongeveer dacht ik?), doe het niet te vaak. De variabele TIME_BETWEEN_UPDATES bewaakt dit, en staat op 10 minuten.

Known issues:
- Als Home Assistant start, is er nog geen info van de sensor en staat deze op 'Unknown'. 
- Configuratie gaat in de sensor.py file, niet via de Home Assistant configuratie.
- Alleen getest met mijn eigen ondergrondse restafval-container.