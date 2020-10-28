---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704400"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="957e4-102">CControlledCA – funkce</span><span class="sxs-lookup"><span data-stu-id="957e4-102">CControlledCA function</span></span>

<span data-ttu-id="957e4-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="957e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="957e4-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="957e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="957e4-105">V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true.</span><span class="sxs-lookup"><span data-stu-id="957e4-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="957e4-106">Pokud k `false` tomu nedojde, nic se nestane.</span><span class="sxs-lookup"><span data-stu-id="957e4-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="957e4-107">Modifikátor `CA` označuje, že operace je ovladatelné a s sousedními poli.</span><span class="sxs-lookup"><span data-stu-id="957e4-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="957e4-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="957e4-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="957e4-109">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL a ADJ</span><span class="sxs-lookup"><span data-stu-id="957e4-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="957e4-110">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="957e4-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="957e4-111">Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL + ADJ</span><span class="sxs-lookup"><span data-stu-id="957e4-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="957e4-112">Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="957e4-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="957e4-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="957e4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="957e4-114">'S</span><span class="sxs-lookup"><span data-stu-id="957e4-114">'T</span></span>

<span data-ttu-id="957e4-115">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="957e4-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="957e4-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="957e4-116">See Also</span></span>

- [<span data-ttu-id="957e4-117">Microsoft. proCControlled. Canon.</span><span class="sxs-lookup"><span data-stu-id="957e4-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)