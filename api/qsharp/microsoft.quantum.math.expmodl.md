---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708535"
---
# <a name="expmodl-function"></a>ExpModL – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček [](https://nuget.org/packages/)


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