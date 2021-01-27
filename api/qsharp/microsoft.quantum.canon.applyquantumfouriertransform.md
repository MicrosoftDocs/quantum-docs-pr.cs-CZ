---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Operace ApplyQuantumFourierTransform
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844763"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="5e65a-102">Operace ApplyQuantumFourierTransform</span><span class="sxs-lookup"><span data-stu-id="5e65a-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="5e65a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5e65a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5e65a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e65a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e65a-105">Provádí operaci Fourierova transformace v registru s jednou hodnotou, která obsahuje celé číslo v reprezentaci Little-endian.</span><span class="sxs-lookup"><span data-stu-id="5e65a-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5e65a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="5e65a-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="5e65a-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e65a-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5e65a-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="5e65a-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e65a-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e65a-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5e65a-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="5e65a-110">Remarks</span></span>

<span data-ttu-id="5e65a-111">U vstupu a výstupu se předpokládá kódování ve Little endian.</span><span class="sxs-lookup"><span data-stu-id="5e65a-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e65a-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="5e65a-112">See Also</span></span>

- [<span data-ttu-id="5e65a-113">Microsoft. proApplyQuantumFourierTransformBE. Canon.</span><span class="sxs-lookup"><span data-stu-id="5e65a-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)