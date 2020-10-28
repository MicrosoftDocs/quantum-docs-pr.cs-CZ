---
uid: Microsoft.Quantum.Canon.QFT
title: Operace QFT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698917"
---
# <a name="qft-operation"></a><span data-ttu-id="3696c-102">Operace QFT</span><span class="sxs-lookup"><span data-stu-id="3696c-102">QFT operation</span></span>

<span data-ttu-id="3696c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3696c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3696c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3696c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3696c-105">Provádí operaci Fourierova transformace v rámci registru s velkým objemem, který obsahuje celé číslo v reprezentaci big-endian.</span><span class="sxs-lookup"><span data-stu-id="3696c-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="3696c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3696c-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="3696c-107">QS: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="3696c-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="3696c-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="3696c-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3696c-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3696c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3696c-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3696c-110">Remarks</span></span>

<span data-ttu-id="3696c-111">U vstupu a výstupu se předpokládá, že jsou v kódování big endian.</span><span class="sxs-lookup"><span data-stu-id="3696c-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="3696c-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="3696c-112">See Also</span></span>

- [<span data-ttu-id="3696c-113">Microsoft. proApplyQuantumFourierTransformBE. Canon.</span><span class="sxs-lookup"><span data-stu-id="3696c-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)