---
uid: Microsoft.Quantum.Arithmetic.Invert2sSI
title: Operace Invert2sSI
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Invert2sSI
qsharp.summary: Inverts a given integer modulo 2's complement.
ms.openlocfilehash: e86a5f8586cf438189c19da75c60cfd97632dcb1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843135"
---
# <a name="invert2ssi-operation"></a><span data-ttu-id="2c4ec-102">Operace Invert2sSI</span><span class="sxs-lookup"><span data-stu-id="2c4ec-102">Invert2sSI operation</span></span>

<span data-ttu-id="2c4ec-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2c4ec-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2c4ec-104">Balíček: [Microsoft. prodoby. NUMERIC](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="2c4ec-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="2c4ec-105">Obrátí daný celočíselný doplněk modulo 2.</span><span class="sxs-lookup"><span data-stu-id="2c4ec-105">Inverts a given integer modulo 2's complement.</span></span>

```qsharp
operation Invert2sSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2c4ec-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2c4ec-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="2c4ec-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2c4ec-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="2c4ec-108">n-bit podepsané celé číslo (SignedLittleEndian) bude mít opačný doplněk modulo 2.</span><span class="sxs-lookup"><span data-stu-id="2c4ec-108">n-bit signed integer (SignedLittleEndian), will be inverted modulo 2's complement.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2c4ec-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2c4ec-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

