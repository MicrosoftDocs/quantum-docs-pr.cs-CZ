---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210740"
---
# <a name="expmodl-function"></a>ExpModL – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí celé číslo umocněné na daný příkon s ohledem na dané zbytky.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Popis

ExpBase $, Power by vám podíváme na to, co je to $x $, Power by $p $ a $N modulům.
Funkce vrátí $x ^ p \operatorname{mod} N $.

Předpokládáme, že $N $, $x $ jsou kladné a výkon je nezáporný.

## <a name="input"></a>Vstup

### <a name="expbase--bigint"></a>expBase: [bigint](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>napájení: [bigint](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>Modulus: [bigint](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Poznámky

Doba trvá v poměru k počtu bitů v `power` , nikoli na `power` samotném.