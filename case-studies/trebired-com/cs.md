---
title: trebired.com, vlastní web organizace
lead: Web postavený z vlastních balíčků organizace, kde každé slovo i každá cena leží tam, kde si je čtenář může ověřit.
published: 2026-10-19
author: mirmachynka
client: Trebired
---

## Zadání

Organizace potřebovala web, který řekne, co je, co staví, co stavět odmítá a kolik si účtuje, a každé z těch tvrzení si musel umět ověřit i ten, kdo nám nevěří na slovo. Web je zároveň první práce, kterou klient uvidí, takže musel být postavený podle standardu, který organizace prodává, z jejích vlastních balíčků, a zveřejněný celý jako všechno ostatní.

## Text žije mimo web

Zásady, filozofie, standardy a příručka se píšou ve veřejném repozitáři <!--tbf:link https://github.com/Trebired/meta tab-->Trebired/meta<!--/tbf:link-->. Zápisy a případové studie, včetně této, se píšou v <!--tbf:link https://github.com/Trebired/publications tab-->Trebired/publications<!--/tbf:link-->. Web si oba načte při sestavení a když GitHub není dostupný, nechá si poslední kopii, kterou načetl, takže výpadek sítě žádnou stránku nevyprázdní.

Cena za to je záměrná. Změna zásad se na web dostane až při dalším sestavení a formát textu je malý: nadpisy, odstavce a odkazy. Cokoli, co konzument nevykreslí, by beze stopy zmizelo, a tak to formát rovnou odmítne.

## Cena je číslo

Každá cena je číslo v korunách, zapsané jednou. Web ji převede do měny jazyka, který se právě čte, podle denních referenčních kurzů Evropské centrální banky stažených při sestavení, a naformátuje ji tak, jak se v tom jazyce píšou peníze. Strop se zaokrouhluje dolů a spodní hranice nahoru, takže převedená cena nikdy netvrdí víc než původní.

## Obrázky, o které se nemusí nikdo starat

Ilustrace se kreslí v prohlížeči jako risografické tisky: samostatné vrstvy barvy, rastr a mírný posun soutisku, pomocí p5.riso. Tisk se nakreslí jednou a zůstane po celou návštěvu, a čtenáři, který si vyžádá omezený pohyb, se nic nehýbe.

Obálky zápisů a případových studií se generují z jejich vlastního textu při sestavení webu. Stejný text vždy dá stejný obrázek, takže zápis nepotřebuje k vydání žádný obrázek a jeho obálka se mění jen tehdy, když se mění jeho slova.

## Opraveno tam, kde byla chyba

Když běžný text vycházel menší, než stránky potřebovaly, velikost se ve webu nepřebíjela. Pocházela z konstanty ve frontendovém balíčku organizace, a tak balíček teď bere velikost odstavce ze své vlastní škály písma a web si jen vybere stupeň. Stejné pravidlo platilo po celou dobu: chyba, která patří balíčku, se opraví v balíčku a opravu dostane i každý další web, který na něm stojí.

## Co vyšlo a co se neměřilo

Web, jeho anglický a český text a každý dokument za ním jsou veřejné. Nemá žádné sledovací kódy a nespouští žádnou analytiku. Doby načítání ani velikost stránek se pro tuto studii neměřily, a tak o nich netvrdí nic.
