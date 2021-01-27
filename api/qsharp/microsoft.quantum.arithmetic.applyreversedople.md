---
uid: Microsoft.Quantum.Arithmetic.ApplyReversedOpLE
title: Operace ApplyReversedOpLE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyReversedOpLE
qsharp.summary: Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.
ms.openlocfilehash: 5f26a25afe5e3d52bae7f7c1b9c8146e5f8a747c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843547"
---
# <a name="applyreversedople-operation"></a><span data-ttu-id="eb7c8-102">Operace ApplyReversedOpLE</span><span class="sxs-lookup"><span data-stu-id="eb7c8-102">ApplyReversedOpLE operation</span></span>

<span data-ttu-id="eb7c8-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="eb7c8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="eb7c8-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb7c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb7c8-105">Aplikuje operaci, která se zařadí do registru pomocí formátu Little endian, a kódování unsigned integer ve formátu big endian.</span><span class="sxs-lookup"><span data-stu-id="eb7c8-105">Applies an operation that takes little-endian input to a register encoding an unsigned integer using big-endian format.</span></span>

```qsharp
operation ApplyReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), register : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="eb7c8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="eb7c8-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="eb7c8-107">op: [](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotka](xref:microsoft.quantum.lang-ref.unit) LittleEndian</span><span class="sxs-lookup"><span data-stu-id="eb7c8-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eb7c8-108">Operace, která funguje v registru Little-endian.</span><span class="sxs-lookup"><span data-stu-id="eb7c8-108">Operation that acts on a little-endian register.</span></span>


### <a name="register--bigendian"></a><span data-ttu-id="eb7c8-109">registrovat: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="eb7c8-109">register : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="eb7c8-110">Registr big-endian, který se má transformovat.</span><span class="sxs-lookup"><span data-stu-id="eb7c8-110">A big-endian register to be transformed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb7c8-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb7c8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="eb7c8-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="eb7c8-112">See Also</span></span>

- [<span data-ttu-id="eb7c8-113">Microsoft. prostředníky. aritmetické. ApplyReversedOpLEA</span><span class="sxs-lookup"><span data-stu-id="eb7c8-113">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [<span data-ttu-id="eb7c8-114">Microsoft. prostředníky. aritmetické. ApplyReversedOpLEC</span><span class="sxs-lookup"><span data-stu-id="eb7c8-114">Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEC)
- [<span data-ttu-id="eb7c8-115">Microsoft. prostředníky. aritmetické. ApplyReversedOpLECA</span><span class="sxs-lookup"><span data-stu-id="eb7c8-115">Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA</span></span>](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)