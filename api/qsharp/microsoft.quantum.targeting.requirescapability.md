---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Uživatelem definovaný typ RequiresCapability
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231003"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="32ee8-102">Uživatelem definovaný typ RequiresCapability</span><span class="sxs-lookup"><span data-stu-id="32ee8-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="32ee8-103">Obor názvů: [Microsoft. Protargeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="32ee8-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="32ee8-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="32ee8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="32ee8-105">Atribut rozpoznaný kompilátorem, který slouží k označení možného možného spuštění s běhovými funkcemi, které vyžaduje.</span><span class="sxs-lookup"><span data-stu-id="32ee8-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="32ee8-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="32ee8-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="32ee8-107">Level: [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="32ee8-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="32ee8-108">Název úrovně běhové funkce, kterou vyžaduje možnost volat.</span><span class="sxs-lookup"><span data-stu-id="32ee8-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="32ee8-109">Důvod: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="32ee8-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="32ee8-110">Popis důvodu, proč vyžaduje tuto možnost spuštění.</span><span class="sxs-lookup"><span data-stu-id="32ee8-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="32ee8-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="32ee8-111">Remarks</span></span>

<span data-ttu-id="32ee8-112">Tento atribut je automaticky přidán pro volání kompilátorem, pokud instance tohoto atributu již na volání nelze navolat.</span><span class="sxs-lookup"><span data-stu-id="32ee8-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="32ee8-113">Neměl by být použit kromě výjimečných případů, kdy kompilátor neodvodí požadovanou funkci správně.</span><span class="sxs-lookup"><span data-stu-id="32ee8-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="32ee8-114">Níže je uveden seznam názvů úrovní schopností, v pořadí rostoucích možností nebo snížení omezení:</span><span class="sxs-lookup"><span data-stu-id="32ee8-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="32ee8-115">Výsledky měření nejde porovnávat s rovností.</span><span class="sxs-lookup"><span data-stu-id="32ee8-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="32ee8-116">Výsledky měření lze porovnat pouze s rovností v podmíněných výrazech if-Statement v operacích.</span><span class="sxs-lookup"><span data-stu-id="32ee8-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="32ee8-117">Blok if příkazu, který závisí na výsledku, nemůže obsahovat příkazy set pro proměnlivé proměnné deklarované mimo blok nebo příkazy Return.</span><span class="sxs-lookup"><span data-stu-id="32ee8-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="32ee8-118">Žádná běhová omezení.</span><span class="sxs-lookup"><span data-stu-id="32ee8-118">No runtime restrictions.</span></span> <span data-ttu-id="32ee8-119">Můžete spustit libovolný program Q #.</span><span class="sxs-lookup"><span data-stu-id="32ee8-119">Any Q# program can be executed.</span></span>