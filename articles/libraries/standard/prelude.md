---
title: 'Q # standardní knihovny – předehru | Microsoft Docs'
description: 'Q # standardní knihovny – předehru'
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: dddb3d4a5ebcdca16da41a5ae5520d98ea900a7f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/29/2019
ms.locfileid: "73183229"
---
# <a name="the-prelude"></a>Předehru #

Kompilátor Q # a cílové počítače, které jsou součástí vývojové sady pro plnění, poskytují sadu vnitřních funkcí a operací, které se dají použít při psaní programů v systému Q #.

## <a name="intrinsic-operations-and-functions"></a>Vnitřní operace a funkce ##

Vnitřní operace definované ve standardní knihovně zhruba spadají do jedné z několika kategorií:

- Základní klasické funkce shromážděné v oboru názvů <xref:microsoft.quantum.core>.
- Operace, které představují unitaries tvořené [Clifford a $T $ branami](xref:microsoft.quantum.concepts.qubit).
- Operace představující rotace různých operátorů.
- Operace implementující měření.

Vzhledem k tomu, že sada Clifford + $T $ je [univerzální](xref:microsoft.quantum.concepts.multiple-qubits) pro práci s výpočetním prostředím, tyto operace postačují k tomu, aby se v negligibly malé chybě vyimplementovala jakákoli algoritmus.
V případě, že zadáváte i rotace, Q # umožňuje programátorovi pracovat v rámci jedné qubit jednotkové a CNOTové knihovny brány. Tato knihovna je mnohem jednodušší, protože nepotřebuje programátora přímo vyjádřit Clifford $T + dekompozici $ a protože pro kompilaci jednoho qubit unitaries do Clifford a na $T $ Branch existují vysoce efektivní metody (viz [tady](xref:microsoft.quantum.more-information) pro další informace).

Pokud je to možné, operace definované v předehru, které fungují na qubits, umožňují použít `Controlled` variantu, takže cílový počítač provede příslušné rozklady.

Mnohé z funkcí a operací definovaných v této části předehru jsou v oboru názvů @"microsoft.quantum.intrinsic", takže většina zdrojových souborů Q # bude mít direktivu `open Microsoft.Quantum.Intrinsic;` hned po deklaraci počátečního oboru názvů.
Obor názvů <xref:microsoft.quantum.core> je automaticky otevřen, takže funkce jako <xref:microsoft.quantum.core.length> lze použít bez příkazu `open`.

### <a name="common-single-qubit-unitary-operations"></a>Běžné operace s jedním qubit jednotkou ###

Předehru také definuje mnoho běžných [qubit operací](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).
Všechny tyto operace umožňují `Controlled` i `Adjoint` funktory.

#### <a name="pauli-operators"></a>Pauli operátory ####

Operace <xref:microsoft.quantum.intrinsic.x> implementuje operátor Pauli $X $.
Tato situace se někdy označuje také jako brána `NOT`.
Má `(Qubit => Unit is Adj + Ctl)`podpisu.
Odpovídá qubit jednotkám:

\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: aktuálně používá napadení quadwhack.
1 & 0 \end{bmatrix} \end{Equation}

Operace <xref:microsoft.quantum.intrinsic.y> implementuje operátor Pauli $Y $.
Má `(Qubit => Unit is Adj + Ctl)`podpisu.
Odpovídá qubit jednotkám:

\begin{Equation} \begin{bmatrix} 0 &-i \\\\% FIXME: aktuálně používá napadení quadwhack.
i & 0 \end{bmatrix} \end{Equation}

Operace <xref:microsoft.quantum.intrinsic.z> implementuje operátor Pauli $Z $.
Má `(Qubit => Unit is Adj + Ctl)`podpisu.
Odpovídá qubit jednotkám:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: aktuálně používá napadení quadwhack.
0 &-1 \end{bmatrix} \end{Equation}

