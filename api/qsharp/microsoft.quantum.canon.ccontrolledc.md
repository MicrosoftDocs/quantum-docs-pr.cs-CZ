---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704401"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="a43b9-102">CControlledC – funkce</span><span class="sxs-lookup"><span data-stu-id="a43b9-102">CControlledC function</span></span>

<span data-ttu-id="a43b9-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a43b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a43b9-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a43b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a43b9-105">V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true.</span><span class="sxs-lookup"><span data-stu-id="a43b9-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="a43b9-106">Pokud k `false` tomu nedojde, nic se nestane.</span><span class="sxs-lookup"><span data-stu-id="a43b9-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="a43b9-107">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="a43b9-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="a43b9-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="a43b9-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="a43b9-109">op: t [=> seznamu](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="a43b9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a43b9-110">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="a43b9-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="a43b9-111">Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) = seznam CTL>ch [jednotek](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a43b9-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="a43b9-112">Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="a43b9-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a43b9-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a43b9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a43b9-114">'S</span><span class="sxs-lookup"><span data-stu-id="a43b9-114">'T</span></span>

<span data-ttu-id="a43b9-115">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="a43b9-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a43b9-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="a43b9-116">See Also</span></span>

- [<span data-ttu-id="a43b9-117">Microsoft. proCControlled. Canon.</span><span class="sxs-lookup"><span data-stu-id="a43b9-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)