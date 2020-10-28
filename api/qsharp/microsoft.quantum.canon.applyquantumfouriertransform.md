---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Operace ApplyQuantumFourierTransform
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705097"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="79d30-102">Operace ApplyQuantumFourierTransform</span><span class="sxs-lookup"><span data-stu-id="79d30-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="79d30-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="79d30-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="79d30-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79d30-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79d30-105">Provádí operaci Fourierova transformace v registru s jednou hodnotou, která obsahuje celé číslo v reprezentaci Little-endian.</span><span class="sxs-lookup"><span data-stu-id="79d30-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="79d30-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="79d30-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="79d30-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="79d30-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="79d30-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="79d30-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="79d30-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79d30-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="79d30-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="79d30-110">Remarks</span></span>

<span data-ttu-id="79d30-111">U vstupu a výstupu se předpokládá kódování ve Little endian.</span><span class="sxs-lookup"><span data-stu-id="79d30-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="79d30-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="79d30-112">See Also</span></span>

- [<span data-ttu-id="79d30-113">Microsoft. proApplyQuantumFourierTransformBE. Canon.</span><span class="sxs-lookup"><span data-stu-id="79d30-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)