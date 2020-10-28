---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operace MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707176"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="bc200-102">Operace MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="bc200-102">MeasureInteger operation</span></span>

<span data-ttu-id="bc200-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bc200-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bc200-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc200-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc200-105">Měří obsah v registru a převede ho na celé číslo.</span><span class="sxs-lookup"><span data-stu-id="bc200-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="bc200-106">Měření se provádí s ohledem na standardní výpočetní základ, tj. eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="bc200-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="bc200-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="bc200-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="bc200-108">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bc200-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bc200-109">V rámci kódování ve Little endian se registruje.</span><span class="sxs-lookup"><span data-stu-id="bc200-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="bc200-110">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc200-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc200-111">Unsigned integer obsahující měřenou hodnotu `target` .</span><span class="sxs-lookup"><span data-stu-id="bc200-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc200-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="bc200-112">Remarks</span></span>

<span data-ttu-id="bc200-113">Tato operace obnoví vstupní registr do stavu $ \ket{00\cdots 0} $, který je vhodný pro uvolnění zpět na cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="bc200-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc200-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="bc200-114">See Also</span></span>

- [<span data-ttu-id="bc200-115">Microsoft. proMeasureIntegerBE. Canon.</span><span class="sxs-lookup"><span data-stu-id="bc200-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)