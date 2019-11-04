---
title: Softwarový zásobník | Microsoft Docs
description: Softwarový zásobník
author: QuantumWriter
uid: microsoft.quantum.concepts.software-stack
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f97dfacf6cde5fa92e1f368efaae36554a5c944d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184725"
---
# <a name="software-stack-for-quantum-computing"></a>Softwarový zásobník pro výpočetní výkon
Když si myslíme, že se jedná o počítač, který je v jednom zařízení, na kterém je spuštěná aplikace, ale moderní výpočetní prostředí jsou mnohem složitější a pokročilé. Aplikace, která se obvykle používá, se obvykle nachází na více vrstvách softwaru, které poskytují provádění aplikace na úrovni hardwaru. Tyto softwarové vrstvy jsou nezbytné k abstrakci vývoje řešení aplikace z základní složitosti kompletního výpočetního systému. Pokud se vývojář musel představit o sběrnici, architekturách mezipaměti, komunikačních protokolech a dalších při psaní jednoduché aplikace smartphone, úloha by se stala mnohem složitější.  Koncept *softwarového zásobníku* byl vyvinutý v klasickém výpočetním prostředí, aby bylo možné tyto problémy vyřešit.  Z hlediska klasického konceptu je softwarový zásobník také klíčovou součástí výhledu za sebou – výpočetní výkon s Q #.

## <a name="conventional-stack"></a>Konvenční zásobník
Klíčový nápad za softwarový zásobník je rekurze.  Skládá se z několika vnořených vrstev rozhraní, které z vývojářů zahodily podrobnosti o nižších úrovních zařízení.  Často používaný softwarový zásobník například zahrnuje spuštění ASP.NET (programovací jazyk), nad SQL serverem (systém pro správu relačních databází), který běží na Internetová informační služba (webový server), který běží na Windows serveru ( operační systém), který řídí hardware počítače.  Když si vyhledáte software jako hierarchii, může jeden psát software v ASP.NET, aniž by bylo nutné porozumět podrobnostem o nízké úrovni veškerého softwaru pod ním.

## <a name="quantum-stack"></a>Zásobník pro všechna množství

Softwarový zásobník v množstvích výpočetních prostředí není v zásadě odlišný a v praxi se chová na nižší úrovni než tradiční zásobníky.  Jak vypadá zásobník pro nečinnosti?  Počítač s více než jednou z nich není náhradou za tradiční (často označované jako klasické) počítače.  Ve skutečnosti budou počítače se systémem téměř určitě spolupracovat s klasickými počítači a řešit tak výpočetní problémy.  V některých případech to vznikne z důvodu nekřehkosti dat.  Data o době nezáleží na tom, že pokud si to ještě nejste poznamenali, je to u nich skoro jistě poškození informací.  Počítače s příznačnými údaji budou muset být navržené tak, aby se opravily chyby. to znamená, že osamocené interakce z jejího fyzického prostředí neúmyslně poškozují informace a výpočty. Z tohoto důvodu je přirozený cíl pro Q # chybně opravený počítač (často označovaný jako počítač se *selháním, který je odolný vůči chybám* ), který přijímá seznam instrukcí na základě počtu procesorů (nazývaných brány nebo operace s bránou) a tyto pokyny aplikuje na stav. data, která jsou v něm uložená.  Počítejte s tím, že pokud je počet operací qubits a hradlo v algoritmu nebo programu dostatečně malý, oprava chyb nemusí být nezbytně nutná.  Jelikož se ale zvýší počet qubits a provozních operací, bude se vám tento požadavek lišit, takže jsme si náš softwarový zásobník a Q # napravili na aptly a efektivně zavedli opravy chyb a umožnili škálovatelnou výpočetní výkon, který je odolný proti chybám.

### <a name="error-correction"></a>Oprava chyb
Korekce chyb vyžaduje rychlý a spolehlivý klasický počítač, který je možné spustit v součinnosti s počítačem s více operačními systémy, aby opravil chyby, jak se objevují při výpočtu.  V praxi může být potřeba, aby komponenty, jako jsou pole programovatelné brány (FPGA) nebo procesory Fast Cryogenic, mohly identifikovat a opravit chyby rychleji než přirozeně nahromadění v počítači s procesorem.  V důsledku toho je počítač s velkým množstvím hybridním počítačem, který se skládá z několika různých výpočetních zařízení, která fungují v rámci široké škály teplot.  Z tohoto důvodu je mnohem užitečnější, abyste si myslíte o programování počítače s velkým množstvím pomocí objektivu softwarového zásobníku, protože je potřeba mít k dispozici spoustu hardwarových a softwarových (klasických) a softwaru, který je nezbytný k tomu, aby se zajistila implementace. algoritmus v počítači se systémem na více počítačů.

