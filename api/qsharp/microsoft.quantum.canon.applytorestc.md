---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: Operace ApplyToRestC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850495"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="66e87-102">Operace ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="66e87-102">ApplyToRestC operation</span></span>

<span data-ttu-id="66e87-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="66e87-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="66e87-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66e87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66e87-105">Aplikuje operaci na všechny, ale na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="66e87-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="66e87-106">Popis</span><span class="sxs-lookup"><span data-stu-id="66e87-106">Description</span></span>

<span data-ttu-id="66e87-107">Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="66e87-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="66e87-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="66e87-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="66e87-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je seznam CTL.</span><span class="sxs-lookup"><span data-stu-id="66e87-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="66e87-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="66e87-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="66e87-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="66e87-111">targets : 'T[]</span></span>

<span data-ttu-id="66e87-112">Pole cílů, z nichž všechny kromě prvního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="66e87-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="66e87-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="66e87-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="66e87-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="66e87-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="66e87-115">'S</span><span class="sxs-lookup"><span data-stu-id="66e87-115">'T</span></span>

<span data-ttu-id="66e87-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="66e87-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="66e87-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="66e87-117">See Also</span></span>

- [<span data-ttu-id="66e87-118">Microsoft. proApplyToRest. Canon.</span><span class="sxs-lookup"><span data-stu-id="66e87-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="66e87-119">Microsoft. proApplyToRestA. Canon.</span><span class="sxs-lookup"><span data-stu-id="66e87-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="66e87-120">Microsoft. proApplyToRestCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="66e87-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)