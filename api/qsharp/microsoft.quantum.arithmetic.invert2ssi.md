---
uid: Microsoft.Quantum.Arithmetic.Invert2sSI
title: Operace Invert2sSI
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Invert2sSI
qsharp.summary: Inverts a given integer modulo 2's complement.
ms.openlocfilehash: 86d90fc5406089549de0036fcaebd9dc9d188c40
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222843"
---
# <a name="invert2ssi-operation"></a><span data-ttu-id="feefe-102">Operace Invert2sSI</span><span class="sxs-lookup"><span data-stu-id="feefe-102">Invert2sSI operation</span></span>

<span data-ttu-id="feefe-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="feefe-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="feefe-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="feefe-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="feefe-105">Obrátí daný celočíselný doplněk modulo 2.</span><span class="sxs-lookup"><span data-stu-id="feefe-105">Inverts a given integer modulo 2's complement.</span></span>

```qsharp
operation Invert2sSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="feefe-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="feefe-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="feefe-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="feefe-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="feefe-108">n-bit podepsané celé číslo (SignedLittleEndian) bude mít opačný doplněk modulo 2.</span><span class="sxs-lookup"><span data-stu-id="feefe-108">n-bit signed integer (SignedLittleEndian), will be inverted modulo 2's complement.</span></span>



## <a name="output--unit"></a><span data-ttu-id="feefe-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="feefe-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

