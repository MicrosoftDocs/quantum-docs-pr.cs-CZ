---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704408"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="cedbd-102">CControlledA – funkce</span><span class="sxs-lookup"><span data-stu-id="cedbd-102">CControlledA function</span></span>

<span data-ttu-id="cedbd-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cedbd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cedbd-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cedbd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cedbd-105">V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true.</span><span class="sxs-lookup"><span data-stu-id="cedbd-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="cedbd-106">Pokud k `false` tomu nedojde, nic se nestane.</span><span class="sxs-lookup"><span data-stu-id="cedbd-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="cedbd-107">Modifikátor `A` označuje, že operace je sousední.</span><span class="sxs-lookup"><span data-stu-id="cedbd-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="cedbd-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="cedbd-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="cedbd-109">op: t => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cedbd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="cedbd-110">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="cedbd-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="cedbd-111">Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) =>á [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="cedbd-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="cedbd-112">Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="cedbd-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cedbd-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cedbd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cedbd-114">'S</span><span class="sxs-lookup"><span data-stu-id="cedbd-114">'T</span></span>

<span data-ttu-id="cedbd-115">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="cedbd-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cedbd-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="cedbd-116">See Also</span></span>

- [<span data-ttu-id="cedbd-117">Microsoft. proCControlled. Canon.</span><span class="sxs-lookup"><span data-stu-id="cedbd-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)