### <a name="quantum-conceptual-stack"></a>Koncepční zásobník
Koncepční zásobník, který ilustruje funkční tok faktoringu 8704143553785700723 v výpočetních prostředích, je uvedený níže:

![Softwarový zásobník](~/media/concepts_stack.png)

### <a name="specification-and-algorithm"></a>Specifikace a algoritmus
Existuje několik hlavních fází programování, jako je výpočet.  První a pravděpodobně nejnáročnější fáze určuje problém, který si přejeme vyřešit.  V takovém případě se jedná o problém s číslem 8704143553785700723 na součin dvou apostrofových čísel.  Další krok zahrnuje návrh algoritmu pro řešení tohoto výpočetního problému.  V takovém případě je možné pomocí algoritmu Shor slavných pro hledání faktorů použít algoritmus pro vynásobení.  Tento algoritmus je vyjádřený v Q # a pak sekvence operací s více procesory je výstupem, který se dá spustit na ideálním počítači s bezplatnými chybami.  

### <a name="physical-gates"></a>Fyzické brány
V tomto příkladu se předpokládá, že povaha není tak, aby poskytovala chybový počítač bez chyb, takže následný krok provede operace vygenerované v Q # a překládá je pomocí šablon určených metodou opravy chyb pro incidenty zvolené na fyzické brány, které základní hardware může být spuštěn.  Tento proces zahrnuje nahrazení všech logických qubit popsaných v předchozím modelu s hostitelem fyzických qubits, které se používají k ukládání a ochraně informací v jednom qubit redundantním způsobem, který může odolat místním chybám u fyzického prvku. qubits dostatečně dlouho, aby se tyto chyby zjistily a opravily.  Stejně jako logické qubits popsané v kódu Q # musí být nahrazeno velkým počtem fyzických qubits, podobně každou bránu pro práci s poli, která je popsána ve výstupu, se musí přeložit do sekvence fyzických bran, které fungují na fyzickém qubits.  Z tohoto důvodu je výstup Q # jenom v konečném cíli pro výpočetní výkon a další úrovně abstrakce je potřeba ke spuštění kódu na hardwaru oblivious způsobem.

### <a name="control-computer"></a>Řídicí počítač
Fyzická sekvence brány se pak načte do obyčejného počítače, který tyto pokyny pošle do řídicího počítače, který rozhraní přímo s počítačem s taktem.  Tato vrstva v softwarovém zásobníku se často zpracovává pomocí experimentálního řídicího softwaru, jako je [QCoDeS](http://qcodes.github.io/Qcodes/).

### <a name="interface-computer"></a>Počítač rozhraní
Poslední krok tohoto procesu zahrnuje počítač rozhraní, který je nejdřív vysílaný jako potřebný pro počítač s rychlým ovládáním. Pak počítač s rychlým ovládáním aplikuje potřebné napětí (obvykle nazývané Pulse) k implementaci požadovaných bran na qubits. To je potřeba udělat při opravě chyb, které jsou pozorovány prostřednictvím opravy chyb.  Cryogenic FPGA nebo jiný exotický hardware může být potřeba k provedení těchto kroků v rámci přísných časových požadavků stanovených rychlostí, při které se zobrazí chyby v počítači s nárokem na tento počítač.  Cílový jazyk na této úrovni je často [VHDL](https://en.wikipedia.org/wiki/VHDL), což vyžaduje odlišný způsob, který je třeba uvažovat od toho, který se používá v horním konci zásobníku k analýze popisu pro tento algoritmus.

### <a name="the-q-quantum-programming-language"></a>Jazyk programovacího jazyka Q #
Cílem Q # je poskytnout jednoduchý jazyk, který vývojářům umožňuje psát kód, který se zaměřuje na širokou spoustu výpočetních platforem a rozhraní, s využitím vrstev softwaru, který stojí mezi uživatelem a zařízením.  Tento jazyk to usnadňuje tím, že přechodu pojem softwarový zásobník a abstrakce spousty podrobností o podkladovém počítači s velkým stavem a zároveň umožňuje další úrovně zásobníku zveřejněné prostřednictvím jazyka C#, jako je, k provedení potřebného překlady z kódu Q # k základním operacím.  To umožňuje vývojářům soustředit se na to, co je nejlepší: návrh algoritmů a řešení problémů.
