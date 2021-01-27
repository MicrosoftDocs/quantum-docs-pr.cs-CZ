---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e09c9da500889dfcb514d0a02dec957bfaa70e1c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851394"
---
# <a name="inversemodl-function"></a>InverseModL – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí $b $ tak, že $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Vstup

### <a name="a--bigint"></a>a: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Počet, který se obrátí


### <a name="modulus--bigint"></a>Modulus: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Zbytek v závislosti na tom, které hodnoty jsou obráceny



## <a name="output--bigint"></a>Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Integer $b $, což $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.