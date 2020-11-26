---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEA
title: Operace ApplyLEOperationOnPhaseLEA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 408bd4e5d7146a74d7aec233765a63b2086b8ede
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190849"
---
# <a name="applyleoperationonphaselea-operation"></a><span data-ttu-id="03605-102">Operace ApplyLEOperationOnPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="03605-102">ApplyLEOperationOnPhaseLEA operation</span></span>

<span data-ttu-id="03605-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="03605-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="03605-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03605-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03605-105">Použije operaci, která <xref:microsoft.quantum.arithmetic.phaselittleendian> jako vstup převezme registraci v cílovém registru typu <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="03605-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="03605-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="03605-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj"></a><span data-ttu-id="03605-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ.</span><span class="sxs-lookup"><span data-stu-id="03605-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="03605-108">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="03605-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="03605-109">cíl: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="03605-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="03605-110">Registr, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="03605-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="03605-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03605-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="03605-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="03605-112">Remarks</span></span>

<span data-ttu-id="03605-113">Registr se transformuje na `LittleEndian` použití <xref:microsoft.quantum.canon.qftle> a se pak vrátí do původní reprezentace po použití `op` .</span><span class="sxs-lookup"><span data-stu-id="03605-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="03605-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="03605-114">See Also</span></span>

- [<span data-ttu-id="03605-115">Microsoft. proApplyLEOperationonPhaseLE. Canon.</span><span class="sxs-lookup"><span data-stu-id="03605-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="03605-116">Microsoft. proApplyLEOperationonPhaseLEC. Canon.</span><span class="sxs-lookup"><span data-stu-id="03605-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="03605-117">Microsoft. proApplyLEOperationonPhaseLECA. Canon.</span><span class="sxs-lookup"><span data-stu-id="03605-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)