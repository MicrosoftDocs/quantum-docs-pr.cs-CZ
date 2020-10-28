---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Uživatelem definovaný typ PhaseLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706352"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="f6ecd-102">Uživatelem definovaný typ PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="f6ecd-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="f6ecd-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f6ecd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f6ecd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6ecd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6ecd-105">Celá čísla bez znaménka ve formátu Little endian v QFT bázi.</span><span class="sxs-lookup"><span data-stu-id="f6ecd-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="f6ecd-106">Pokud má například $ \ket{x} $ kódování Integer $x $ v rámci výpočtu na úrovni Little endian, pak $ \operatorname{QFTLE} \ket{x} $ je kódování $x $ v QFT.</span><span class="sxs-lookup"><span data-stu-id="f6ecd-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="f6ecd-107">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f6ecd-107">Remarks</span></span>

<span data-ttu-id="f6ecd-108">V dokumentaci se zkrátí `PhaseLittleEndian` `PhaseLE` .</span><span class="sxs-lookup"><span data-stu-id="f6ecd-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6ecd-109">Viz také</span><span class="sxs-lookup"><span data-stu-id="f6ecd-109">See Also</span></span>

- [<span data-ttu-id="f6ecd-110">Microsoft. proQFT. Canon.</span><span class="sxs-lookup"><span data-stu-id="f6ecd-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="f6ecd-111">Microsoft. proQFTLE. Canon.</span><span class="sxs-lookup"><span data-stu-id="f6ecd-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)