Níže vidíte, že tyto transformace jsou mapované na [Bloch koule](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (osa otočení v každém případě je zvýrazněna červeně):

![Pauli operace mapované na sféru Bloch](~/media/prelude_pauliBloch.png)

Je důležité si uvědomit, že použití stejné Pauliové brány dvakrát na stejný qubit zruší operaci (protože jste nyní provedli úplné otočení 2π (360 °) na povrchu Bloch koule, čímž se dorazí zpátky na výchozí bod). Tím se nám přineseme k následující identitě:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

To může být visualised v oblasti Bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Další Cliffords s jedním qubit ####

Operace <xref:microsoft.quantum.intrinsic.h> implementuje bránu Hadamard.
Tím se změní Pauli $X $ a $Z $ na osy cílového qubit, například $H \ket{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\sqrt{2}$ a $H \ket{+} = \ket{0}$.
Má signaturu `(Qubit => Unit is Adj + Ctl)`a odpovídá qubit jednotkám:

\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: aktuálně používá napadení quadwhack.
1 &-1 \end{bmatrix} \end{Equation}

Brána Hadamard je zvláště důležitá, protože se dá použít k vytvoření nadmnožiny{1}států $ \ket{0}$ a $ \ket. V Blochi sféry je nejjednodušší ho představit jako rotaci $ \ket{\psi} $ kolem osy x \pi $ radiánů ($ 180 ^ \circ $) následovanou otočením (po směru hodinových ručiček) kolem osy y podle $ \ pi/2 $ radiánů ($ 90 ^ \circ $):

![Hadamard operace mapovaná na sféru Bloch](~/media/prelude_hadamardBloch.png)

Operace <xref:microsoft.quantum.intrinsic.s> implementuje bránu fáze $S $.
Toto je maticová odmocnina operace Pauli $Z $.
To znamená, $S ^ 2 = Z $.
Má signaturu `(Qubit => Unit is Adj + Ctl)`a odpovídá qubit jednotkám:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: aktuálně používá napadení quadwhack.
0 & \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Rotace ####

Kromě výše uvedených Pauli a Clifford operací Q # předehru poskytuje celou řadu způsobů, jak vyjádřit rotace.
Jak je popsáno v [qubit operacích](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), možnost otáčení je zásadní pro algoritmy.

Začneme zpětným voláním, které umožňuje vyjádřit jakoukoli operaci s jedním qubit pomocí $H $ a $T $, kde $H $ je operace Hadamard a kde \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: aktuálně používá Quad back. napadení/Swagger/docs/v1.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} je to druhá odmocnina operace <xref:microsoft.quantum.intrinsic.s>, například $T ^ 2 = S $.
Brána $T $ je v rámci operace <xref:microsoft.quantum.intrinsic.t> implementovaná a má `(Qubit => Unit is Adj + Ctl)`signatury, což značí, že se jedná o jednotnou operaci na jednom qubit.

I když je to v zásadě dostačující pro popsání jakékoli libovolné operace s jedním qubit, mohou být v různých cílových počítačích efektivnější reprezentace o Pauli operátorech, takže předehru zahrnuje různé způsoby, jak convienently. Vyjádřete taková otočení.
Nejzákladnější z nich je operace <xref:microsoft.quantum.intrinsic.r>, která implementuje otočení kolem zadané osy Pauli, \begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} kde $ \sigma $ je Pauli operátor, $ \phi $ je úhel a kde $ \exp $ představuje exponenciální matrici.
Má `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`podpisů, kde první dvě části vstupu reprezentují klasické argumenty $ \sigma $ a $ \phi $, které jsou potřebné k určení jednotkového operátoru $R (\sigma, \phi) $.
Částečně se dá použít $ \sigma $ a $ \phi $, aby se získala operace, jejíž typ je jedna qubit jednotně.
Například `R(PauliZ, PI() / 4, _)` má typ `(Qubit => Unit is Adj + Ctl)`.

