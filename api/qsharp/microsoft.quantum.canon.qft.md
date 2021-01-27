---
uid: Microsoft.Quantum.Canon.QFT
title: Operace QFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852293"
---
# <a name="qft-operation"></a><span data-ttu-id="ab838-102">Operace QFT</span><span class="sxs-lookup"><span data-stu-id="ab838-102">QFT operation</span></span>

<span data-ttu-id="ab838-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ab838-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ab838-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ab838-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ab838-105">Provádí operaci Fourierova transformace v rámci registru s velkým objemem, který obsahuje celé číslo v reprezentaci big-endian.</span><span class="sxs-lookup"><span data-stu-id="ab838-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ab838-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ab838-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="ab838-107">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="ab838-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="ab838-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="ab838-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="ab838-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab838-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ab838-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ab838-110">Remarks</span></span>

<span data-ttu-id="ab838-111">U vstupu a výstupu se předpokládá, že jsou v kódování big endian.</span><span class="sxs-lookup"><span data-stu-id="ab838-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="ab838-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="ab838-112">See Also</span></span>

- [<span data-ttu-id="ab838-113">Microsoft. proApplyQuantumFourierTransformBE. Canon.</span><span class="sxs-lookup"><span data-stu-id="ab838-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)