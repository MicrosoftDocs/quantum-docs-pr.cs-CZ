---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: Operace ApplyPhaseLEOperationOnLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: adccad53e8d874cb2879d7005711624bbcc69201
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190764"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="7e1d6-102">Operace ApplyPhaseLEOperationOnLE</span><span class="sxs-lookup"><span data-stu-id="7e1d6-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="7e1d6-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7e1d6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7e1d6-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e1d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e1d6-105">Použije operaci, která <xref:microsoft.quantum.arithmetic.littleendian> jako vstup převezme registraci v cílovém registru typu <xref:microsoft.quantum.arithmetic.phaselittleendian> .</span><span class="sxs-lookup"><span data-stu-id="7e1d6-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7e1d6-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7e1d6-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="7e1d6-107">op: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) PhaseLittleEndian</span><span class="sxs-lookup"><span data-stu-id="7e1d6-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7e1d6-108">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="7e1d6-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="7e1d6-109">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7e1d6-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7e1d6-110">Registr, na který se operace používá</span><span class="sxs-lookup"><span data-stu-id="7e1d6-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7e1d6-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e1d6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7e1d6-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7e1d6-112">Remarks</span></span>

<span data-ttu-id="7e1d6-113">Registr se transformuje na `PhaseLittleEndian` použití <xref:microsoft.quantum.canon.qftle> a se pak vrátí do původní reprezentace po použití `op` .</span><span class="sxs-lookup"><span data-stu-id="7e1d6-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e1d6-114">Viz také</span><span class="sxs-lookup"><span data-stu-id="7e1d6-114">See Also</span></span>

- [<span data-ttu-id="7e1d6-115">Microsoft. proApplyPhaseLEOperationonLEA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7e1d6-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="7e1d6-116">Microsoft. proApplyPhaseLEOperationonLEA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7e1d6-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="7e1d6-117">Microsoft. proApplyPhaseLEOperationonLECA. Canon.</span><span class="sxs-lookup"><span data-stu-id="7e1d6-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)