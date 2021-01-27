---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC
title: Operace ApplyReversedOpLEC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLEC
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 74ecc705a6e3d1d59c4c4ae71d30171c12fa45ae
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843505"
---
# <a name="applyreversedoplec-operation"></a><span data-ttu-id="69096-102">Operace ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="69096-102">ApplyReversedOpLEC operation</span></span>

<span data-ttu-id="69096-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="69096-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="69096-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69096-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69096-105">Aplikuje operaci, která se zařadí do registru pomocí formátu Little endian, a kódování unsigned integer ve formátu big endian.</span><span class="sxs-lookup"><span data-stu-id="69096-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="69096-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="69096-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="69096-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian je CTL</span><span class="sxs-lookup"><span data-stu-id="69096-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="69096-108">Operace, která funguje v registru Little-endian.</span><span class="sxs-lookup"><span data-stu-id="69096-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="69096-109">registrovat: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="69096-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="69096-110">Registr big-endian, který se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="69096-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69096-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69096-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="69096-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="69096-112">See Also</span></span>

- [<span data-ttu-id="69096-113">Microsoft. prostředníky. aritmetické. ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="69096-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLE</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [<span data-ttu-id="69096-114">Microsoft. prostředníky. aritmetické. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="69096-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="69096-115">Microsoft. prostředníky. aritmetické. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="69096-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)