---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857037"
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