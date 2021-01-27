---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operace QFTLE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852281"
---
# <a name="qftle-operation"></a><span data-ttu-id="0e052-102">Operace QFTLE</span><span class="sxs-lookup"><span data-stu-id="0e052-102">QFTLE operation</span></span>

<span data-ttu-id="0e052-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0e052-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0e052-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e052-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e052-105">Provádí operaci Fourierova transformace v registru s jednou hodnotou, která obsahuje celé číslo v reprezentaci Little-endian.</span><span class="sxs-lookup"><span data-stu-id="0e052-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0e052-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="0e052-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="0e052-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0e052-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0e052-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="0e052-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e052-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e052-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0e052-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="0e052-110">Remarks</span></span>

<span data-ttu-id="0e052-111">U vstupu a výstupu se předpokládá kódování ve Little endian.</span><span class="sxs-lookup"><span data-stu-id="0e052-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e052-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="0e052-112">See Also</span></span>

- [<span data-ttu-id="0e052-113">Microsoft. proQFT. Canon.</span><span class="sxs-lookup"><span data-stu-id="0e052-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)