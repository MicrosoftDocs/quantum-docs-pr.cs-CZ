---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195371"
---
# <a name="inversemodi-function"></a>InverseModI – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí $b $ tak, že $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a>Vstup

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Počet, který se obrátí


### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)

Zbytek v závislosti na tom, které hodnoty jsou obráceny



## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)

Integer $b $, což $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.