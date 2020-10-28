---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Operace PrepareUniformSuperposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92697148"
---
# <a name="prepareuniformsuperposition-operation"></a>Operace PrepareUniformSuperposition

Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)

Balíček [](https://nuget.org/packages/)


Vytvoří jednotnou polohu přes stavy, které zakódují 0 do `nIndices - 1` .

To znamená, že tato Jednotková $U $ vytvoří jednotnou polohu ve všech číselných stavech $0 $ to $M-$1 a zadá vstupní stav $ \ket{0\cdots 0} $. Jinými slovy $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{align} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Vstup

### <a name="nindices--int"></a>nIndices: [int](xref:microsoft.quantum.lang-ref.int)

Požadovaný počet stavů $M $ v jednotném umístění.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registr qubit, ve kterém se ukládají číselné stavy ve `LittleEndian` formátu
Tento registr musí být schopný ukládat číslo $M-$1 a předpokládá se, že bude inicializovaný ve stavu $ \ket{0\cdots 0} $.



## <a name="output--unit"></a>Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Poznámky

Tato operace je typu sousední, ale vyžaduje, aby v takovém `indexRegister` případě byla v jednotném stavu v rámci prvního `nIndices` základu.