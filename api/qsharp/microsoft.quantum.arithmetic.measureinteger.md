---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operace MeasureInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843110"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="a3fdc-102">Operace MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="a3fdc-102">MeasureInteger operation</span></span>

<span data-ttu-id="a3fdc-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a3fdc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a3fdc-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3fdc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3fdc-105">Měří obsah v registru a převede ho na celé číslo.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="a3fdc-106">Měření se provádí s ohledem na standardní výpočetní základ, tj. eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="a3fdc-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="a3fdc-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="a3fdc-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="a3fdc-108">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a3fdc-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a3fdc-109">V rámci kódování ve Little endian se registruje.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="a3fdc-110">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3fdc-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3fdc-111">Unsigned integer obsahující měřenou hodnotu `target` .</span><span class="sxs-lookup"><span data-stu-id="a3fdc-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3fdc-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a3fdc-112">Remarks</span></span>

<span data-ttu-id="a3fdc-113">Tato operace obnoví vstupní registr do stavu $ \ket{00\cdots 0} $, který je vhodný pro uvolnění zpět na cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3fdc-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="a3fdc-114">See Also</span></span>

- [<span data-ttu-id="a3fdc-115">Microsoft. proMeasureIntegerBE. Canon.</span><span class="sxs-lookup"><span data-stu-id="a3fdc-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)