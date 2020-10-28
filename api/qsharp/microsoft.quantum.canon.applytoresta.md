---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: Operace ApplyToRestA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 99a18e835115491cc3451a4e3b44a6ff70e9dc6c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704689"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="47ac5-102">Operace ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="47ac5-102">ApplyToRestA operation</span></span>

<span data-ttu-id="47ac5-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="47ac5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="47ac5-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="47ac5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="47ac5-105">Aplikuje operaci na všechny, ale na první prvek pole.</span><span class="sxs-lookup"><span data-stu-id="47ac5-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="47ac5-106">Popis</span><span class="sxs-lookup"><span data-stu-id="47ac5-106">Description</span></span>

<span data-ttu-id="47ac5-107">Daná operace `op` a pole cílů `targets` platí `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="47ac5-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="47ac5-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="47ac5-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="47ac5-109">op: t [] => ADJ. [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47ac5-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="47ac5-110">Operace, která se má použít.</span><span class="sxs-lookup"><span data-stu-id="47ac5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="47ac5-111">cíle: t []</span><span class="sxs-lookup"><span data-stu-id="47ac5-111">targets : 'T[]</span></span>

<span data-ttu-id="47ac5-112">Pole cílů, z nichž všechny kromě prvního budou aplikovány na `op` .</span><span class="sxs-lookup"><span data-stu-id="47ac5-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47ac5-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47ac5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="47ac5-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="47ac5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="47ac5-115">'S</span><span class="sxs-lookup"><span data-stu-id="47ac5-115">'T</span></span>

<span data-ttu-id="47ac5-116">Vstupní typ operace, která má být použita.</span><span class="sxs-lookup"><span data-stu-id="47ac5-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="47ac5-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="47ac5-117">See Also</span></span>

- [<span data-ttu-id="47ac5-118">Microsoft. proApplyToRest. Canon.</span><span class="sxs-lookup"><span data-stu-id="47ac5-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="47ac5-119">Microsoft. proApplyToRestC. Canon.</span><span class="sxs-lookup"><span data-stu-id="47ac5-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="47ac5-120">Microsoft. proApplyToRestCA. Canon.</span><span class="sxs-lookup"><span data-stu-id="47ac5-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)