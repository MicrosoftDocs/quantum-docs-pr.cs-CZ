---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: Operace CompareGTSI
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: 735ae21168d8efb3e626a8f1ea36e97f5cdf8760
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707384"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="bc69e-102">Operace CompareGTSI</span><span class="sxs-lookup"><span data-stu-id="bc69e-102">CompareGTSI operation</span></span>

<span data-ttu-id="bc69e-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bc69e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bc69e-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc69e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc69e-105">Obálka pro porovnání se znaménkem pro celé číslo: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="bc69e-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="bc69e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="bc69e-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="bc69e-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bc69e-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="bc69e-108">První $n $-bitové číslo</span><span class="sxs-lookup"><span data-stu-id="bc69e-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="bc69e-109">y: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bc69e-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="bc69e-110">Druhé $n $-bitové číslo</span><span class="sxs-lookup"><span data-stu-id="bc69e-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="bc69e-111">výsledek: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bc69e-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bc69e-112">Bude převráceno, pokud $xs > y $</span><span class="sxs-lookup"><span data-stu-id="bc69e-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc69e-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc69e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

