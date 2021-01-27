---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Operace ApplyQuantumFourierTransformBE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841570"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="dff29-102">Operace ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="dff29-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="dff29-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dff29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dff29-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dff29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dff29-105">Provádí operaci Fourierova transformace v rámci registru s velkým objemem, který obsahuje celé číslo v reprezentaci big-endian.</span><span class="sxs-lookup"><span data-stu-id="dff29-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dff29-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="dff29-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="dff29-107">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="dff29-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="dff29-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="dff29-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="dff29-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dff29-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dff29-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dff29-110">Remarks</span></span>

<span data-ttu-id="dff29-111">U vstupu a výstupu se předpokládá, že jsou v kódování big endian.</span><span class="sxs-lookup"><span data-stu-id="dff29-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="dff29-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="dff29-112">See Also</span></span>

- [<span data-ttu-id="dff29-113">Microsoft. proApproximateQFT. Canon.</span><span class="sxs-lookup"><span data-stu-id="dff29-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="dff29-114">Microsoft. proQFTLE. Canon.</span><span class="sxs-lookup"><span data-stu-id="dff29-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)