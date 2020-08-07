---
title: Diagnostika ve Q# standardních knihovnách
description: Přečtěte si o diagnostických funkcích a operacích v rámci Q# standardních knihoven používaných k zachycení chyb nebo chyb v programech pro práci s poli.
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a98795b2459adaa4e47c888751121fffdc70971
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868538"
---
# <a name="diagnostics"></a>Diagnostika #

Stejně jako u klasického vývoje je důležité, abyste mohli diagnostikovat chyby a chyby v programech za běhu.
Q#Standardní knihovny poskytují celou řadu různých způsobů, jak zajistit správnost programů v řadě, jak je popsáno v <xref:microsoft.quantum.guide.testingdebugging> .
Z velké části řečeno tato podpora přichází ve formě funkcí a operací, které buď instruují cílový počítač, aby poskytoval další diagnostické informace pro hostitelský program nebo vývojáře, nebo vynutil správnost podmínek a invariant vyjádřených voláním funkce nebo operace.

## <a name="machine-diagnostics"></a>Diagnostika počítače ##

Diagnostiku o klasických hodnotách se dá získat pomocí <xref:microsoft.quantum.intrinsic.message> funkce pro protokolování zprávy ve formě závislé na počítači.
Ve výchozím nastavení zapíše řetězec do konzoly.
Používá se společně s interpolované řetězce a usnadňuje <xref:microsoft.quantum.intrinsic.message> tak sestavy diagnostických informací o klasických hodnotách:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message`má signaturu `(String -> Unit)` , která reprezentuje, že generování zprávy protokolu ladění není možné pozorovat v rámci Q# .

<xref:microsoft.quantum.diagnostics.dumpmachine>A <xref:microsoft.quantum.diagnostics.dumpregister> volat cílové počítače instruují, aby poskytovaly diagnostické informace o všech aktuálně přidělených qubits nebo o konkrétním registru qubits, v uvedeném pořadí.
Každý cílový počítač se liší v tom, jaké diagnostické informace jsou k dispozici v reakci na instrukci výpisu paměti.
Úplný cílový počítač [simulátoru stavu](xref:microsoft.quantum.machines.full-state-simulator) poskytuje hostitelský program s vektorem stavu, který interně používá k reprezentaci registru qubits.
Porovnáním je cílový počítač [simulátoru Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) jediným klasickým bitem pro každou qubit.

 Další informace o výstupu [simulátoru úplného stavu](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` najdete v části funkce výpisu paměti v našem [článku o testování a ladění](xref:microsoft.quantum.guide.testingdebugging#dump-functions).


## <a name="facts-and-assertions"></a>Fakta a kontrolní výrazy ##

Jak je popsáno v tématu [testování a ladění](xref:microsoft.quantum.guide.testingdebugging), funkce nebo operace s podpisem `Unit -> Unit` nebo v `Unit => Unit` uvedeném pořadí může být označena jako *Test jednotky*.
Každý test jednotek se obvykle skládá z malého programu v řádu a jedné nebo více podmínek, které kontrolují správnost tohoto programu.
Tyto podmínky můžou být ve formě obou _skutečností_, které kontrolují hodnoty jejich vstupů nebo _kontrolních výrazů_, které kontrolují stavy jednoho nebo více qubits předaných jako vstup.

Například `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` představuje matematický fakt, který $1 + 1 = $2, zatímco `AssertQubit(One, qubit)` představuje podmínku, kterou měření `qubit` vrátí `One` s jistotou.
V bývalém případě můžeme ověřit správnost podmínky, pokud jsou k disqubity jenom jeho hodnoty, ale v druhém případě je potřeba, abyste zjistili něco o stavu, abyste mohli kontrolní výraz vyhodnotit.

Q#Standardní knihovny poskytují několik různých funkcí pro reprezentaci faktů, včetně:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Testování stavů qubit ###

Kontrolní výrazy v praxi spoléhají na skutečnost, že klasické simulace [přívětach hodnot nevyžadují řízení bez klonování](https://arxiv.org/abs/quant-ph/9607018), takže můžeme při použití simulátoru pro náš cílový počítač udělat nefyzická měření a kontrolní výrazy.
Proto můžeme před nasazením na hardware otestovat jednotlivé operace na klasický simulátor.
V cílových počítačích, které neumožňují vyhodnocování kontrolních výrazů, volání <xref:microsoft.quantum.diagnostics.assertmeasurement> lze bezpečně ignorovat.

Obecně platí, že operace vyhodnotí <xref:microsoft.quantum.diagnostics.assertmeasurement> , že měření daného qubits v dané Pauli základu bude mít vždy daný výsledek.
Pokud se kontrolní výraz nezdařil, spuštění skončí voláním `fail` dané zprávy.
Ve výchozím nastavení tato operace není implementována. simulátory, které ji mohou podporovat, by měly poskytnout implementaci, která provádí kontrolu za běhu.
`AssertMeasurement`má signaturu `((Pauli[], Qubit[], Result, String) -> ())` .
Vzhledem k tomu `AssertMeasurement` , že se jedná o funkci s prázdnou řazenou kolekcí členů jako svůj výstupní typ, `AssertMeasurement` nejsou v rámci programu pozorovatelé žádné účinky volání Q# .

<xref:microsoft.quantum.diagnostics.assertmeasurementprobability>Funkce Operation vyhodnotí, že měření daného qubits v daném Pauli základu bude mít daný výsledek s danou pravděpodobností v rámci určité tolerance.
Tolerance je aditivní (např. `abs(expected-actual) < tol` ).
Pokud se kontrolní výraz nezdařil, spuštění skončí voláním `fail` dané zprávy.
Ve výchozím nastavení tato operace není implementována. simulátory, které ji mohou podporovat, by měly poskytnout implementaci, která provádí kontrolu za běhu.
`AssertMeasurementProbability`má signaturu `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` . První z `Double` parametrů poskytuje požadovanou pravděpodobnost výsledku a druhou pro toleranci.

Můžeme provést více než vyhodnotit jedno měření, a to pomocí klasických informací používaných simulátorem, které reprezentují vnitřní stav qubit, snadněji ke kopírování. to znamená, že pro otestování tohoto kontrolního výrazu není nutné skutečně provádět měření.
Konkrétně to nám umožní důvod na *nekompatibilní* měření, která by nebyla možná na skutečném hardwaru.

Předpokládejme, že `P : Qubit => Unit` se jedná o operaci, která má za cíl připravit stav $ \ket{\psi} $, pokud je jeho vstup ve stavu $ \ket {0} $.
Pojďme $ \ket{\psi} $ být skutečným stavem, který připravil `P` .
Pak $ \ket{\psi} = \ket{\psi '} $ IF a pouze pokud se měří $ \ket{\psi '} $ na ose popsané v $ \ket{\psi} $ Always vrátí `Zero` .
To znamená, že \begin{align} \ket{\psi} = \ket{\psi '} \Text{if a pouze if} \braket{\psi | \psi '} = 1.
\end{align} pomocí primitivních operací, které jsou definovány v předehru, můžeme přímo provést měření, které vrátí, `Zero` Pokud je $ \ket{\psi} $ eigenstate jedné z operátorů Pauli.


Tato operace <xref:microsoft.quantum.diagnostics.assertqubit> poskytuje obzvláště užitečnou zkrácený zkrácený postup v případě, že chceme otestovat kontrolní výraz $ \ket{\psi} = \ket {0} $.
To je běžné, například když jsme nepočítali, aby vraceli ancilla qubits na $ \ket {0} $ před jejich uvolněním.
Vystavování proti $ \ket {0} $ je také užitečné, když chceme uplatnit, že se dopravují dvě stavová Příprava `P` a `Q` operace připravují stejný stav a když `Q` podporuje `Adjoint` .
Konkrétně

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

Obecně řečeno, ale nemůžeme mít přístup k kontrolním hodnotám, které se neshodují s eigenstates operátorů Pauli.
Například $ \ket{\psi} = (\ket {0} + e ^ {i \pi/8} \ket {1} )/\sqrt {2} $ není eigenstate žádného operátoru Pauli, takže nemůžeme použít <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> k jednoznačnému určení toho, že se stav $ \ket{\psi} $ rovná $ \ket{\psi} $.
Místo toho je nutné vyhodnotit kontrolní výraz $ \ket{\psi} = \ket{\psi} $ na předpoklady, které mohou být přímo testovány pomocí primitivních hodnot, které podporuje náš simulátor.
Provedete to tak, že $ \ket{\psi} = \Alpha \ket {0} + \beta \ket {1} $ for Complex Numbers $ \Alpha = a \_ r + a \_ i $ a $ \beta $.
Všimněte si, že tento výraz vyžaduje čtyři reálné hodnoty $ \{ a \_ r, a \_ i, b \_ r, b \_ i \} $, aby bylo možné určit, že každé komplexní číslo může být vyjádřeno jako součet reálné a imaginární části.
Z důvodu globální fáze si ale můžeme vybrat $a \_ i = $0, takže potřebujeme jenom tři reálné počty, abyste jednoznačně určili qubit stav.

Proto je potřeba zadat tři kontrolní výrazy, které jsou vzájemně nezávislé, aby bylo možné vyhodnotit stav, který očekáváme.
Provedeme to tak, že `Zero` vyhledáme pravděpodobnost pozorování pro každé měření Pauliy uvedené na hodnotu $ \Alpha $ a $ \beta $ a každý nezávisle se vyhodnotí.
`Result`Hodnoty pro Pauli $X $, $Y $ a $Z $ nechte $x $, $y $ a $z $.
Pak použijte funkci pravděpodobnosti pro měření doby využívání hodnoty \begin{align} \Pr (x = \texttt{Zero} | \Alpha, \beta) & = \frac12 + a \_ r b \_ r + a \_ i b \_ i \\ \\ \Pr (y = \texttt{Zero} | \Alpha, \beta) & = \frac12 + a \_ r b \_ i-a \_ i b \_ r \\ \\ \Pr (z = \texttt{Zero} | \Alpha, \beta) & = \frac12\left (1 + a \_ r ^ 2 + a \_ i ^ 2 + b \_ r ^ 2 + b \_ i ^ 2 \right).
\end{align}

Tato <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> operace implementuje tyto kontrolní výrazy s ohledem na reprezentace $ \Alpha $ a $ \beta $ jako hodnoty typu <xref:microsoft.quantum.math.complex> .
To je užitečné, když se očekávaný stav dá vypočítat matematicky.

### <a name="asserting-equality-of-quantum-operations"></a>Vyhodnocení rovnosti operací s více podsebou ###

Zatím jsme se zavedli k testování operací, které jsou určené k přípravě konkrétních stavů.
Často se ale zajímá, jak operace funguje pro libovolné vstupy, a ne pro jeden pevný vstup.
Předpokládejme například, že jsme implementovali operaci `U : ((Double, Qubit[]) => () : Adjoint)` odpovídající rodině operátorů s jednou $U (t) $ a místo použití byla poskytnuta explicitní `adjoint` blok `adjoint auto` .
Můžeme vás zajímat, že $U ^ \dagger (t) = U (-t) $, jak je očekáváno, pokud $t $ představuje čas vývoje.

Obecně řečeno, existují dvě různé strategie, které můžeme použít při provádění kontrolního výrazu, který se shoduje se dvěma operacemi `U` a `V` jednají stejným způsobem.
Nejprve můžeme kontrolovat, zda `U(target); (Adjoint V)(target);` zachovává každý stav na daném základě.
Za druhé můžeme ověřit, že `U(target); (Adjoint V)(target);` jednání na polovinu entangled stavu zachovává entanglement.
Tyto strategie jsou implementované operacemi Canon <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> a v <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced> uvedeném pořadí.

> [!NOTE]
> Odkazovaný kontrolní výraz uvedený výše funguje na základě [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), matematického rozhraní, které souvisí s operacemi $n $ qubits až entangled stavy na $2N $ qubits.
> Konkrétně operace identity na $n $ qubits je představována $n $ kopie stavu entangled $ \ket{\ beta_ {00} } \mathrel{: =} (\ket {00} + \ket {11} )/\sqrt {2} $.
> Tato operace <xref:microsoft.quantum.preparation.preparechoistate> implementuje tuto isomorphism a připraví stav, který představuje danou operaci.

Zhruba tyto strategie jsou odlišené o kompromisech podle času.
Iterace v každém vstupním stavu trvá delší dobu, zatímco použití entanglement jako odkazu vyžaduje uložení dalších qubits.
V případech, kdy operace implementuje vratné klasické operace, například zajímá Vás jenom o své chování při výpočetních intervalech, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> testuje rovnost v této omezené sadě vstupů.

> [!TIP]
> Iterace v rámci vstupních stavů je zpracována operacemi výčtu <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> a <xref:microsoft.quantum.canon.iteratethroughcartesianpower> .
> Tyto operace jsou obecně užitečné pro použití operace u každého prvku kartézském produktu mezi dvěma nebo více sadami.

U těchto dvou přístupů se ale Nepostradatelně testují různé vlastnosti testovaných operací.
Vzhledem k tomu, že místní kontrolní výraz volá každou operaci několikrát, jednou pro každý vstupní stav, jakékoli náhodné volby a výsledky měření mohou být mezi jednotlivými voláními změněny.
Naproti tomu odkazovaný kontrolní výraz volá každou operaci přesně jednou, takže kontroluje, zda se operace rovnají *v jednom snímku*.
Oba tyto testy jsou užitečné v případě, že jsou zajištěny správné množství programů.


## <a name="further-reading"></a>Další čtení ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:microsoft.quantum.diagnostics>
