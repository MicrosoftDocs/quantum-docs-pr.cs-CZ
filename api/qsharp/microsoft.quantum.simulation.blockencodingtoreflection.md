---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847265"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection – funkce

Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Převede na `BlockEncoding` ekvivalentní `BLockEncodingReflection` .

To znamená, že s ohledem na `BlockEncoding` jednotkové $U $, který kóduje nějaký operátor $H $ Interest, převede ho na `BlockEncodingReflection` $U $, který kóduje stejný operátor, ale také splňuje $U ' ^ \Dagger = U ' $.
Tím se zvýší velikost pomocného registru $U $ o jeden qubit.

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Vstup

### <a name="blockencoding--blockencoding"></a>blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

`BlockEncoding`Jednotková $U $, která má být převedena na reflexi.



## <a name="output--blockencodingreflection"></a>Výstup: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Jednotková $U ' $ jednají společně na registrech `a` a `s` blokující kódování $H $ a splňuje $U ' ^ \Dagger = U ' $.

## <a name="remarks"></a>Poznámky

Tím se zvýší velikost pomocného registru $U $ o jeden qubit.

## <a name="references"></a>Reference

- Simulace Hamiltonian podle Qubitization Guang vystoupí hao nízká, Petr L. Čuangština https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Viz také

- [Microsoft. v. simulace. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. v. simulace. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)