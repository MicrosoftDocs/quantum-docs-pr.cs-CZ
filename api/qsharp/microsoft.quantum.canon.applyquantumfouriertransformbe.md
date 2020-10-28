---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Operace ApplyQuantumFourierTransformBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705096"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="fc6a4-102">Operace ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="fc6a4-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="fc6a4-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fc6a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fc6a4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc6a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc6a4-105">Provádí operaci Fourierova transformace v rámci registru s velkým objemem, který obsahuje celé číslo v reprezentaci big-endian.</span><span class="sxs-lookup"><span data-stu-id="fc6a4-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="fc6a4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fc6a4-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="fc6a4-107">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="fc6a4-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="fc6a4-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="fc6a4-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="fc6a4-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc6a4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fc6a4-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="fc6a4-110">Remarks</span></span>

<span data-ttu-id="fc6a4-111">U vstupu a výstupu se předpokládá, že jsou v kódování big endian.</span><span class="sxs-lookup"><span data-stu-id="fc6a4-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc6a4-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="fc6a4-112">See Also</span></span>

- [<span data-ttu-id="fc6a4-113">Microsoft. proApproximateQFT. Canon.</span><span class="sxs-lookup"><span data-stu-id="fc6a4-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="fc6a4-114">Microsoft. proQFTLE. Canon.</span><span class="sxs-lookup"><span data-stu-id="fc6a4-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)