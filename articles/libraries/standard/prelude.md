---
title: Vnitřní operace a funkce v QDK
description: Seznamte se s vnitřními operacemi a funkcemi v QDK, včetně klasických funkcí a operací s jednotkou, rotací a měřením.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 19674620475e68b41c855023807a5fd1f7945ec9
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327675"
---
# <a name="the-prelude"></a>Předehru #

Kompilátor Q # a cílové počítače, které jsou součástí vývojové sady pro plnění, poskytují sadu vnitřních funkcí a operací, které se dají použít při psaní programů v systému Q #.

## <a name="intrinsic-operations-and-functions"></a>Vnitřní operace a funkce ##

Vnitřní operace definované ve standardní knihovně zhruba spadají do jedné z několika kategorií:

- Základní klasické funkce shromážděné v <xref:microsoft.quantum.core> oboru názvů.
- Operace, které představují unitaries tvořené [Clifford a $T $ branami](xref:microsoft.quantum.concepts.qubit).
- Operace představující rotace různých operátorů.
- Operace implementující měření.

Vzhledem k tomu, že sada Clifford + $T $ je [univerzální](xref:microsoft.quantum.concepts.multiple-qubits) pro práci s výpočetním prostředím, tyto operace postačují k tomu, aby se v negligibly malé chybě vyimplementovala jakákoli algoritmus.
V případě, že zadáváte i rotace, Q # umožňuje programátorovi pracovat v rámci jedné qubit jednotkové a CNOTové knihovny brány. Tato knihovna je mnohem jednodušší, protože nepotřebuje programátora přímo vyjádřit $T Clifford a dekompozici $, protože pro kompilaci jednoduchých qubit unitaries do Clifford a $T $ Branch existují vysoce efektivní metody (Další informace najdete [tady](xref:microsoft.quantum.more-information) ).

Pokud je to možné, operace definované v předehru, které fungují na qubits, umožňují použití `Controlled` varianty, takže cílový počítač provede příslušné rozklady.

Mnohé z funkcí a operací, které jsou definovány v této části předehru, jsou v @"microsoft.quantum.intrinsic" oboru názvů, takže většina zdrojových souborů Q # bude následovat po `open Microsoft.Quantum.Intrinsic;` počáteční deklaraci oboru názvů direktivou.
<xref:microsoft.quantum.core>Obor názvů se automaticky otevře, takže funkce, jako například, <xref:microsoft.quantum.core.length> lze použít bez `open` příkazu.

### <a name="common-single-qubit-unitary-operations"></a>Běžné operace s jedním qubit jednotkou ###

Předehru také definuje mnoho běžných [qubit operací](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).
Všechny tyto operace umožňují `Controlled` `Adjoint` funktory i.

#### <a name="pauli-operators"></a>Pauli operátory ####

<xref:microsoft.quantum.intrinsic.x>Operace implementuje operátor Pauli $X $.
Tato situace se někdy označuje také jako `NOT` Brána.
Má signaturu `(Qubit => Unit is Adj + Ctl)` .
Odpovídá qubit jednotkám:

\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % fixme: aktuálně používá napadení quadwhack.
1 & 0 \end{bmatrix} \end{Equation}

<xref:microsoft.quantum.intrinsic.y>Operace implementuje operátor Pauli $Y $.
Má signaturu `(Qubit => Unit is Adj + Ctl)` .
Odpovídá qubit jednotkám:

\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % fixme: aktuálně používá napadení quadwhack.
i & 0 \end{bmatrix} \end{Equation}

<xref:microsoft.quantum.intrinsic.z>Operace implementuje operátor Pauli $Z $.
Má signaturu `(Qubit => Unit is Adj + Ctl)` .
Odpovídá qubit jednotkám:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: aktuálně používá napadení quadwhack.
0 &-1 \end{bmatrix} \end{Equation}