> [!NOTE]
> Operace <xref:microsoft.quantum.intrinsic.r> rozdělí vstupní úhel o 2 a násobí ho hodnotou-1.
> Pro $Z $ rotace to znamená, že $ \ket{0}$ eigenstate je otočeno pomocí $-\phi/$2 a $ \ket{1}$ eigenstate je otočeno $ \phi/$2, takže $ \ket{1}$ eigenstate je otočena $ \phi $ vzhledem k $ \ket{0}$ eigenstate.
>
> Konkrétně to znamená, že `T` a `R(PauliZ, PI() / 8, _)` se liší pouze nepodstatnými [globálními fázemi](xref:microsoft.quantum.glossary#global-phase).
> Z tohoto důvodu se $T $ někdy označuje jako brána $ \frac{\pi}{8}$-.
>
> Všimněte si také, že při otočení `PauliI` stačí použít globální fázi $ \phi/$2. I když tyto fáze nejsou důležité, jak je uvedeno v [koncepčních dokumentech](xref:microsoft.quantum.concepts.qubit), jsou relevantní pro kontrolované `PauliI` rotace.

V rámci algoritmů doby použitelnosti je často užitečné vyjádřit rotace jako dyadic zlomky, jako je $ \phi = \pi k/2 ^ n $ pro některá $k \in \mathbb{Z} $ a $n \in \mathbb{N} $.
Operace <xref:microsoft.quantum.intrinsic.rfrac> implementuje otočení kolem zadané osy Pauli pomocí této konvence.
Liší se od <xref:microsoft.quantum.intrinsic.r> v tom, že úhel otočení je zadán jako dva vstupy typu `Int`a interpretovány jako dyadic zlomek.
Proto `RFrac` má `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`signatury.
Implementuje jedinou qubit jednotk $ \exp (i \pi k \sigma/2 ^ n) $, kde $ \sigma $ je Pauli matice odpovídající prvnímu argumentu, $k $ je druhý argument a $n $ je třetí argument.
`RFrac(_,k,n,_)` je stejná jako `R(_,-πk/2^n,_)`; Všimněte si, že úhel je *záporný* pro zlomek.

Operace <xref:microsoft.quantum.intrinsic.rx> implementuje otočení kolem osy Pauli $X $.
Má `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.
`Rx(_, _)` je stejná jako `R(PauliX, _, _)`.

Operace <xref:microsoft.quantum.intrinsic.ry> implementuje otočení kolem osy Pauli $Y $.
Má `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.
`Ry(_, _)` je stejná jako `R(PauliY,_ , _)`.

Operace <xref:microsoft.quantum.intrinsic.rz> implementuje otočení kolem osy Pauli $Z $.
Má `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.
`Rz(_, _)` je stejná jako `R(PauliZ, _, _)`.

Operace <xref:microsoft.quantum.intrinsic.r1> implementuje rotaci o danou velikost kolem $ \ket{1}$, eigenstate $-$1 z $Z $.
Má `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.
`R1(phi,_)` je stejná jako `R(PauliZ,phi,_)` následovaná `R(PauliI,-phi,_)`.

Operace <xref:microsoft.quantum.intrinsic.r1frac> implementuje zlomkové otočení o zadanou hodnotu kolem hodnoty Z = 1 eigenstate.
Má `((Int,Int, Qubit) => Unit is Adj + Ctl)`podpisu.
`R1Frac(k,n,_)` je stejná jako `RFrac(PauliZ,-k.n+1,_)` následovaná `RFrac(PauliI,k,n+1,_)`.

Příklad operace otočení (kolem osy Pauli $Z $, v této instanci) mapované na Bloch koule, je uveden níže:

![Operace otočení mapovaná na sféru Bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operace s více qubit ####

Kromě qubit operací uvedených výše definuje předehru také několik operací s více qubit.

Nejprve operace <xref:microsoft.quantum.intrinsic.cnot> provádí standardní bránu řízenou`NOT`, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} má signatura `((Qubit, Qubit) => Unit is Adj + Ctl)`, která představuje, že $ \operatorname{CNOT} $ funguje unitarily na dvou individuálních qubits.
`CNOT(q1, q2)` je stejná jako `(Controlled X)([q1], q2)`.
Vzhledem k tomu, že `Controlled` funktor umožňuje řízení v registru, používáme `[q1]` literálu pole k označení toho, že chceme mít pouze jeden ovládací prvek.

Operace <xref:microsoft.quantum.intrinsic.ccnot> provádí nebránu se dvěma procesory, někdy také označované jako brána Toffoli.
Má `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`podpisu.
`CCNOT(q1, q2, q3)` je stejná jako `(Controlled X)([q1, q2], q3)`.

Operace <xref:microsoft.quantum.intrinsic.swap> proměňuje stavy se dvěma qubitsy.
To znamená, že implementuje jednotnou matrici \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} má podpis `((Qubit, Qubit) => Unit is Adj + Ctl)`.
`SWAP(q1,q2)` je ekvivalentní `CNOT(q1, q2)`, po kterém následuje `CNOT(q2, q1)` a potom `CNOT(q1, q2)`.

> [!NOTE]
> Brána *swap není stejná* jako změna uspořádání prvků proměnné s typem `Qubit[]`.
> Použití `SWAP(q1, q2)` způsobí změnu stavu qubits, na který odkazuje `q1` a `q2`, zatímco `let swappedRegister = [q2, q1];` má vliv na to, jak odkazujeme na tyto qubits.
> Kromě toho `(Controlled SWAP)([q0], (q1, q2))` umožňuje, aby bylo `SWAP` podmíněně ve stavu třetího qubit, který nemůžeme reprezentovat prvky.
> Brána kontrolovaného zahození, označovaná také jako brána Fredkin, je dostatečně výkonná pro zahrnutí všech klasických výpočtů.

Nakonec předehru poskytuje dvě operace pro reprezentaci exponenciálních hodnot operátorů Pauli s více qubit.
Operace <xref:microsoft.quantum.intrinsic.exp> provádí rotaci na základě tensor produktu Paulich matric, jak je znázorněno v qubit jednotkovém \begin{Equation} \operatorname{Exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \sigma_0 \otimes \sigma_1 \otimes \ cdots \otimes \sigma_n \right), \end{Equation} kde $ \vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n) $ je sekvence operátorů qubit s jedním Pauli a kde $ \phi $ je úhel.
`Exp` rotace představuje $ \vec{\sigma} $ jako pole `Pauli` prvků, takže má `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`signatury.

Operace <xref:microsoft.quantum.intrinsic.expfrac> provádí stejnou rotaci pomocí dyadic zlomkového zápisu popsaného výše.
Má `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`podpisu.

