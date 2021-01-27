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
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="6e681-102">Uživatelem definovaný typ PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="6e681-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="6e681-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6e681-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6e681-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e681-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e681-105">Celá čísla bez znaménka ve formátu Little endian v QFT bázi.</span><span class="sxs-lookup"><span data-stu-id="6e681-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="6e681-106">Pokud má například $ \ket{x} $ kódování Integer $x $ v rámci výpočtu na úrovni Little endian, pak $ \operatorname{QFTLE} \ket{x} $ je kódování $x $ v QFT.</span><span class="sxs-lookup"><span data-stu-id="6e681-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="6e681-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="6e681-107">Remarks</span></span>

<span data-ttu-id="6e681-108">V dokumentaci se zkrátí `PhaseLittleEndian` `PhaseLE` .</span><span class="sxs-lookup"><span data-stu-id="6e681-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e681-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="6e681-109">See Also</span></span>

- [<span data-ttu-id="6e681-110">Microsoft. proQFT. Canon.</span><span class="sxs-lookup"><span data-stu-id="6e681-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="6e681-111">Microsoft. proQFTLE. Canon.</span><span class="sxs-lookup"><span data-stu-id="6e681-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)