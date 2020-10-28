---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704265"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA – funkce

Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)

Balíček [](https://nuget.org/packages/)


Vrátí operaci implementující integrátoru Trotter – Suzuki pro danou operaci.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Vstup

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

Počet operací rozloženého na časové kroky.


### <a name="op--intdoublet--unit-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operace, která přijímá vstup indexu (typ `Int` ) a vstupní čas (typ `Double` ) pro rozklad.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Vybere pořadí, ve kterém se má použít integrátor Trotter-Suzuki.
Objednávka 1 a dokonce i objednávky 2, 4, 6,... jsou aktuálně podporovány.



## <a name="output--doublet--unit-adj--ctl"></a>Výstup: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Vrátí jednotnou implementaci integrátoru Trotter – Suzuki, kde první parametr `Double` je velikost kroku integrace, a druhý parametr je cílem, na kterém se pracuje.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'S

Typ, na který má každý krok reagovat; obvykle buď `Qubit[]` nebo `Qubit` .

## <a name="remarks"></a>Poznámky

Při volání s `order` hodnotou Equal `1` vrátí tato funkce operaci, kterou lze simulovat pomocí nejnižšího řádu Trotter – Suzuki integrátor $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ tam, kde jsme následovali zápis [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) a let $ \lambda $ bude časem vývoje (reprezentovaný prvním vstupem vrácené operace), a nechat $ \{ H_j \} _ {j = 1} ^ {m} $ být sadou (zkosit-Hermitian) dynamické generátory, které `op(j, lambda, _)` jsou simulované jednotkovým operátorem $e ^ {H_j \lambda} $.

Podobně vrátí objekt `order` z `2` druhé objednávky symetrický Trotter – Suzuki integrátor $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.
\end{align} $ $

Vyšší i hodnoty `order` jsou implementovány pomocí rekurzivní konstrukce [quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).

## <a name="references"></a>Odkazy

- [*D. W. bobulovina, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)