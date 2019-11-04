---
title: Úvod k technikům vývoje Microsoft Docs
description: Úvod k technikům vývoje
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 702d23293a1c340ddd3d7032d0e05294345469b2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442553"
---
# <a name="q-program-overview"></a>Přehled programu Q #

Q # je škálovatelný a víceúrovňový programovací jazyk specifický pro doménu pro náročné výpočty. Q # je programovací jazyk, ve kterém se dá použít k popisu způsobu, jakým se spouští instrukce na počítačích s více podsebou. Počítače, u kterých se může zaměřit rozsah z simulátorů na skutečný hardware na více než jednou. Q # je škálovatelný: dá se použít k psaní jednoduchých ukázkových programů, jako je teleport, které běží na několika qubits, ale podporuje také psaní velkých a propracovaných programů, jako jsou simulace složitých molekul, které budou vyžadovat velké počítače s miliony qubits. I když jsou velké fyzické počítače stále v budoucnosti, Q # umožňuje programátorům programovat komplexní algoritmy pro všechna období. Co je více, Q # podporuje různé úkoly, jako je ladění, profilace, odhad prostředků a určité simulace pro zvláštní účely, škálovatelný způsob. 

Z technického hlediska může být program pro práci s více částmi zobrazený jako konkrétní sada klasických funkcí, které při volání generují okruhy na sebe jako vedlejší účinky. Důležitým vlivem tohoto zobrazení je to, že program napsaný v Q # přímo nemodeluje qubits sám sebe, ale místo toho popisuje, jak počítač s klasickým ovládacím prvkem komunikuje s těmito qubits.
V rámci návrhu Q # proto nedefinuje stavy, které jsou na sobě nebo jiné vlastnosti, přímo, ale nepřímo prostřednictvím akce různých podprocesů definovaných v jazyce.
Například je třeba vzít v úvahu stav $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ popsaný v příručce k [koncepcím výpočetního](xref:microsoft.quantum.concepts.intro) stavu.
K přípravě tohoto stavu v Q # použijeme fakty, že se qubits inicializuje ve stavu $ \ket{0}$ a že $ \ket{+} = H\ket{0}$, kde $H $ je převod Hadamard:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # tranformations stavů

Při psaní výše uvedeného programu jsme v rámci tohoto programu explicitně neodkazovali na stav ve Q #, ale místo toho jsme popsali, jak byl stav *transformován* náš program.
Podobně podobný způsob, jakým program grafického shaderu shromažďuje popis transformací na každý vrchol, program v rámci Q # shromažďuje transformace na stavové stavy.
To nám umožní zcela nezávislá informace o tom, co *je* stav bez nároku na každém cílovém počítači, což může mít různé interpretace v závislosti na počítači. 

Z perspektivy programu Q # je qubit zcela neprůhledný odkaz na vnitřní strukturu cílového počítače.
Program Q # nemá žádnou schopnost introspect do stavu qubit, jeho reprezentace na cílovém počítači nebo i to, jestli se jedná o stejný qubit jako ostatní qubit k dispozici pro program.
Program může spíše volat operace, jako je například `Measure`, k získání informací z qubit a volání operací, jako je `X` a `H`, aby fungovaly ve stavu qubit.
Tyto operace nemají v rámci jazyka žádnou vnitřní definici a jsou provedeny pouze cílovým počítačem používaným ke spuštění konkrétního programu Q #.
Program Q # znovu sloučí tyto operace, jak jsou definovány cílovým počítačem, a vytvoří tak nové operace vyšší úrovně, které budou vyjadřovat výpočetní procesory.
V tomto případě Q # usnadňuje vyjádření logiky podkladových a hybridních životních procesorů, a to i obecně s ohledem na strukturu cílového počítače nebo simulátoru.

## <a name="q-operations-and-functions"></a>Operace a funkce Q #

V betonu je program Q # tvořen jednou nebo více *operacemi*, jednou nebo více *funkcemi*a uživatelem definovanými typy. Operace slouží k popisu transformací stavu počítačového provozu a jsou to nejzákladnější stavební blok programů Q #. Každá operace definovaná v rámci Q # může potom zavolat libovolný počet dalších operací, včetně integrovaných *vnitřních* operací implementovaných cílovým počítačem.
Při kompilaci je každá operace reprezentována jako typ třídy .NET, který lze poskytnout cílovým počítačům.

Na rozdíl od operací se funkce používají k popisu čistě klasického chování a nemají žádné vlivy na výpočetní výkonové hodnoty v klasickém prostředí. Q # je jazyk silného typu a je dodáván se sadou vestavěných primitivních typů, jakož i s podporou pro uživatelsky definované typy. 

V celé zbývající části tohoto průvodce se dozvíte, jak používat různé jazykové koncepty a konstrukce, které nám pomůžou definovat složité programy v jádře prostřednictvím základních stavebních bloků operací, funkcí a typů. 

## <a name="structure-of-q-source-files"></a>Struktura zdrojových souborů Q #

Minimálně zdrojový soubor Q # se skládá z *deklarace oboru názvů*, která určuje obor názvů .NET, který bude obsahovat definice ve zdrojovém souboru.
Definice z jiných zdrojových souborů Q # a knihoven lze zahrnout pomocí příkazu `open`.
Například většina operací definujících základní brány je definována v oboru názvů <xref:microsoft.quantum.intrinsic>.
Abychom to mohli zpřístupnit pro náš kód, jednoduše `open` tento obor názvů na začátku každého souboru:

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

V rámci oboru názvů každý zdrojový soubor Q # může definovat libovolnou kombinaci *operací*, *funkcí*a *uživatelsky definovaných typů*.
Ve zbytku této části popíšeme každou z nich a nabídnou si příklady, jak je možné využít v praxi k zajištění užitečných programů pro užívání.
