---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: Operace ApplyToRestCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: e64eeaae2151a28c289e3e71e47f897d6c378b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841245"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="59f89-102">Operace ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="59f89-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="59f89-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59f89-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59f89-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59f89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59f89-105">Aplikuje operaci na všechny, ale na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="59f89-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="59f89-106">Popis</span><span class="sxs-lookup"><span data-stu-id="59f89-106">Description</span></span>

<span data-ttu-id="59f89-107">Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="59f89-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="59f89-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="59f89-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="59f89-109">op: t [] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="59f89-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="59f89-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="59f89-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="59f89-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="59f89-111">targets : 'T[]</span></span>

<span data-ttu-id="59f89-112">Pole cílů, z nichž všechny kromě prvního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="59f89-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59f89-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59f89-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="59f89-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="59f89-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59f89-115">'S</span><span class="sxs-lookup"><span data-stu-id="59f89-115">'T</span></span>

<span data-ttu-id="59f89-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="59f89-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="59f89-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="59f89-117">See Also</span></span>

- [<span data-ttu-id="59f89-118">Microsoft. proApplyToRest. Canon.</span><span class="sxs-lookup"><span data-stu-id="59f89-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="59f89-119">Microsoft. proApplyToRestA. Canon.</span><span class="sxs-lookup"><span data-stu-id="59f89-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="59f89-120">Microsoft. proApplyToRestC. Canon.</span><span class="sxs-lookup"><span data-stu-id="59f89-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)