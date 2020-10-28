---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operace QFTLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698913"
---
# <a name="qftle-operation"></a><span data-ttu-id="762b9-102">Operace QFTLE</span><span class="sxs-lookup"><span data-stu-id="762b9-102">QFTLE operation</span></span>

<span data-ttu-id="762b9-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="762b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="762b9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="762b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="762b9-105">Provádí operaci Fourierova transformace v registru s jednou hodnotou, která obsahuje celé číslo v reprezentaci Little-endian.</span><span class="sxs-lookup"><span data-stu-id="762b9-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="762b9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="762b9-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="762b9-107">QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="762b9-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="762b9-108">Registrování v registru, na které se používá Fourierova transformace</span><span class="sxs-lookup"><span data-stu-id="762b9-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="762b9-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="762b9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="762b9-110">Poznámky</span><span class="sxs-lookup"><span data-stu-id="762b9-110">Remarks</span></span>

<span data-ttu-id="762b9-111">U vstupu a výstupu se předpokládá kódování ve Little endian.</span><span class="sxs-lookup"><span data-stu-id="762b9-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="762b9-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="762b9-112">See Also</span></span>

- [<span data-ttu-id="762b9-113">Microsoft. proQFT. Canon.</span><span class="sxs-lookup"><span data-stu-id="762b9-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)