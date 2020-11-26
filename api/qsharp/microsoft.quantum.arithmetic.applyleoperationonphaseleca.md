---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLECA
title: Operace ApplyLEOperationOnPhaseLECA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLECA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 4762eb17b4c11e46b5b94498b7fc8fd2f855c659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190679"
---
# <a name="applyleoperationonphaseleca-operation"></a><span data-ttu-id="afbe3-102">Operace ApplyLEOperationOnPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="afbe3-102">ApplyLEOperationOnPhaseLECA operation</span></span>

<span data-ttu-id="afbe3-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="afbe3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="afbe3-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="afbe3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="afbe3-105">Použije operaci, která <xref:microsoft.quantum.arithmetic.phaselittleendian> jako vstup převezme registraci v cílovém registru typu <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="afbe3-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="afbe3-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="afbe3-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="afbe3-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="afbe3-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="afbe3-108">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="afbe3-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="afbe3-109">cíl: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="afbe3-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="afbe3-110">Registr, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="afbe3-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="afbe3-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afbe3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="afbe3-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="afbe3-112">Remarks</span></span>

<span data-ttu-id="afbe3-113">Registr se transformuje na `LittleEndian` použití <xref:microsoft.quantum.canon.qftle> a se pak vrátí do původní reprezentace po použití `op` .</span><span class="sxs-lookup"><span data-stu-id="afbe3-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="afbe3-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="afbe3-114">See Also</span></span>

- [<span data-ttu-id="afbe3-115">Microsoft. proApplyLEOperationonPhaseLE. Canon.</span><span class="sxs-lookup"><span data-stu-id="afbe3-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="afbe3-116">Microsoft. proApplyLEOperationonPhaseLEA. Canon.</span><span class="sxs-lookup"><span data-stu-id="afbe3-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="afbe3-117">Microsoft. proApplyLEOperationonPhaseLEC. Canon.</span><span class="sxs-lookup"><span data-stu-id="afbe3-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)