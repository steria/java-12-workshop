# java-12-workshop
Oppgavene tar for seg litt av det som er nytt i java9, 10, 11 og 12.

Oppgavene er delt inn i to deler, der den første anbefales utført i IntelliJ, mens den andre anbefales utført i JShell.  Du står fritt til å hoppe mellom deler- og oppgaver som du ønsker. 

Merk at Git bash ikke anbefales for jshell-oppgaver, men kan benyttes ved å kjøre "winpty jshell".

NB! Har du en settings.xml som er endret for å fungere for prosjektet ditt? Da bør du endre tilbake til standard settings.xml.

Javadoc:

* https://docs.oracle.com/javase/9/ 
* https://docs.oracle.com/javase/10/ 
* https://docs.oracle.com/en/java/javase/11/ 
* https://docs.oracle.com/en/java/javase/12/ 

Skulle du bli ferdig med resten av oppgavene, så oppfordrer vi til at du leter frem informasjon om endringer selv, og prøver ut noe du synes virker interessant. 

# Del 1 (IntelliJ)
## Oppgave 1-4 ligger under modules folderen
Her ligger den en run.sh i hver av oppgavene, disse kan enten kjøres direkte eller så kan kommandoene i filen kjøres hver for seg. Merk at mkdir kanskje er unødvendig da.
## Oppgave 5 - Http2 client (Java 9/11)
## a)
Ferdigstill implementasjon av DovreKlient slik at svaret på hvorvidt dovre har falt hentes vha den nye Http2-klienten vha synkrone kall mot http://www.vondess.com/dovre/api. 
Link til [Javadoc](https://docs.oracle.com/en/java/javase/11/docs/api/index.html)

## b)
Endre klienten fra oppgave _a)_ til å være asynkron.
Legg inn _Thread.sleep(5000)_ før du sjekker om det har kommet respons.

NB! Husk å kansellere requestet hvis det ikke har kommet respons. 

## Oppgave 6 - Private methods i interfacer (Java 9)

## a)
Få testene i _DemoInterfaceTest.java_ til å gå grønt uten å utvide interface med nye metoder.

## Oppgave 7 - Local variable type inference (Java 10)

* Ta en kikk på eksempelklassen, og forsøk å endre deklarasjon til var.

* Gitt overstående - gjør deg selv noen tanker om den nye variablen 
    ** Hvordan kan dette påvirke lesbarhet av koden?
    ** Hva er din mening om denne endringen? 

## Oppgave 8 - Switch expressions (Java 12)

* Endre implementasjonen slik at testen bygger grønt. 
* Skriv om til bruk av switch expression

## Oppgave 9 - Timeunit conversion (Java 11)

* Fiks implementasjonen slik at testen bygger grønt vha en oneliner 

# Del 2 (JShell) 

## Oppgave 1 - JShell (Java 9)

 * Start opp jshell
 * Skriv inn "Hello, World!" og trykk enter.
 * Print "Hello, World!" ved å bruke $1. 
 * Modifiser variablen til "JShell - Hello, World!". 
 * Definer til en navngitt streng som innehar samme tekst (ved å assigne verdi fra variablen).  
 * Finn verdien av 151230951 + 502801459 i jshell
 
 Observer at semikolon ikke er nødvendig i JShell (når man er i ren jshell-context).  

## Oppgave 2 - Endringer i Collections- og Stream-API (Java 9)

### a)

* Lag en liste med navn i jShell vha Collection Factory-metoder (Se f.eks List. <tab>, eller finn frem i javadoc) 
* Forsøk å legg til et nytt element i listen
    Observer at collections opprettet via Collection Factory-metoder er immutable. 
* Lag et Set og et Map


### b)

Bruk dropwhile, takewhile og utfør følgende:

* Gitt en strøm av tall fra 1-100, print alle tall > 50
* Gitt en strøm av tall fra 1-100, print alle tall < 50

## Oppgave 3 - Endringer i Collections og Optional (Java 9/10)

### a) 

* Lag en liste som inneholder duplikater på 'tradisjonell måte'
* Print ut settet, og forsøk å legge til et nytt element. 

### b) 

* Gitt en strøm av tall, opprett en immutable liste av tallene

### c)

* Lag en empty Optional
* Ta i bruk nytt api som kom med java 9, og print ut "Tom" når optional er tom, og "Ikke tom" når Optional har verdi. Endre optionalen til å ha en verdi, og verifiser at begge deler fungerer som for
* Ta i bruk ny metode som kom med java 10, for å kaste en feil når optional er tom
* Sammenlikn med Optional.get og Optional.orElseThrow((Supplier<? extends X> exceptionSupplier) 
og gjør deg noen tanker om lesbarhet
ventet. 


### e) 
```Java
var frukt = Arrays.asList("Eple", "Appelsin")
var unmodifiableFrukt = Collections.unmodifiableList(frukt);
frukt.set(0, "Banan");
```
Hva tror du unmodifieableFrukt.get0) gir her? 
Ta i bruk List.copyOf mot frukt, og observer 


## Oppgave 4 - Nye string-operasjoner - og endringer i Files (Java 11/12)
*  Ta i bruk nye apier som kom med Java 11 for å sjekke om tekstene under er blanke
```Java
var foersteTekst = "  ";
var andreTekst =  " Olabukse";
```
*  Print ut teksten under uten whitespace, og uten bruk av 3. part lib. Forsøk først med trim()
```Java
var s = "Unicode-tekst\u205F";
```

*  Gjør følgende om til en liste pr. linje tekst
```Java
var lines = "Hei Sopra Steria\n Håper alle har det fint på Apps Deep Dive!";
```
*  Gjør følgende om til en liste pr. linje tekst
```Java
var lines = "Hei Sopra Steria\n Håper alle har det fint på Apps Deep Dive!";
```

*  Konverter strengen under til HeiHeiHeiHeiHei
```Java
var tekst = "Hei";
```
* Skriv følgende til en fil, og les opp igjen fra filen som tekst
```Java
var lines = "Hei Sopra Steria\n Håper alle har det fint på Apps Deep Dive!";
```
* 
Transformer følgende streng til 'FOO BAR'
```Java
var tekst = "foo";
```

* Indenter teksten fra forrige oppgave med 4 whitespacer

## Oppgave 5 - Not predicate (Java 11)

Gitt 
```Java
var tekststream = List.of("Hei", "").stream()
```

Filtrer bort den tomme strengen vha not-predikat. 


