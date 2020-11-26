---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operace MeasureInteger
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222639"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="63c90-102">Operace MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="63c90-102">MeasureInteger operation</span></span>

<span data-ttu-id="63c90-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="63c90-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="63c90-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63c90-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63c90-105">Měří obsah v registru a převede ho na celé číslo.</span><span class="sxs-lookup"><span data-stu-id="63c90-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="63c90-106">Měření se provádí s ohledem na standardní výpočetní základ, tj. eigenbasis `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="63c90-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="63c90-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="63c90-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="63c90-108">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="63c90-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="63c90-109">V rámci kódování ve Little endian se registruje.</span><span class="sxs-lookup"><span data-stu-id="63c90-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="63c90-110">Výstup: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63c90-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63c90-111">Unsigned integer obsahující měřenou hodnotu `target` .</span><span class="sxs-lookup"><span data-stu-id="63c90-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="63c90-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="63c90-112">Remarks</span></span>

<span data-ttu-id="63c90-113">Tato operace obnoví vstupní registr do stavu $ \ket{00\cdots 0} $, který je vhodný pro uvolnění zpět na cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="63c90-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="63c90-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="63c90-114">See Also</span></span>

- [<span data-ttu-id="63c90-115">Microsoft. proMeasureIntegerBE. Canon.</span><span class="sxs-lookup"><span data-stu-id="63c90-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)