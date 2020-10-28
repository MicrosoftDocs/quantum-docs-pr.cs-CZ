---
title: Oprava chyb ve Q# standardních knihovnách
description: Naučte se, jak používat chyby při opravování kódů v Q# programech při ochraně stavu qubits.
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 94251e185cea65c5fc08ed70d5fba9b7b19501e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692044"
---
# <a name="error-correction"></a>Oprava chyb #

## <a name="introduction"></a>Úvod ##

Pokud jeden z klasických výpočetních prostředků chce chránit bitovou kopii proti chybám, může to často stačit k tomu, aby tento bit představoval *logický bit* opakováním datového bitu.
Například let $ \overline {0} = $0 je kódování datového bitu 0, kde používáme řádek nad popiskem 0 k označení toho, že se jedná o kódování bitu ve stavu 0.
Pokud obdobně ponecháme $ \overline {1} = $111, máme k dispozici jednoduchý kód opakování, který chrání proti libovolné bitové chybě překlopení.
To znamená, že pokud se některé ze tří bitů překlopí, můžeme obnovit stav logického bitu tím, že vyberete většinou hlasů.
I když klasická chyba je mnohem rozsáhlejší, že tento konkrétní příklad (doporučujeme [Lint Úvod do kódování](https://www.springer.com/us/book/9783540641339)), výše uvedený kód opakování již odkazuje na možný problém při ochraně stavových kódů.
To znamená, že pokud si [věta žádného klonování](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) , znamená to, že pokud si vyměříme jednotlivé qubity a v případě, že použijete stejný hlas na klasický kód výše, ztratili jsme přesné informace, které se snažíme chránit.

V nastavení pro stavové pole uvidíme, že měření je problematické. Přesto můžeme implementovat kódování uvedené výše.
To je užitečné, pokud chcete zjistit, jak můžeme provést generalizaci opravy chyb na případ.
Proto $ \ket{\overline {0} } = \ket {000} = \ket {0} \otimes \ket {0} \otimes \ket {0} $ a let $ \ket{\overline {1} } = \ket {111} $.
Po linearitě jsme pro všechny vstupy definovali náš kód opakování. např. $ \ket{\overline{+}} = (\ket{\overline {0} } + \ket{\overline {1} })/\sqrt {2} = (\ket {000} + \ket {111} )/\sqrt {2} $.
Konkrétně v důsledku překlopení chyby $X _1 $ Act v prostředních qubit jsme zjistili, že oprava potřebná v obou větvích je přesně $X _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left (X_1 \ket {000} + X_1 \ket {111} \right) \\ \\ & = \frac {1} {\sqrt {2} } \left (\ket {010} + \ket {101} \right).
\end{align} $ $

Pokud se chcete podívat, jak můžeme zjistit, že se jedná o tento případ bez měření velmi velkého stavu, který se snažíme chránit, je užitečné, abyste si vyzkoušeli, co každá z různých bitových překlopných chyb dělá u našich logických stav

| Chyba $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ |
| $X _0 $ | $ \ket {100} $ | $ \ket {011} $ |
| $X _1 $ | $ \ket {010} $ | $ \ket {101} $ |
| $X _2 $ | $ \ket {001} $ | $ \ket {110} $ |

Abychom chránili stav, který kódujeme, musíme být schopni odlišit tři chyby od sebe navzájem a z identity $ \boldone $ bez rozlišení mezi $ \ket{\overline {0} } $ a $ \ket{\overline {1} } $.
Pokud například měříme $Z _0 $, získáme jiný výsledek pro $ \ket{\overline {0} } $ a $ \ket{\overline {1} } $ v případu No-Error, takže se sbalí kódovaný stav.
Na druhé straně zvažte měření $Z _0 Z_1 $, paritu prvních dvou bitů v každém výpočetním stavu.
Načtěte si, že každé měření Pauli operátoru kontroluje, které eigenvalue se má měřit, takže pro každý stav $ \ket{\psi} $ v tabulce výše můžeme vypočítat $Z _0 Z_1 \ket{\psi} $, abyste zjistili, jestli se vrátíme $ \pm\ket{\psi} $.
Všimněte si, že $Z _0 Z_1 \ket {000} = \ket {000} $ a $Z _0 Z_1 \ket {111} = \ket {111} $, takže jsme uzavřeli, že toto měření bude stejné jako u kódovaných stavů.
Na druhé straně $Z _0 Z_1 \ket {100} =-\ket {100} $ a $Z _0 Z_1 \ket {011} =-\ket {011} $, takže výsledek měření $Z _0 Z_1 $ odhalí užitečné informace o tom, která chyba nastala.

Pokud to chcete zdůraznit, opakujeme tabulku výše, ale do každého řádku přidejte výsledky měření $Z _0 Z_1 $ a $Z _1y Z_2 $.
Poznamenejte si výsledky každého měření pomocí znaménka eigenvalue, který je pozorován, buď $ + $ nebo $-$, který odpovídá Q# `Result` hodnotám v `Zero` a v `One` uvedeném pořadí.

| Chyba $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ | Výsledek $Z _0 Z_1 $ | Výsledek $Z _1 Z_2 $ |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ | $+$ | $+$ |
| $X _0 $ | $ \ket {100} $ | $ \ket {011} $ | $-$ | $+$ |
| $X _1 $ | $ \ket {010} $ | $ \ket {101} $ | $-$ | $-$ |
| $X _2 $ | $ \ket {001} $ | $ \ket {110} $ | $+$ | $-$ |

Proto výsledky dvou měření jednoznačně určují, jakou chybu překlopení došlo k chybě, ale bez odhalení informací o tom, jaký stav je zakódovaný.
Tyto výsledky říkáme *Syndrome* a přečtěte si proces mapování Syndrome zpátky na chybu, která způsobila *obnovení* .
Zejména jsme zdůraznili, že obnovení je *klasický* postup odvození, který jako svůj vstup přebírá Syndrome, ke kterému došlo, a vrátí předpis pro opravu chyb, ke kterým mohlo dojít.

> [!NOTE]
> Výše uvedený kód překlápění lze opravit pouze proti chybám s jedním překlopením; To znamená, že `X` operace funguje na jednom qubit.
> Použití `X` na více než jeden qubit bude namapovat $ \ket{\overline {0} } $ na $ \ket{\overline {1} } $ po obnovení.
> Podobně při použití operace překlápění fáze `Z` se namapuje $ \ket{\overline {1} } $ na $-\ket{\overline {1} } $, a proto se namapuje $ \ket{\overline{+}} $ na $ \ket{\overline {-} } $.
> Obecněji je možné vytvářet kódy pro zpracování většího počtu chyb a zpracovávat chyby $Z $ a také chyby $X $.

Vhledem, jak můžeme popsat měření při opravách chyb, která působí stejným způsobem u všech stavů kódu, je podstata *formalit na stabilizaci* .
Q#Canon poskytuje rozhraní pro popis kódování a dekódování z kódů stabilizovaných a pro popis toho, jak se jedno obnovuje z chyb.
V této části popíšeme toto rozhraní a jeho aplikaci na několik jednoduchých chybných procesorů.

> [!TIP]
> Úplný Úvod k formalitám na stabilizaci je nad rámec této části.
> Čtenářům, kteří mají zájem o další informace, se dozvíte o [Gottesman 2009](https://arxiv.org/abs/0904.2557).

## <a name="representing-error-correcting-codes-in-no-locq"></a>Reprezentace chybových oprav kódů v Q# ##

Aby bylo možné zadat chyby oprav kódů, Q# Canon poskytuje několik různých uživatelsky definovaných typů:

- <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister>`= Qubit[]`: Označuje, že registr qubits by měl být interpretován jako blok kódu pro chybu s opravou kódu.
- <xref:Microsoft.Quantum.ErrorCorrection.Syndrome>`= Result[]`: Označuje, že pole výsledků měření by mělo být interpretováno jako Syndrome měřené na bloku kódu.
- <xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn>`= (Syndrome -> Pauli[])`: Označuje, že by se měla použít *Klasická* funkce k interpretaci Syndrome a vrácení opravy, která by se měla použít.
- <xref:Microsoft.Quantum.ErrorCorrection.EncodeOp>`= ((Qubit[], Qubit[]) => LogicalRegister)`: Označuje, že operace přebírá qubits, která představuje data společně s čerstvou ancilla qubits, aby vytvořila blok kódu pro chybu s opravou kódu.
- <xref:Microsoft.Quantum.ErrorCorrection.DecodeOp>`= (LogicalRegister => (Qubit[], Qubit[]))`: Všimněte si, že operace označuje blok kódu chyby správného opravy kódu do qubits dat a ancilla qubits, který slouží k reprezentaci informací Syndrome.
- <xref:Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp>`= (LogicalRegister => Syndrome)`: Označuje operaci, která by měla být použita k extrakci informací Syndrome z bloku kódu, aniž by narušila stav chráněný kódem.

Nakonec Canon poskytne <xref:Microsoft.Quantum.ErrorCorrection.QECC> typ pro shromáždění dalších typů potřebných k definování chybných hodnot při opravách kódu. V souvislosti s každým kódem doby stabilizace je délka kódu $n $, číslo $k $ logického qubits a minimální vzdálenost $d $, která je často vhodná pro seskupení do Notation ⟦ $n $, $k $, $d $ ⟧. Například <xref:Microsoft.Quantum.ErrorCorrection.BitFlipCode> funkce definuje ⟦ 3, 1, 1 ⟧ bit překlopení kódu:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Všimněte si, že `QECC` typ *not* nezahrnuje funkci obnovení.
Díky tomu můžeme změnit funkci obnovení, která se používá při opravách chyb beze změny definice samotného kódu; Tato možnost je užitečná zejména při začlenění zpětné vazby z měření popisu do modelu, který předpokládá obnovení.

Po definování kódu tímto způsobem můžeme použít <xref:Microsoft.Quantum.ErrorCorrection.Recover> operaci k zotavení z chyb:

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

Podrobněji o tom prozkoumáme v [ukázce bitové překlopení kódu](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code).

Kromě kódu překlápění, Q# je technologie Canon k dispozici s implementacemi [qubit dokonalého kódu](https://arxiv.org/abs/quant-ph/9602019)a [sedmi qubit kódem](https://arxiv.org/abs/quant-ph/9705052), který může opravit libovolnou chybu s jedním qubit.
