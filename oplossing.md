Vul onderstaande aan met de antwoorden op de vragen uit de readme.md file. Wil je de oplossingen file van opmaak voorzien? Gebruik dan [deze link](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) om informatie te krijgen over
opmaak met Markdown.


a) 
Via ssh hebben we een connectie gemaakt tussen Jenkins & Github, waarna we een fork maakten van de calculcator app en de broncode binnenhalen in de pipeline.
Dit deden we door middel van de github credentials die we in Jenkins hadden toegevoegd.


![Screenshot 2024-12-12 095539](https://github.com/user-attachments/assets/127eff32-12ec-414d-9e41-0dcb53389662)
![Screenshot 2024-12-12 094740](https://github.com/user-attachments/assets/b94935c0-ba20-4797-bcfc-b447955cd4c4)
![Screenshot 2024-12-12 094628](https://github.com/user-attachments/assets/cf482dff-cb79-48bf-9e4a-8332d636c3cf)
![image](https://github.com/user-attachments/assets/4c35c08b-0437-4f27-ba16-ee1dd4a7d0d8)


b)
Na het installeren van de NodeJs plugin, konden we bij tools een NodeJS installation toevoegen, genaamd TINnode-devops.
Hiermee gebruikte we de laatste beschikbare LTS versie van NodeJS.

![NodeSetup](https://github.com/user-attachments/assets/7136df6a-ce0f-475d-9984-09e6d00ec719)
![RunNodeJS](https://github.com/user-attachments/assets/38c4ace3-c959-4feb-b136-7e34eddce33c)


c)
Na het binnenhalen van de broncode installeren we alle benodigde NodeJS dependencies met npm install.
Vervolgens runnen we de tests met npm test en wordt een JUnit rapport gegenereerd en gekoppeld aan de build.
We maken een map bundle aan waarin we enkel de noodzakelijke bestanden voor de werkende app in kopieren.
Deze wordt gecromprimeerd naar een .zip bestand en als artifact gearchiveerd.
Als de pipeline zou falen, wordt een foutmelding met datum en tijd geschreven naar een bestand jenkinserrorlog in de homefolder.
De build kan meermaals na elkaar succesvol uitgevoerd worden.

![Testresults](https://github.com/user-attachments/assets/a7dd64fd-be25-4c89-9c87-87358e36a60c)
![MultipleBuilds](https://github.com/user-attachments/assets/5bd7124c-cf13-4f64-afbb-3a1e2595cc39)
![Bundle+tests](https://github.com/user-attachments/assets/0b3b4248-fb69-47f7-a5b7-f9f6beb198d0)



d)
