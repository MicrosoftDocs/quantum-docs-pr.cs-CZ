---
title: 'Diagnostika v knihovně Q # Standard'
description: 'Přečtěte si o diagnostických funkcích a operacích v knihovnách Q # Standard používaných k zachycení chyb nebo chyb v programech pro práci s poli.'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: ba2f248327bb3db4ee895f8e65ea31c17e42b5f4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906232"
---
# <a name="diagnostics"></a>Diagnostika #

Stejně jako u klasického vývoje je důležité, abyste mohli diagnostikovat chyby a chyby v programech za běhu.
Standardní knihovny Q # poskytují celou řadu různých způsobů, jak zajistit správnost programových chyb, jak je popsáno v <xref:microsoft.quantum.techniques.testing-and-debugging>.
Z velké části řečeno tato podpora přichází ve formě funkcí a operací, které buď instruují cílový počítač, aby poskytoval další diagnostické informace pro hostitelský program nebo vývojáře, nebo vynutil správnost podmínek a neutrálních vyjádření. voláním funkce nebo operace.

## <a name="machine-diagnostics"></a>Diagnostika počítače ##

Diagnostiku o klasických hodnotách se dá získat pomocí funkce <xref:microsoft.quantum.intrinsic.message> pro protokolování zprávy ve formě závislé na počítači.
Ve výchozím nastavení zapíše řetězec do konzoly.
Pomocí <xref:microsoft.quantum.intrinsic.message> společně s interpolované řetězcem usnadňuje sestavování diagnostických informací o klasických hodnotách:

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> `Message` má `(String -> Unit)`signatury, které reprezentují, že se ve Q # nedokáže vygenerovat zpráva protokolu ladění.

<xref:microsoft.quantum.diagnostics.dumpmachine> a <xref:microsoft.quantum.diagnostics.dumpregister> se dá dát cílovým počítačům pokyn, aby poskytovaly diagnostické informace o všech aktuálně přidělených qubits nebo o konkrétní registraci qubits v uvedeném pořadí.
Každý cílový počítač se liší v tom, jaké diagnostické informace jsou k dispozici v reakci na instrukci výpisu paměti.
Úplný cílový počítač [simulátoru stavu](xref:microsoft.quantum.machines.full-state-simulator) poskytuje hostitelský program s vektorem stavu, který interně používá k reprezentaci registru qubits.
Porovnáním je cílový počítač [simulátoru Toffoli](xref:microsoft.quantum.machines.toffoli-simulator) jediným klasickým bitem pro každou qubit.

 Další informace o výstupu `DumpMachine` [simulátoru úplného stavu](xref:microsoft.quantum.machines.full-state-simulator) najdete v části funkce výpisu paměti našeho [článku o testování a ladění](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions).


## <a name="facts-and-assertions"></a>Fakta a kontrolní výrazy ##

Jak je popsáno v tématu [testování a ladění](xref:microsoft.quantum.techniques.testing-and-debugging), funkce nebo operace s podpisem `Unit -> Unit` nebo `Unit => Unit`, v uvedeném pořadí, mohou být označeny jako *Test jednotky*.
Každý test jednotek se obvykle skládá z malého programu v řádu a jedné nebo více podmínek, které kontrolují správnost tohoto programu.
Tyto podmínky můžou být ve formě obou _skutečností_, které kontrolují hodnoty jejich vstupů nebo _kontrolních výrazů_, které kontrolují stavy jednoho nebo více qubits předaných jako vstup.

`EqualityFactI(1 + 1, 2, "1 + 1 != 2")` například představuje matematický fakt, který $1 + 1 = $2, zatímco `AssertQubit(One, qubit)` představuje podmínku, kterou měření `qubit` vrátí `One` s jistotou.
V bývalém případě můžeme ověřit správnost podmínky, pokud jsou k disqubity jenom jeho hodnoty, ale v druhém případě je potřeba, abyste zjistili něco o stavu, abyste mohli kontrolní výraz vyhodnotit.

Standardní knihovny Q # poskytují několik různých funkcí pro reprezentaci faktů, včetně:

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a>Testování stavů qubit ###