> [!WARNING]
> Exponenciální podíly tensor produktu operátorů Pauli nejsou stejné jako tensor produkty exponenciálních operátorů Pauli.
> To znamená, $e ^ {i (Z \otimes Z) \phi} \Ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Měření ###

Při měření `Zero` odpovídá eigenvalue a-1 eigenvalueému operátoru, který má výsledek `One`.

> [!NOTE]
> I když se tato konvence může zdát lichá, má dvě skvělé výhody.
> Nejprve se zobrazí výsledek $ \ket{0}$, který je reprezentován hodnotou `Result` `Zero`, zatímco sledování $ \ket{1}$ odpovídá `One`.
> Za druhé můžeme napsat, že eigenvalue $ \lambda $ odpovídající výsledku $r $ je $ \lambda = (-1) ^ r $.

Měření operací nepodporuje ani `Adjoint` ani `Controlled` funktor.

Operace <xref:microsoft.quantum.intrinsic.measure> provádí společné měření jednoho nebo více qubits v zadaném produktu Pauli Operators.
Pokud se pole Pauli a qubit liší od různých délek, operace se nezdařila.
`Measure` má `((Pauli[], Qubit[]) => Result)`signatury.

Počítejte s tím, že společná měření není shodná s měřením jednotlivých qubit jednotlivě.
Zvažte například stav $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.
Měření $Z _0 $ a $Z _1 každou jednotlivě získáme výsledky $r _0 = $1 a $r _1 = $1.
Měření $Z _0 Z_1 $ ale získáme jeden výsledek $r _ {\textrm{Joint}} = $0, což představuje, že dvojice $ \ket{11}$ je kladná.
Neumísťujte jinak $ (-1) ^ {r_0 + r_1} = (-1) ^ R_ {\textrm{Joint}}) $.
Vzhledem k tomu, že jsme se dozvěděli *jenom* o paritě z tohoto měření, jsou zachovány všechny informace o všech procesorech, které jsou reprezentované na pozici mezi 2 2 qubit stavy kladné parity, $ \ket{00}$ a $ \ket{11}$.
Tato vlastnost bude v podstatě pozdější, protože se zabývá opravami chyb.

Pro usnadnění práce předehru poskytuje také dvě další operace pro měření qubits.
Vzhledem k tomu, že provádění qubit měření je poměrně běžné, definuje předehru pro tento případ Zkrácený Zkrácený tvar.
Operace <xref:microsoft.quantum.intrinsic.m> měří operátor Pauli $Z $ v jednom qubit a má `(Qubit => Result)`podpisu.
`M(q)` je ekvivalentem `Measure([PauliZ], [q])`.

<xref:microsoft.quantum.measurement.multim> měří operátor Pauli $Z $ *samostatně* pro každé pole qubits a vrátí *pole* `Result` hodnot získaných pro každé qubit.
V některých případech je to možné optimalizovat. Má signaturu (`Qubit[] => Result[])`.
`MultiM(qs)` je ekvivalentní:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Funkce rozšíření a operace ##

Kromě toho předehru definuje bohatou sadu matematických a typových funkcí pro převod na úrovni .NET pro použití v kódu Q #.
Například obor názvů <xref:microsoft.quantum.extensions.math> definuje užitečné operace, jako jsou <xref:microsoft.quantum.extensions.math.sin> a <xref:microsoft.quantum.extensions.math.log>.
Implementace poskytovaná vývojovou sadou pro plnění z více systémů používá knihovnu klasických tříd .NET Base, a proto může zahrnovat další komunikaci s výměnou mezi programy a jejich klasickými ovladači.
I když to nepředstavuje problém pro místní simulátor, může to být problém s výkonem při použití vzdáleného simulátoru nebo skutečného hardwaru jako cílového počítače.
V takovém případě může jednotlivý cílový počítač zmírnit tento dopad na výkon tím, že tyto operace přepíše verze, které jsou pro konkrétní systém efektivnější.

### <a name="math"></a>Matematický ###

Obor názvů <xref:microsoft.quantum.extensions.math> poskytuje mnoho užitečných funkcí z [`System.Math` třídy](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)základní knihovny třídy .NET.
Tyto funkce lze použít stejným způsobem jako jakékoli jiné funkce Q #:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

V případě přetížení statické metody rozhraní .NET na základě typu argumentů je odpovídající funkce Q # opatřena příponou, která označuje typ jejího vstupu:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Bitové operace ###

Nakonec <xref:microsoft.quantum.extensions.bitwise> obor názvů poskytuje několik užitečných funkcí pro manipulaci s celými čísly prostřednictvím bitových operátorů.
Například <xref:microsoft.quantum.extensions.bitwise.parity> vrátí bitovou paritu celého čísla jako jiné celé číslo.
