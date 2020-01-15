---
name: Frontend checklist (Dynamicweb)
about: Hvad skal vi altid huske når et nyt Dynamicweb website kodes?
title: Frontend checklist
labels: ''
assignees: ''

---

# Udvikling og test

## Hosting og løsning

### Bestil løsning
- [ ] Bestil løsning hos Dynamicweb
- [ ] Bestil evt. partnerskifteerklæring hos Dynamicweb
- [ ] Bestil FTP adgang hos HostNordic

### DW indstillinger
- [ ] Login skærm: We've got your back + we@gotcha.dk
- [ ] Indstillinger: √ Disable performance comment √ Tilføj ikke base href
- [ ] Indstillinger > Item typer: Slet de items der som standard er med - vi bruget dem ikke
- [ ] Indstillinger > Web og HTTP > Brugerdefinerede URL'er - √ Placering og sidenavn
- [ ] Indstlilinger > Web og HTTP > Brugerdefinerede URL'er > Hvis et site eller flere sprog med unikke domæner: Vis ikke sproglag. Hvis flere sites på et domæne - medtag sproglag eller ISO 
- [ ] Indstillinger > Web og HTTP > Brugerdefinerede URL'er >  Hvis ét website eller flere websites med unikke domæner: Ensure unique paths for each area

## Secondary front-end test
Grundlæggende test af funktionaliteter og formularer. Ex. responsive, pagespeed, nyhedsbrevformular, søgefunktion etc. Bemærk: Design testes af designer.

### Testliste (der kan tilføjes punkter af primær front-ender)
Liste over ting 1. ønsker testet specifikt
- [ ] Tjek for console-fejl/console.logs

### Device test
- [ ] PC - IE 11
- [ ] PC - Edge 
- [ ] PC - Chrome
- [ ] PC - Firefox
- [ ] Mac - Safari
- [ ] Mac - Chrome
- [ ] Mac - Firefox
- [ ] iPhone 5/SE - Safari
- [ ] iPhone 5/SE - Chrome
- [ ] iPad - Safari
- [ ] iPad - Chrome
- [ ] Android mobil - Chrome
- [ ] Android tablet - Chrome

## Implementering inkl. løbende test
- [ ] 404 side
- [ ] Cookiebar
- [ ] Lav skabeloner af sider - med billeder fra f.eks. placehold.it, hvor billedmål står i - så kan brugeren se den størrelse de skal gemme billederne i  
- [ ] Kvittering på web + kvittering på mail ved udfyldte formularer?  
- [ ] Søgeresultatside

# Undervisning og inddatering

## Undervisning (skal filmes 🎬)

### Opgaver
- [ ] Mail med link til løsning & login oplysninger + billedeguide
- [ ] Link til løsning, login oplysninger + billedeguide
- [ ] Indsættes i mail til kunde

> Link til løsning: .by.gotcha.dk
> Brugernavn:
> Adgangskode:
> 
> Anbefaling til billeder, som uploades på websitet
> 1. Billeder på websitet skal exporteres i lavest mulige filstørrelse uden af gå på kompromis med kvalitet.
> 2. Anvendes Photoshop bruges 'Save for web' til export af billeder. Typisk vil en kvalitet på 40-60 være tilstrækkeligt uden at gå på kompromis med kvaliteten, men vi anbefaler af I selv tager stilling til dette.
> 
> Bemærk: Grunden til at filstørrelsen skal være så lav som muligt, er at hastigheden på websitet påvirkes af billedets filstørrelse. Ligeledes kan det have en negativt effekt på websitets SEO performance.

### Tjekliste
- [ ] 404 side
- [ ] Søgeresultat
- [ ] Kvitteringsside & mails ved formular 
- [ ] Privacy Policy 
- [ ] Cookie Policy
- [ ] Nyhedsbrev
- [ ] Redirects

# Website godkendelse

## Godkendelse af website hos kunde
- [ ] Redirects
    1. [ ] Lav udtræk af gamle URL'er
    2. [ ] Download URL skabelon fra løsning
    3. [ ] Kopier URL'er ind i skabelon
    4. [ ] Excel ark sendes til kunde
- [ ] Excelark modtaget fra kunde

# Launch

## TTL & SSL certifikat / Forberedelse til launch

### SSL
- [ ] Bestil SSL certifikat
- [ ] Godkend SSL certifikat via DNS

### TTL
- [ ] Sørg for at TTL for domæne(r) er sat ned til 600 sek.

## Launch

### Opsæt evt. unikke 404 sider pr. sprog
- [ ] Angiv 404-side(r) nodeId i 'Config > umbracosettings.config' (Kodeeksempel herpå findes i filen).
- [ ] Husk at 404-sider ikke virker før at 'trySkipIisCustomErrors' er sat korrekt. Gøres ifm. 'Health Check'

### Online markedsføring
- [ ] 301-redirects template udfyldt og implementeret i CMS
- [ ] Google Search Console
- [ ] Google Analytics
- [ ] Google Tag Manager

### Ændringer i config filer
- [ ] Opsæt SMTP via Mandrill for løsningen - med kundens egen email-adresse. (Sørg for at oprette en unik ApiKey for løsningen. Denne skal bruges som kodeord.  NB. Husk at aktivere API key efter oprettelsen - denne vil automatisk være inaktiv (snyder dog UI-mæssigt).
- [ ] Opsæt clientCache I web.config (Tilføj følgende linje under "system.webServer" > "staticContent" i web.config.)
- [ ] Slå test fra på Gotcha Redirect Module (redirectModuleDebugMode) (Sæt'redirectModuleDebugMode' i AppSettings i web.config til true, således der fortages 301 redirects i stedet for 302).
- [ ] Tilføj 'enforce-trailing-slash' rewrite-regel (Tilføj rewrite-regel i web.config under 'system.webServer'. Se vedlagte fil med kode-stump.  Reglen sørger for altid at tilføre en '/' i URLen.)
- [ ] Opsæt URL-regler (URL-regler som sørge for at (301) redirecte korrekt til primærtdomæne.  Eksempelvis:  Force HTTPS Redirect altid til www Medtag sti (efter domæne) i redirectet)
- [ ] Ændre afsender for Umbraco notifkationer (kundens mail-adresse) (Dette gøres i 'Config/umbracoSettings.config' under 'content > notifications > email')

### Diverse
- [ ] Opsæt URL-regler (URL-regler som sørge for at (301) redirecte korrekt til primærtdomæne.  Eksempelvis:  Force HTTPS Redirect altid til www Medtag sti (efter domæne) i redirectet)
- [ ] Developer > Health Check: Lav en test og fjern eventuelle fejl - Debug = false?
- [ ] Undgå duplicate-content på 'forside' (Hvis vi bruger 'umbracoInternalRedirectId' til forsiden, så sørg for at tilføje en 'umbracoUrlName' med værdien '/' på forsiden.)

### Tilføj domæner (hostnames)
- [ ] TIlføj hostnames i Umbraco backoffice
- [ ] Er der tilføjet binding på website i IIS'en?
- [ ] Peg domæne(r) ind på server

### SSL
- [ ] Har kunden SSL-certifikat og kan det flyttes? (efter launch)