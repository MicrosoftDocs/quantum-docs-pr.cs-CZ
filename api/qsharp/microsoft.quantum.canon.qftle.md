---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operace QFTLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 460e43bc7997e9efad06c58ad14822e28cc45cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205571"
---
# <a name="qftle-operation"></a><span data-ttu-id="e7a2c-102">Operace QFTLE</span><span class="sxs-lookup"><span data-stu-id="e7a2c-102">QFTLE operation</span></span>

<span data-ttu-id="e7a2c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e7a2c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e7a2c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7a2c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7a2c-105">Provádí operaci Fourierova transformace v registru s jednou hodnotou, která obsahuje celé číslo v reprezentaci Little-endian.</span><span class="sxs-lookup"><span data-stu-id="e7a2c-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e7a2c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="e7a2c-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="e7a2c-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e7a2c-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e7a2c-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="e7a2c-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="e7a2c-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e7a2c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e7a2c-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="e7a2c-110">Remarks</span></span>

<span data-ttu-id="e7a2c-111">U vstupu a výstupu se předpokládá kódování ve Little endian.</span><span class="sxs-lookup"><span data-stu-id="e7a2c-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7a2c-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="e7a2c-112">See Also</span></span>

- [<span data-ttu-id="e7a2c-113">Microsoft. proQFT. Canon.</span><span class="sxs-lookup"><span data-stu-id="e7a2c-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)