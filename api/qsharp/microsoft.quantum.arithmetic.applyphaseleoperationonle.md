---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: Operace ApplyPhaseLEOperationOnLE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: d94fdb55e051e76dd518eff14b80d1a24516bf8a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843683"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="087e4-102">Operace ApplyPhaseLEOperationOnLE</span><span class="sxs-lookup"><span data-stu-id="087e4-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="087e4-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="087e4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="087e4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="087e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="087e4-105">Použije operaci, která <xref:microsoft.quantum.arithmetic.littleendian> jako vstup převezme registraci v cílovém registru typu <xref:microsoft.quantum.arithmetic.phaselittleendian> .</span><span class="sxs-lookup"><span data-stu-id="087e4-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="087e4-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="087e4-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="087e4-107">op: [](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="087e4-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="087e4-108">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="087e4-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="087e4-109">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="087e4-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="087e4-110">Registr, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="087e4-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="087e4-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="087e4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="087e4-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="087e4-112">Remarks</span></span>

<span data-ttu-id="087e4-113">Registr se transformuje na `PhaseLittleEndian` použití <xref:microsoft.quantum.canon.qftle> a se pak vrátí do původní reprezentace po použití `op` .</span><span class="sxs-lookup"><span data-stu-id="087e4-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="087e4-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="087e4-114">See Also</span></span>

- [<span data-ttu-id="087e4-115">Microsoft. proApplyPhaseLEOperationonLEA. Canon.</span><span class="sxs-lookup"><span data-stu-id="087e4-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="087e4-116">Microsoft. proApplyPhaseLEOperationonLEA. Canon.</span><span class="sxs-lookup"><span data-stu-id="087e4-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="087e4-117">Microsoft. proApplyPhaseLEOperationonLECA. Canon.</span><span class="sxs-lookup"><span data-stu-id="087e4-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)