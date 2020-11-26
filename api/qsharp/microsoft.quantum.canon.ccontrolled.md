---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: 76e663e9a4b53c7ed74a1b70da516fb07958923b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216892"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="f50fb-102">CControlled – funkce</span><span class="sxs-lookup"><span data-stu-id="f50fb-102">CControlled function</span></span>

<span data-ttu-id="f50fb-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f50fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f50fb-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f50fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f50fb-105">V případě operace op vrátí novou operaci, která použije hodnotu op, pokud je klasický řídicí bit true.</span><span class="sxs-lookup"><span data-stu-id="f50fb-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="f50fb-106">Pokud k `false` tomu nedojde, nic se nestane.</span><span class="sxs-lookup"><span data-stu-id="f50fb-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="f50fb-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="f50fb-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="f50fb-108">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f50fb-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f50fb-109">Operace, která se má podmíněně použít</span><span class="sxs-lookup"><span data-stu-id="f50fb-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="f50fb-110">Výstup: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f50fb-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="f50fb-111">Nová operace, která je op, pokud má klasický řídicí bit hodnotu true.</span><span class="sxs-lookup"><span data-stu-id="f50fb-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f50fb-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f50fb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f50fb-113">'S</span><span class="sxs-lookup"><span data-stu-id="f50fb-113">'T</span></span>

<span data-ttu-id="f50fb-114">Vstupní typ operace, která se má podmíněně použít.</span><span class="sxs-lookup"><span data-stu-id="f50fb-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f50fb-115">Viz také</span><span class="sxs-lookup"><span data-stu-id="f50fb-115">See Also</span></span>

- [<span data-ttu-id="f50fb-116">Microsoft. proCControlledC. Canon.</span><span class="sxs-lookup"><span data-stu-id="f50fb-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="f50fb-117">Microsoft. proCControlledA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f50fb-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="f50fb-118">Microsoft. proCControlledCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="f50fb-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)