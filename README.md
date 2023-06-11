# LOS_to_CSV
A powershell code that creates a Windows Form to get data from a LOS excel file and export relevant data to CSV files

Dette PowerShell-script, LOSGUI.ps1, er designet til at automatisere konverteringsprocessen af data fra en LOS-fil (en Excel fil der benyttes til håndtering af organisationsændringer) til CSV (Comma-Separated Values) filer. Scriptet leverer en intuitiv og brugervenlig grafisk brugerflade (GUI), der gør det let for brugere uden erfaring med PowerShell at interagere med og drage fordel af konverteringsfunktionaliteten.

Når scriptet startes, åbnes en brugervenligt grafisk brugerflade (GUI), der præsenterer forskellige elementer og interaktive komponenter til brugeren. En væsentlig del af GUI'en er "Vælg LOS ark" knappen, der giver brugeren mulighed for at vælge en LOS-fil fra deres lokale filsystem. Når brugeren klikker på " Vælg LOS ark " knappen, åbnes en dialogboks, hvor de kan navigere til og vælge den ønskede LOS-fil. Filens placering vises derefter tydeligt i et tekstfelt på GUI'en, hvilket giver brugeren visuel bekræftelse på, at den korrekte fil er valgt.

Ved valg af LOS-filen bliver destinationen og navnet på de/den CSV-fil, der skal genereres som resultat af konverteringen, automatisk bestemt. Dette gøres ved at bruge værdier fra de relevante faner i LOS arket. 
Når LOS-filen er indlæst, kan brugeren trykke på "Eksporter CSV" knappen for at starte konverteringsprocessen. Dette udløser en sekvens af PowerShell-kode, der styrer selve konverteringen og inkluderer også robust fejlhåndtering for at sikre en pålidelig udførelse af scriptet.

Scriptet implementerer fejlhåndtering ved hjælp af try-catch-funktionen i PowerShell. Hver handling i konverteringsprocessen er omgivet af en try-blok, der overvåger eventuelle undtagelser eller fejl, der kan opstå. Hvis en fejl opstår, fanges den af catch-blokken, og scriptet udfører passende handlinger for at håndtere fejlen og give brugeren relevante oplysninger.
Under konverteringsprocessen kontrollerer scriptet nøje de nødvendige filstier og sikrer, at både LOS-filen og den ønskede CSV-fil kan tilgås og oprettes. Hvis en sti til en fil ikke er gyldig eller der opstår problemer med at åbne eller oprette filer, fanges fejlen af catch-blokken. Brugeren informeres om fejlen via en advarselsmeddelelse på GUI'en, og konverteringen afbrydes for at undgå yderligere problemer.
Under læsning og analyse af LOS-filen kontrollerer scriptet også, om de nødvendige sektioner, nøgleværdier og attributter eksisterer og er gyldige. Hvis der opstår manglende eller ugyldige data under analysen, håndteres det af catch-blokken, og brugeren informeres om problemet.
Når konverteringsprocessen er fuldført uden nogen fejl, vises en meddelelse på GUI'en for at informere brugeren om, at konverteringen er afsluttet. Brugeren kan nu trykke på "Åben Mappe" knappen for at komme direkte til de oprettet CSV filer. Brugeren kan også vælge at trykke på ”Luk” knappen for at lukke GUI'en og arbejde med den genererede CSV-fil, der indeholder konverterede data fra LOS-filen.