---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: Operace ApplyToTail
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 72b55ec7161d5f6af5e4cb512c648078516c3b4e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704633"
---
# <a name="applytotail-operation"></a><span data-ttu-id="9c87a-102">Operace ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="9c87a-102">ApplyToTail operation</span></span>

<span data-ttu-id="9c87a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c87a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c87a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c87a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c87a-105">Použije operaci na poslední prvek pole.</span><span class="sxs-lookup"><span data-stu-id="9c87a-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9c87a-106">Popis</span><span class="sxs-lookup"><span data-stu-id="9c87a-106">Description</span></span>

<span data-ttu-id="9c87a-107">Daná operace `op` a pole cílů `targets` platí `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="9c87a-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="9c87a-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="9c87a-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="9c87a-109">op: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c87a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9c87a-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="9c87a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9c87a-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="9c87a-111">targets : 'T[]</span></span>

<span data-ttu-id="9c87a-112">Pole cílů, z nichž poslední bude použito `op` .</span><span class="sxs-lookup"><span data-stu-id="9c87a-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c87a-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c87a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9c87a-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9c87a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9c87a-115">'S</span><span class="sxs-lookup"><span data-stu-id="9c87a-115">'T</span></span>

<span data-ttu-id="9c87a-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="9c87a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c87a-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="9c87a-117">See Also</span></span>

- [<span data-ttu-id="9c87a-118">Microsoft. proApplyToTailA. Canon.</span><span class="sxs-lookup"><span data-stu-id="9c87a-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="9c87a-119">Microsoft. proApplyToTailC. Canon.</span><span class="sxs-lookup"><span data-stu-id="9c87a-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="9c87a-120">Microsoft. proApplyToTailCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="9c87a-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)