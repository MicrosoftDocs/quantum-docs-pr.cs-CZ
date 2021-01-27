---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848375"
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