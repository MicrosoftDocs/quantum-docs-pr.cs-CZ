---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operace ApplyToTail
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850438"
---
# <a name="applytotail-operation"></a><span data-ttu-id="5a36d-102">Operace ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="5a36d-102">ApplyToTail operation</span></span>

<span data-ttu-id="5a36d-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5a36d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5a36d-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a36d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a36d-105">Použije operaci na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="5a36d-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="5a36d-106">Popis</span><span class="sxs-lookup"><span data-stu-id="5a36d-106">Description</span></span>

<span data-ttu-id="5a36d-107">Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="5a36d-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="5a36d-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="5a36d-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="5a36d-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a36d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5a36d-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="5a36d-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="5a36d-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="5a36d-111">targets : 'T[]</span></span>

<span data-ttu-id="5a36d-112">Pole cílů, z nichž poslední bude použito `op` .</span><span class="sxs-lookup"><span data-stu-id="5a36d-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a36d-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a36d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5a36d-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5a36d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5a36d-115">'S</span><span class="sxs-lookup"><span data-stu-id="5a36d-115">'T</span></span>

<span data-ttu-id="5a36d-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="5a36d-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="5a36d-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="5a36d-117">Example</span></span>

<span data-ttu-id="5a36d-118">Následující fragmenty Q # jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="5a36d-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="5a36d-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="5a36d-119">See Also</span></span>

- [<span data-ttu-id="5a36d-120">Microsoft. proApplyToTailA. Canon.</span><span class="sxs-lookup"><span data-stu-id="5a36d-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="5a36d-121">Microsoft. proApplyToTailC. Canon.</span><span class="sxs-lookup"><span data-stu-id="5a36d-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="5a36d-122">Microsoft. proApplyToTailCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="5a36d-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)