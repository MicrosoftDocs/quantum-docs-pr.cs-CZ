---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 25ac2b35047b1c33a89149eae6d40f6f7ae3b454
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216910"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="a3a13-102">CControlledC – funkce</span><span class="sxs-lookup"><span data-stu-id="a3a13-102">CControlledC function</span></span>

<span data-ttu-id="a3a13-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a3a13-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a3a13-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3a13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3a13-105">V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true.</span><span class="sxs-lookup"><span data-stu-id="a3a13-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="a3a13-106">Pokud k `false` tomu nedojde, nic se nestane.</span><span class="sxs-lookup"><span data-stu-id="a3a13-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="a3a13-107">Modifikátor `C` označuje, že operace je ovladatelné.</span><span class="sxs-lookup"><span data-stu-id="a3a13-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="a3a13-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="a3a13-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="a3a13-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="a3a13-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a3a13-110">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="a3a13-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-ctl"></a><span data-ttu-id="a3a13-111">Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL</span><span class="sxs-lookup"><span data-stu-id="a3a13-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="a3a13-112">Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="a3a13-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a3a13-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a3a13-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3a13-114">'S</span><span class="sxs-lookup"><span data-stu-id="a3a13-114">'T</span></span>

<span data-ttu-id="a3a13-115">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="a3a13-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3a13-116">Viz také</span><span class="sxs-lookup"><span data-stu-id="a3a13-116">See Also</span></span>

- [<span data-ttu-id="a3a13-117">Microsoft. proCControlled. Canon.</span><span class="sxs-lookup"><span data-stu-id="a3a13-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)