Níže vidíte, že tyto transformace jsou mapované na [Bloch koule](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (osa otočení v každém případě je zvýrazněna červeně):

![Pauli operace mapované na sféru Bloch](~/media/prelude_pauliBloch.png)

Je důležité si uvědomit, že použití stejné Pauliové brány dvakrát na stejný qubit zruší operaci (protože jste nyní provedli úplné otočení 2π (360 °) na povrchu Bloch koule, čímž se dorazí zpátky na výchozí bod). Tím se nám přineseme k následující identitě:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

To může být visualised v oblasti Bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Další Cliffords s jedním qubit ####

Tato <xref:microsoft.quantum.intrinsic.h> operace implementuje bránu Hadamard.
Tím se změní Pauli $X $ a $Z $ na osy cílového qubit, například $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ a $H \ket{+} = \ket {0} $.
Má signaturu `(Qubit => Unit is Adj + Ctl)` a odpovídá qubit jednotkám v jednom:

\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % fixme: aktuálně používá napadení quadwhack.
1 &-1 \end{bmatrix} \end{Equation}

Brána Hadamard je zvláště důležitá, protože se dá použít k vytvoření nadmnožiny {0} stavů $ \ket $ a $ \ket {1} $. V Blochi sféry je nejjednodušší ho představit jako rotaci $ \ket{\psi} $ kolem osy x \pi $ radiánů ($ 180 ^ \circ $) následovanou otočením (po směru hodinových ručiček) kolem osy y podle $ \ pi/2 $ radiánů ($ 90 ^ \circ $):

![Hadamard operace mapovaná na sféru Bloch](~/media/prelude_hadamardBloch.png)

Tato <xref:microsoft.quantum.intrinsic.s> operace implementuje bránu fáze $S $.
Toto je maticová odmocnina operace Pauli $Z $.
To znamená, $S ^ 2 = Z $.
Má signaturu `(Qubit => Unit is Adj + Ctl)` a odpovídá qubit jednotkám v jednom:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: aktuálně používá napadení quadwhack.
0 & \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Rotace ####

Kromě výše uvedených Pauli a Clifford operací Q # předehru poskytuje celou řadu způsobů, jak vyjádřit rotace.
Jak je popsáno v [qubit operacích](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), možnost otáčení je zásadní pro algoritmy.

Začneme vrácením se změnami, kterou můžeme vyjádřit pomocí $H $ a $T $, kde $H $ je operace Hadamard a kde \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % fixme: to v současné době používá napadení ze čtyř back-qubit.
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} Toto je druhá odmocnina <xref:microsoft.quantum.intrinsic.s> operace, například $T ^ 2 = S $.
Brána $T $ je zase implementovaná <xref:microsoft.quantum.intrinsic.t> operací a má signaturu `(Qubit => Unit is Adj + Ctl)` , která značí, že se jedná o jednotnou operaci na jednom qubit.