Kontrolní výrazy v praxi spoléhají na skutečnost, že klasické simulace [přívětach hodnot nevyžadují řízení bez klonování](https://arxiv.org/abs/quant-ph/9607018), takže můžeme při použití simulátoru pro náš cílový počítač udělat nefyzická měření a kontrolní výrazy.
Proto můžeme před nasazením na hardware otestovat jednotlivé operace na klasický simulátor.
V cílových počítačích, které neumožňují vyhodnocování kontrolních výrazů, volání <xref:microsoft.quantum.intrinsic.assert> lze bezpečně ignorovat.

Obecně platí, že <xref:microsoft.quantum.intrinsic.assert> operace vyhodnotí, že měření daného qubits v dané Pauli základu bude mít vždy daný výsledek.
Pokud se kontrolní výraz nezdařil, spuštění skončí voláním `fail` s danou zprávou.
Ve výchozím nastavení tato operace není implementována. simulátory, které ji mohou podporovat, by měly poskytnout implementaci, která provádí kontrolu za běhu.
`Assert` má `((Pauli[], Qubit[], Result, String) -> ())`signatury.
Vzhledem k tomu, že `Assert` je funkce s prázdnou řazenou kolekcí členů jako svůj výstupní typ, nebudou v programu Q # pozorovatelé žádné účinky volání `Assert`.

Funkce operace <xref:microsoft.quantum.intrinsic.assertprob> vyhodnotí, že měření daného qubits v daném Pauli základu bude mít daný výsledek s danou pravděpodobností v rámci určité tolerance.
Tolerance je aditivní (např. `abs(expected-actual) < tol`).
Pokud se kontrolní výraz nezdařil, spuštění skončí voláním `fail` s danou zprávou.
Ve výchozím nastavení tato operace není implementována. simulátory, které ji mohou podporovat, by měly poskytnout implementaci, která provádí kontrolu za běhu.
`AssertProb` má `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`signatury. První z parametrů `Double` dává požadovanou pravděpodobnost výsledku a druhá je tolerance.

Můžeme provést více než vyhodnotit jedno měření, a to pomocí klasických informací používaných simulátorem, které reprezentují vnitřní stav qubit, snadněji ke kopírování. to znamená, že pro otestování tohoto kontrolního výrazu není nutné skutečně provádět měření.
Konkrétně to nám umožní důvod na *nekompatibilní* měření, která by nebyla možná na skutečném hardwaru.

Předpokládejme, že `P : Qubit => Unit` je operace určená k přípravě stavu $ \ket{\psi} $, když je jeho vstup ve stavu $ \ket{0}$.
Pojďme $ \ket{\psi '} $ být skutečným stavem připraveným `P`.
Pak $ \ket{\psi} = \ket{\psi '} $ IF a pouze pokud se měří $ \ket{\psi '} $ na ose popsané v $ \ket{\psi} $ Always vrátí `Zero`.
To znamená, že \begin{align} \ket{\psi} = \ket{\psi '} \Text{if a pouze if} \braket{\psi | \psi '} = 1.
\end{align} pomocí primitivních operací, které jsou definovány v předehru, můžeme přímo provést měření, které vrátí `Zero`, pokud $ \ket{\psi} $ je eigenstate jedné z Pauli operátorů.


Operace <xref:microsoft.quantum.diagnostics.assertqubit> poskytuje obzvláště užitečnou zkrácený tvarování v případě, že chceme otestovat kontrolní výraz $ \ket{\psi} = \ket{0}$.
To je běžné, například když jsme nepočítali, aby vraceli ancilla qubits na $ \ket{0}$ před jejich uvolněním.
Vystavování proti $ \ket{0}$ je také užitečné, když chceme vyhodnotit, že se dvě přípravná Příprava stavu `P` a `Q` operace připravují stejný stav a když `Q` podporuje `Adjoint`.
Konkrétně

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

Obecně řečeno, ale nemůžeme mít přístup k kontrolním hodnotám, které se neshodují s eigenstates operátorů Pauli.
Například $ \ket{\psi} = (\ket{0} + e ^ {i \pi/8} \ket{1})/\sqrt{2}$ není eigenstate žádného operátoru Pauli, takže nemůžeme použít <xref:microsoft.quantum.intrinsic.assertprob> k jednoznačnému určení toho, že se stav $ \ket{\psi} $ rovná $ \ket{\psi} $.
Místo toho je nutné vyhodnotit kontrolní výraz $ \ket{\psi} = \ket{\psi} $ na předpoklady, které mohou být přímo testovány pomocí primitivních hodnot, které podporuje náš simulátor.
Provedete to tak, že použijete $ \ket{\psi} = \Alpha \ket{0} + \beta \ket{1}$ pro komplexní čísla $ \Alpha = a\_r + a\_i i $ a $ \beta $.
Všimněte si, že tento výraz vyžaduje čtyři reálné číslo $\{\_r,\_i, b\_r, b\_i\}$, aby bylo možné určit, že každé komplexní číslo může být vyjádřeno jako součet reálné a imaginární části.
V důsledku globální fáze ale můžeme zvolit $a\_i = $0, takže potřebujeme jenom tři reálné počty, abyste jednoznačně určili qubit stav.

Proto je potřeba zadat tři kontrolní výrazy, které jsou vzájemně nezávislé, aby bylo možné vyhodnotit stav, který očekáváme.
Provedeme to tak, že vyhledáme pravděpodobnost pozorování `Zero` pro každé měření Pauliy uvedené na hodnotu $ \Alpha $ a $ \beta $ a každý z nich se vyhodnotí jako nezávisle.
V uvedeném pořadí $x $, $y $ a $z $ budou `Result` hodnoty pro Pauli $X $, $Y $ a $Z $.
Pak použijte funkci pravděpodobnosti pro měření doby využívání hodnot \begin{align} \Pr (x = \texttt{Zero} | \Alpha, \beta) & = \frac12 +\_r b\_r + a\_i b\_i \\\Pr (y = \texttt{Zero} | \Alpha, \beta) & = \frac12 + a\_r b\_i-a\_i b\_r \\\\ \Pr (z = \texttt{Zero} | \Alpha, \beta) & = \frac12\left (1 +\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_i ^ 2 \right).\\
\end{align}

Operace <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> implementuje tyto kontrolní výrazy s ohledem na reprezentace $ \Alpha $ a $ \beta $ jako hodnoty typu <xref:microsoft.quantum.math.complex>.
To je užitečné, když se očekávaný stav dá vypočítat matematicky.

### <a name="asserting-equality-of-quantum-operations"></a>Vyhodnocení rovnosti operací s více podsebou ###

Zatím jsme se zavedli k testování operací, které jsou určené k přípravě konkrétních stavů.
Často se ale zajímá, jak operace funguje pro libovolné vstupy, a ne pro jeden pevný vstup.
Předpokládejme například, že jsme implementovali operaci `U : ((Double, Qubit[]) => () : Adjoint)` odpovídající rodině operátorů s velkými operátory $U (t) $ a zadali jste explicitní `adjoint` blok namísto použití `adjoint auto`.
Můžeme vás zajímat, že $U ^ \dagger (t) = U (-t) $, jak je očekáváno, pokud $t $ představuje čas vývoje.

Obecně řečeno, existují dvě různé strategie, které můžeme použít při provádění kontrolního výrazu, který dvě operace `U` a `V` působit stejným způsobem.
Nejprve můžeme ověřit, že `U(target); (Adjoint V)(target);` zachovává každý stav na daném základě.
Za druhé můžeme ověřit, že `U(target); (Adjoint V)(target);`, který působí na polovinu stavu entangled, zachová entanglement.
Tyto strategie jsou implementovány pomocí operací Canon <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> a <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>v uvedeném pořadí.

> [!NOTE]
> Odkazovaný kontrolní výraz uvedený výše funguje na základě [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), matematického rozhraní, které souvisí s operacemi $n $ qubits až entangled stavy na $2N $ qubits.
> Konkrétně operace identity na $n $ qubits představuje $n $ kopie stavu entangled $ \ket{\ beta_{00}} \mathrel{: =} (\ket{00} + \ket{11})/\sqrt{2}$.
> Operace <xref:microsoft.quantum.preparation.preparechoistate> implementuje tuto isomorphism a připraví stav, který představuje danou operaci.

Zhruba tyto strategie jsou odlišené o kompromisech podle času.
Iterace v každém vstupním stavu trvá delší dobu, zatímco použití entanglement jako odkazu vyžaduje uložení dalších qubits.
V případech, kdy operace implementuje vratné klasické operace, například zajímá Vás jenom o své chování při výpočetních intervalech, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> testuje rovnost v této omezené sadě vstupů.

> [!TIP]
> Iterace v rámci vstupních stavů je zpracována operacemi výčtu <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> a <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.
> Tyto operace jsou obecně užitečné pro použití operace u každého prvku kartézském produktu mezi dvěma nebo více sadami.

U těchto dvou přístupů se ale Nepostradatelně testují různé vlastnosti testovaných operací.
Vzhledem k tomu, že místní kontrolní výraz volá každou operaci několikrát, jednou pro každý vstupní stav, jakékoli náhodné volby a výsledky měření mohou být mezi jednotlivými voláními změněny.
Naproti tomu odkazovaný kontrolní výraz volá každou operaci přesně jednou, takže kontroluje, zda se operace rovnají *v jednom snímku*.
Oba tyto testy jsou užitečné v případě, že jsou zajištěny správné množství programů.


## <a name="further-reading"></a>Další čtení ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
