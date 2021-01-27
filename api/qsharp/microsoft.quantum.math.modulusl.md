---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842749"
---
# <a name="modulusl-function"></a>ModulusL – funkce

Obor názvů: [Microsoft.. Math](xref:Microsoft.Quantum.Math)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vypočítá kanonický zbytek `value` modulo `modulus` .

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Vstup

### <a name="value--bigint"></a>hodnota: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Hodnota, kterou je vypočítáno reziduum


### <a name="modulus--bigint"></a>Modulus: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Zbytky, podle kterých jsou zbytky vzaty, musí být kladné



## <a name="output--bigint"></a>Výstup: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Celé číslo $r $ mezi 0 a `modulus - 1` to `value - r` je dělitelé modulem.

## <a name="remarks"></a>Poznámky

Tato funkce se chová jinak, než se operátor `%` chová v jazyce C# a Q #, protože ve výsledku je vždy nezáporné celé číslo mezi 0 a `modulus - 1` , i když je hodnota záporná.