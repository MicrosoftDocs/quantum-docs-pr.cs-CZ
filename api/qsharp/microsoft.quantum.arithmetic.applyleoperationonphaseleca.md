---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLECA
title: Operace ApplyLEOperationOnPhaseLECA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLECA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 024eb923d8e09ecb75a95dd61d300fd0d643c7ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843741"
---
# <a name="applyleoperationonphaseleca-operation"></a><span data-ttu-id="4d66a-102">Operace ApplyLEOperationOnPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="4d66a-102">ApplyLEOperationOnPhaseLECA operation</span></span>

<span data-ttu-id="4d66a-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4d66a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4d66a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d66a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d66a-105">Použije operaci, která <xref:microsoft.quantum.arithmetic.phaselittleendian> jako vstup převezme registraci v cílovém registru typu <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="4d66a-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4d66a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4d66a-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="4d66a-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="4d66a-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4d66a-108">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="4d66a-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="4d66a-109">cíl: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4d66a-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="4d66a-110">Registr, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="4d66a-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d66a-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d66a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4d66a-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4d66a-112">Remarks</span></span>

<span data-ttu-id="4d66a-113">Registr se transformuje na `LittleEndian` použití <xref:microsoft.quantum.canon.qftle> a se pak vrátí do původní reprezentace po použití `op` .</span><span class="sxs-lookup"><span data-stu-id="4d66a-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d66a-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="4d66a-114">See Also</span></span>

- [<span data-ttu-id="4d66a-115">Microsoft. proApplyLEOperationonPhaseLE. Canon.</span><span class="sxs-lookup"><span data-stu-id="4d66a-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="4d66a-116">Microsoft. proApplyLEOperationonPhaseLEA. Canon.</span><span class="sxs-lookup"><span data-stu-id="4d66a-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="4d66a-117">Microsoft. proApplyLEOperationonPhaseLEC. Canon.</span><span class="sxs-lookup"><span data-stu-id="4d66a-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)