---
title: Co dokážou kvantové počítače?
description: Přečtěte si o dopadu kvantových výpočtů od nových kvantových algoritmů až po algoritmy inspirované kvantovým přístupem a spouštěné na klasických počítačích.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: 9d8ba90a504f298f9465ebf564c43625a4d43168
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529952"
---
# <a name="what-can-a-quantum-computer-do"></a>Co dokáže kvantový počítač?

Co můžeme dělat s kvantovým počítačem, ale ne s klasickým?

V případě některých z nejobtížnějších světových problémů, kdy by nalezení řešení trvalo současným počítačům miliardy let, by kvantový počítač mohl řešení najít za několik dnů, hodin nebo dokonce minut.

Kvantové výpočty umožní výzkumníkům vyvíjet nové katalyzátory a materiály, vylepšovat léky, zrychlovat pokrok v oblasti umělé inteligence a odpovídat na základní otázky týkající se původu vesmíru.

## <a name="quantum-simulation"></a>Kvantová simulace

Používání kvantových programů k modelování vlastních kvantových systémů poskytuje rozsáhlé možnosti v rozvíjení náhledů, které vedou k inovacím v mnoha odvětvích. Fotosyntéza, supravodiče a složité molekuly jsou příklady kvantových systémů, které lze simulovat s použitím kvantových programů.

Simulace mikroskopických systémů, které se chovají v souladu s kvantovou mechanikou, jsou výpočetně náročné. Je nutné brát v úvahu všechny možné stavy, které můžou být v superpozici. Počet stavů exponenciálně roste s velikostí systému. V kvantovém počítači není třeba modelovat všechny stavy systému. Místo toho vložíme kvantový stav systému, který chceme simulovat v qubitech počítače, a spustíme simulaci se specifickou sadou kvantových hradel. Jinými slovy, k simulaci kvantového systému použijeme kvantový počítač.

Chemické molekuly jsou kvantové systémy, a proto je možné analyzovat je tímto způsobem. Jednou z takových specifických chemických látek je enzym _nitrogenáza_, který by mohl mít potenciál snižovat spotřebu energie a emise skleníkových plynů u stávajících hnojiv, pokud bychom jeho vlastnostem lépe porozuměli.

## <a name="cryptography"></a>Kryptografie

Pravděpodobně nejpopulárnější aplikace kvantových výpočtů je v kryptografii, kde Petr Shor v roce 1994 ukázal, že škálovatelný kvantový počítač může prolomit všechny široce používané šifrovací techniky.  Klasická kryptografie spoléhá na úpornost operací s velkými čísly, jako je například faktorizace velkých čísel na dvě prvočísla.

S použitím kvantových výpočtů jsou tyto operace teoreticky proveditelné (pomocí Shorova algoritmu). Ačkoli implementace tohoto algoritmu není při současném rozsahu kvantového hardwaru fyzicky možná, byla impulzem k vývoji algoritmů odolných vůči kvantovému přístupu a zajišťujících zabezpečení dat v budoucnu. Patří mezi ně nové kvantové algoritmy pro šifrování a distribuci šifrovacích klíčů.

My tady v Microsoftu máme špičkový tým postkvantové kryptografie a zabezpečení, který vyvíjí algoritmy odolné i proti kvantovým výpočtům.

## <a name="optimization"></a>Optimalizace

Optimalizace je úloha, kdy se provádí ve vysoce rozměrném prostoru velké hledání řešení, které minimalizuje danou nákladovou funkci.   V kvantovém počítači můžeme zrychlit algoritmy optimalizace a umožnit hledání řešení, která by jinak nebyla možná. Aplikace se uplatní v mnoha oborech, v přepravě a logistice, zdravotní péči, diagnostice nebo materiálových vědách. Může to výrazně ovlivnit, jak můžou být tyto obory efektivnější.

Optimalizace s využitím kvantových výpočtů nám umožňuje inovovat v oblasti přepravy a logistiky způsobem, který není u dnešních klasických systémů možný.

Optimalizace dopravních toků může snížit zácpy.  Kromě plánování trasy jde o přiřazování stojánek letadlům, doručování balíčků, plánování úloh a další. Zásadní objevy v oblasti materiálové vědy můžou vést k novým formám energie, bateriím s větší kapacitou nebo lehčím a pevnějším materiálům.

## <a name="machine-learning"></a>Strojové učení

Velký počet numerických výpočtů na klasických výpočetních prostředcích sestává hlavně z řešení soustav lineárních rovnic, zejména v oblasti strojového učení, kde většinu výpočetních nákladů tvoří výpočet rozsáhlých inverzních matric.

Naštěstí však existuje kvantový algoritmus, který nám umožňuje najít přibližné řešení soustavy exponenciálně rychleji než klasický počítač. Tento algoritmus otvírá cestu ke značnému zrychlení u všech problémů, které vyžadují řešení soustav lineárních rovnic.

Řešení problémů v těchto oblastech pomůžou řešit energetické krize, klimatické změny, nedostatek potravin a přesnou lékařskou diagnostiku.

## <a name="quantum-inspired-computing"></a>Výpočty inspirované kvantovým přístupem

Algoritmy inspirované kvantovým přístupem jsou implementované v klasickém softwaru, využívají však kvantové principy, aby se zvýšila rychlost a přesnost.

Algoritmy inspirované kvantovým přístupem se aplikují v lékařském výzkumu, například pro zvyšování přesnosti skenů magnetické rezonance (MRI). Výpočty inspirované kvantovým přístupem se používají k optimalizaci konfigurace zařízení MRI pro identifikaci konkrétních onemocnění.

## <a name="next-steps"></a>Další kroky

* [Proč se učit provádět kvantové výpočty?](xref:microsoft.quantum.overview.why)
* [Začínáme se sadou Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
