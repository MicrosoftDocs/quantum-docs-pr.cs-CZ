---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Uživatelem definovaný typ PhaseLittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222418"
---
# <a name="phaselittleendian-user-defined-type"></a>Uživatelem definovaný typ PhaseLittleEndian

Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)

Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Celá čísla bez znaménka ve formátu Little endian v QFT bázi.

Pokud má například $ \ket{x} $ kódování Integer $x $ v rámci výpočtu na úrovni Little endian, pak $ \operatorname{QFTLE} \ket{x} $ je kódování $x $ v QFT.

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Poznámky

V dokumentaci se zkrátí `PhaseLittleEndian` `PhaseLE` .

## <a name="see-also"></a>Viz také

- [Microsoft. proQFT. Canon.](xref:Microsoft.Quantum.Canon.QFT)
- [Microsoft. proQFTLE. Canon.](xref:Microsoft.Quantum.Canon.QFTLE)