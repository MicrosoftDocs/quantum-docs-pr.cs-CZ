---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Uživatelem definovaný typ PhaseLittleEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843004"
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