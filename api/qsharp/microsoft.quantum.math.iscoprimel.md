---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851342"
---
# <a name="iscoprimel-function"></a>IsCoprimeL – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vrátí hodnotu true, pokud $a $ a $b $ jsou souběžné a false v opačném případě.

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Vstup

### <a name="a--bigint"></a>a: [bigint](xref:microsoft.quantum.lang-ref.bigint)

první počet primality, které se testují společně


### <a name="b--bigint"></a>b: [bigint](xref:microsoft.quantum.lang-ref.bigint)

druhý počet, který provádí testování primality



## <a name="output--bool"></a>Výstup: [bool](xref:microsoft.quantum.lang-ref.bool)

True, pokud $a $ a $b $ jsou souběžné (například jejich největší společný dělitel je 1) a jinak false