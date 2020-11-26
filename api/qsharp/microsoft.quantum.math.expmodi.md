---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228486"
---
# <a name="expmodi-function"></a>ExpModI – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí celé číslo umocněné na daný příkon s ohledem na dané zbytky.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Popis

ExpBase $, Power by vám podíváme na to, co je to $x $, Power by $p $ a $N modulům.
Funkce vrátí $x ^ p \operatorname{mod} N $.

Předpokládáme, že $N $, $x $ jsou kladné a výkon je nezáporný.

## <a name="input"></a>Vstup

### <a name="expbase--int"></a>expBase: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>napájení: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>Modulus: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Výstup: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Poznámky

Doba trvá v poměru k počtu bitů v `power` , nikoli na `power` samotném.