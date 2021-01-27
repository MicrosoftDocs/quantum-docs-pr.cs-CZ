---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Uživatelem definovaný typ RequiresCapability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855157"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="15426-102">Uživatelem definovaný typ RequiresCapability</span><span class="sxs-lookup"><span data-stu-id="15426-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="15426-103">Obor názvů: [Microsoft. Protargeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="15426-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="15426-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="15426-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="15426-105">Atribut rozpoznaný kompilátorem, který slouží k označení možného možného spuštění s běhovými funkcemi, které vyžaduje.</span><span class="sxs-lookup"><span data-stu-id="15426-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="15426-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="15426-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="15426-107">Level: [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="15426-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="15426-108">Název úrovně běhové funkce, kterou vyžaduje možnost volat.</span><span class="sxs-lookup"><span data-stu-id="15426-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="15426-109">Důvod: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="15426-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="15426-110">Popis důvodu, proč vyžaduje tuto možnost spuštění.</span><span class="sxs-lookup"><span data-stu-id="15426-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="15426-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="15426-111">Remarks</span></span>

<span data-ttu-id="15426-112">Tento atribut je automaticky přidán pro volání kompilátorem, pokud instance tohoto atributu již na volání nelze navolat.</span><span class="sxs-lookup"><span data-stu-id="15426-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="15426-113">Neměl by být použit kromě výjimečných případů, kdy kompilátor neodvodí požadovanou funkci správně.</span><span class="sxs-lookup"><span data-stu-id="15426-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="15426-114">Níže je uveden seznam názvů úrovní schopností, v pořadí rostoucích možností nebo snížení omezení:</span><span class="sxs-lookup"><span data-stu-id="15426-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="15426-115">Výsledky měření nejde porovnávat s rovností.</span><span class="sxs-lookup"><span data-stu-id="15426-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="15426-116">Výsledky měření lze porovnat pouze s rovností v podmíněných výrazech if-Statement v operacích.</span><span class="sxs-lookup"><span data-stu-id="15426-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="15426-117">Blok if příkazu, který závisí na výsledku, nemůže obsahovat příkazy set pro proměnlivé proměnné deklarované mimo blok nebo příkazy Return.</span><span class="sxs-lookup"><span data-stu-id="15426-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="15426-118">Žádná běhová omezení.</span><span class="sxs-lookup"><span data-stu-id="15426-118">No runtime restrictions.</span></span> <span data-ttu-id="15426-119">Můžete spustit libovolný program Q #.</span><span class="sxs-lookup"><span data-stu-id="15426-119">Any Q# program can be executed.</span></span>