I když je to v zásadě dostačující pro popsání jakékoli jakékoli operace s jedním qubit, mohou mít různé cílové počítače efektivnější reprezentace o Paulich operátorech, takže předehru obsahuje nejrůznější způsoby, jak convienently vyjádřit v takových rotacích.
Nejběžnější je <xref:microsoft.quantum.intrinsic.r> operace, která implementuje otočení kolem zadané osy Pauli, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} kde $ \sigma $ je operátor Pauli, $ \phi $ je úhel a kde $ \exp $ představuje exponenciální hodnotu matice.
Má signaturu `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , kde první dvě části vstupu reprezentují klasické argumenty $ \sigma $ a $ \phi $ potřebné k určení jednotkového operátoru $R (\sigma, \phi) $.
Částečně se dá použít $ \sigma $ a $ \phi $, aby se získala operace, jejíž typ je jedna qubit jednotně.
Například `R(PauliZ, PI() / 4, _)` je typu `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> <xref:microsoft.quantum.intrinsic.r>Operace rozdělí vstupní úhel o 2 a násobí ho hodnotou-1.
> Pro $Z $ rotace to znamená, že $ \ket {0} $ eigenstate je otočeno pomocí $-\phi/$2 a $ \ket {1} $ eigenstate je otočeno $ \phi/$2, takže $ \ket {1} $ eigenstate je otočen $ \phi $ vzhledem k $ \ket {0} $ eigenstate.
>
> Konkrétně to znamená, že `T` a `R(PauliZ, PI() / 8, _)` liší se pouze nepodstatnými [globálními fázemi](xref:microsoft.quantum.glossary#global-phase).
> Z tohoto důvodu se $T $ někdy označuje jako brána $ \frac{\pi} {8} $.
>
> Všimněte si také, že `PauliI` v jednoduchém otočení se aplikuje globální fáze $ \phi/$2. I když tyto fáze nejsou důležité, jak je uvedeno v [koncepčních dokumentech](xref:microsoft.quantum.concepts.qubit), jsou relevantní pro řízená `PauliI` otočení.

V rámci algoritmů doby použitelnosti je často užitečné vyjádřit rotace jako dyadic zlomky, jako je $ \phi = \pi k/2 ^ n $ pro některá $k \in \mathbb{Z} $ a $n \in \mathbb{N} $.
<xref:microsoft.quantum.intrinsic.rfrac>Operace implementuje otočení kolem zadané osy Pauli pomocí této konvence.
Liší se od <xref:microsoft.quantum.intrinsic.r> v tom, že úhel otočení je zadán jako dva vstupy typu `Int` , interpretovány jako dyadic zlomek.
Proto `RFrac` má signaturu `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .
Implementuje jedinou qubit jednotk $ \exp (i \pi k \sigma/2 ^ n) $, kde $ \sigma $ je Pauli matice odpovídající prvnímu argumentu, $k $ je druhý argument a $n $ je třetí argument.
`RFrac(_,k,n,_)`je stejná jako `R(_,-πk/2^n,_)` ; Všimněte si, že úhel je *záporný* pro zlomek.

<xref:microsoft.quantum.intrinsic.rx>Operace implementuje otočení kolem osy Pauli $X $.
Má signaturu `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rx(_, _)`je stejná jako `R(PauliX, _, _)` .

<xref:microsoft.quantum.intrinsic.ry>Operace implementuje otočení kolem osy Pauli $Y $.
Má signaturu `((Double, Qubit) => Unit is Adj + Ctl)` .
`Ry(_, _)`je stejná jako `R(PauliY,_ , _)` .

<xref:microsoft.quantum.intrinsic.rz>Operace implementuje otočení kolem osy Pauli $Z $.
Má signaturu `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rz(_, _)`je stejná jako `R(PauliZ, _, _)` .

<xref:microsoft.quantum.intrinsic.r1>Operace implementuje rotaci o danou velikost kolem $ \ket {1} $, $-$1 eigenstate z $Z $.
Má signaturu `((Double, Qubit) => Unit is Adj + Ctl)` .
`R1(phi,_)`je stejný jako `R(PauliZ,phi,_)` následováno `R(PauliI,-phi,_)` .

<xref:microsoft.quantum.intrinsic.r1frac>Operace implementuje zlomkové otočení o zadanou hodnotu kolem hodnoty z = 1 eigenstate.
Má signaturu `((Int,Int, Qubit) => Unit is Adj + Ctl)` .
`R1Frac(k,n,_)`je stejný jako `RFrac(PauliZ,-k.n+1,_)` následováno `RFrac(PauliI,k,n+1,_)` .

Příklad operace otočení (kolem osy Pauli $Z $, v této instanci) mapované na Bloch koule, je uveden níže:

![Operace otočení mapovaná na sféru Bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operace s více qubit ####

Kromě qubit operací uvedených výše definuje předehru také několik operací s více qubit.

Nejprve <xref:microsoft.quantum.intrinsic.cnot> operace provede standardní řízenou `NOT` bránu, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & \\ \\ 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}.
\end{Equation} má signaturu `((Qubit, Qubit) => Unit is Adj + Ctl)` , která představuje $ \operatorname{CNOT} $ chová unitarily na dvou individuálních qubits.
`CNOT(q1, q2)`je stejná jako `(Controlled X)([q1], q2)` .
Vzhledem k `Controlled` tomu, že funktor umožňuje řízení v registru, používáme literál pole `[q1]` k označení toho, že chceme mít pouze jeden ovládací prvek.

Tato <xref:microsoft.quantum.intrinsic.ccnot> operace provádí nebránu s neřízenými dvěma procesory, někdy také známou jako Toffoli brána.
Má signaturu `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .
`CCNOT(q1, q2, q3)`je stejná jako `(Controlled X)([q1, q2], q3)` .

<xref:microsoft.quantum.intrinsic.swap>Operace prohodí stavy se dvěma qubitsy.
To znamená, že implementuje jednotnou matrici \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} má signaturu `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)`je ekvivalentem pro `CNOT(q1, q2)` následovaný `CNOT(q2, q1)` a pak `CNOT(q1, q2)` .

> [!NOTE]
> Brána *swap není stejná* jako změna uspořádání prvků proměnné s typem `Qubit[]` .
> Použití `SWAP(q1, q2)` způsobí změnu stavu qubits, na který odkazuje `q1` a `q2` , zatímco `let swappedRegister = [q2, q1];` pouze to ovlivňuje způsob, jakým odkazujeme na tyto qubits.
> Kromě toho `(Controlled SWAP)([q0], (q1, q2))` umožňuje, `SWAP` aby bylo možné nastavit stav třetího qubit, který nemůžeme reprezentovat prvky.
> Brána kontrolovaného zahození, označovaná také jako brána Fredkin, je dostatečně výkonná pro zahrnutí všech klasických výpočtů.

