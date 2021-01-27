---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: Operace ApplyToRest
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850513"
---
# <a name="applytorest-operation"></a><span data-ttu-id="dee4c-102">Operace ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="dee4c-102">ApplyToRest operation</span></span>

<span data-ttu-id="dee4c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dee4c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dee4c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dee4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dee4c-105">Aplikuje operaci na všechny, ale na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="dee4c-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="dee4c-106">Popis</span><span class="sxs-lookup"><span data-stu-id="dee4c-106">Description</span></span>

<span data-ttu-id="dee4c-107">Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="dee4c-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="dee4c-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="dee4c-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="dee4c-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dee4c-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="dee4c-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="dee4c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="dee4c-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="dee4c-111">targets : 'T[]</span></span>

<span data-ttu-id="dee4c-112">Pole cílů, z nichž všechny kromě prvního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="dee4c-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dee4c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dee4c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dee4c-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="dee4c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dee4c-115">'S</span><span class="sxs-lookup"><span data-stu-id="dee4c-115">'T</span></span>

<span data-ttu-id="dee4c-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="dee4c-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="dee4c-117">Příklad</span><span class="sxs-lookup"><span data-stu-id="dee4c-117">Example</span></span>

<span data-ttu-id="dee4c-118">Následující fragmenty Q # jsou ekvivalentní:</span><span class="sxs-lookup"><span data-stu-id="dee4c-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="dee4c-119">Viz také</span><span class="sxs-lookup"><span data-stu-id="dee4c-119">See Also</span></span>

- [<span data-ttu-id="dee4c-120">Microsoft. proApplyToRestA. Canon.</span><span class="sxs-lookup"><span data-stu-id="dee4c-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="dee4c-121">Microsoft. proApplyToRestC. Canon.</span><span class="sxs-lookup"><span data-stu-id="dee4c-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="dee4c-122">Microsoft. proApplyToRestCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="dee4c-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)