Nakonec předehru poskytuje dvě operace pro reprezentaci exponenciálních hodnot operátorů Pauli s více qubit.
<xref:microsoft.quantum.intrinsic.exp>Operace provádí rotaci na základě tensor produktu Paulich matric, jak je reprezentované qubit jednotkou \begin{Equation} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} kde $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ je sekvence operátorů s jedním qubitm Pauli a kde $ \phi $ je úhel.
`Exp`Rotace představuje $ \vec{\sigma} $ jako pole `Pauli` prvků, takže má signaturu `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

<xref:microsoft.quantum.intrinsic.expfrac>Operace provede stejnou rotaci pomocí dyadic zlomkového zápisu popsaného výše.
Má signaturu `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .

> [!WARNING]
> Exponenciální podíly tensor produktu operátorů Pauli nejsou stejné jako tensor produkty exponenciálních operátorů Pauli.
> To znamená, $e ^ {i (Z \otimes Z) \phi} \Ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Měření ###

Při měření odpovídá eigenvalue + 1 operátoru, který je změřen jako `Zero` výsledek, a-1 eigenvalue na `One` výsledek.

> [!NOTE]
> I když se tato konvence může zdát lichá, má dvě skvělé výhody.
> Nejprve se bude jednat o výsledek $ \ket {0} $, který je reprezentován `Result` hodnotou `Zero` , zatímco pozorování $ \ket {1} $ odpovídá `One` .
> Za druhé můžeme napsat, že eigenvalue $ \lambda $ odpovídající výsledku $r $ je $ \lambda = (-1) ^ r $.

Měření operací nepodporuje ani `Adjoint` `Controlled` funktor.

Tato <xref:microsoft.quantum.intrinsic.measure> operace provede společné měření jednoho nebo více qubits v zadaném produktu Pauli Operators.
Pokud se pole Pauli a qubit liší od různých délek, operace se nezdařila.
`Measure`má signaturu `((Pauli[], Qubit[]) => Result)` .

Počítejte s tím, že společná měření není shodná s měřením jednotlivých qubit jednotlivě.
Zvažte například stav $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.
Měření $Z _0 $ a $Z _1 každou jednotlivě získáme výsledky $r _0 = $1 a $r _1 = $1.
Měření $Z _0 Z_1 $ ale získáme jediný výsledek $r _ {\textrm{Joint}} = $0, který představuje, že je dvojice $ \ket {11} $ kladná.
Vložit jinak, $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{Joint}}) $.
Vzhledem k tomu, že se vám od tohoto měření učí *jenom* parita, jsou zachovány všechny informace o počtu procesorů, které jsou reprezentované na pozici mezi 2 2 – qubit stavy pozitivní parity, $ \ket {00} $ a $ \ket {11} $.
Tato vlastnost bude v podstatě pozdější, protože se zabývá opravami chyb.

Pro usnadnění práce předehru poskytuje také dvě další operace pro měření qubits.
Vzhledem k tomu, že provádění qubit měření je poměrně běžné, definuje předehru pro tento případ Zkrácený Zkrácený tvar.
Tato <xref:microsoft.quantum.intrinsic.m> operace měří operátor Pauli $Z $ v jednom qubit a má signaturu `(Qubit => Result)` .
`M(q)`je ekvivalentem k `Measure([PauliZ], [q])` .

<xref:microsoft.quantum.measurement.multim>Měří operátor Pauli $Z $ *samostatně* pro každé pole qubits a vrací *pole* `Result` hodnot získaných pro každé qubit.
V některých případech je to možné optimalizovat. Má signaturu ( `Qubit[] => Result[])` .
`MultiM(qs)`je ekvivalentem:

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
Například <xref:microsoft.quantum.math> obor názvů definuje užitečné operace, jako například <xref:microsoft.quantum.math.sin> a <xref:microsoft.quantum.math.log> .
Implementace poskytovaná vývojovou sadou pro plnění z více systémů používá knihovnu klasických tříd .NET Base, a proto může zahrnovat další komunikaci s výměnou mezi programy a jejich klasickými ovladači.
I když to nepředstavuje problém pro místní simulátor, může to být problém s výkonem při použití vzdáleného simulátoru nebo skutečného hardwaru jako cílového počítače.
V takovém případě může jednotlivý cílový počítač zmírnit tento dopad na výkon tím, že tyto operace přepíše verze, které jsou pro konkrétní systém efektivnější.

### <a name="math"></a>Matematické ###

<xref:microsoft.quantum.math>Obor názvů poskytuje mnoho užitečných funkcí z [ `System.Math` třídy](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)knihovny základní třídy .NET.
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

Nakonec <xref:microsoft.quantum.bitwise> obor názvů poskytuje několik užitečných funkcí pro manipulaci s celými čísly prostřednictvím bitových operátorů.
Například <xref:microsoft.quantum.bitwise.parity> vrátí bitovou paritu celého čísla jako jiné celé číslo.
