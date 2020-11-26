---
uid: Microsoft.Quantum.Logical.Conditioned
title: Podmíněně – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198482"
---
# <a name="conditioned-function"></a><span data-ttu-id="a901b-102">Podmíněně – funkce</span><span class="sxs-lookup"><span data-stu-id="a901b-102">Conditioned function</span></span>

<span data-ttu-id="a901b-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a901b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a901b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a901b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a901b-105">Vrátí jednu ze dvou hodnot v závislosti na hodnotě logické podmínky.</span><span class="sxs-lookup"><span data-stu-id="a901b-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="a901b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="a901b-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="a901b-107">podmínka: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a901b-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a901b-108">Podmínka sloužící k řízení, který vstup je vrácen.</span><span class="sxs-lookup"><span data-stu-id="a901b-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="a901b-109">Hodnotu ifTrue: 'T</span><span class="sxs-lookup"><span data-stu-id="a901b-109">ifTrue : 'T</span></span>

<span data-ttu-id="a901b-110">Hodnota, která má být vrácena, pokud `condition` je `true` .</span><span class="sxs-lookup"><span data-stu-id="a901b-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="a901b-111">Hodnotu IfFalse: 'T</span><span class="sxs-lookup"><span data-stu-id="a901b-111">ifFalse : 'T</span></span>

<span data-ttu-id="a901b-112">Hodnota, která má být vrácena, pokud `condition` je `false` .</span><span class="sxs-lookup"><span data-stu-id="a901b-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="a901b-113">Výstup: 'T</span><span class="sxs-lookup"><span data-stu-id="a901b-113">Output : 'T</span></span>

<span data-ttu-id="a901b-114">`ifTrue` Pokud `condition` je `true` , a `ifFalse` jinak.</span><span class="sxs-lookup"><span data-stu-id="a901b-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a901b-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a901b-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a901b-116">'S</span><span class="sxs-lookup"><span data-stu-id="a901b-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="a901b-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="a901b-117">Remarks</span></span>

<span data-ttu-id="a901b-118">Na rozdíl od `?|` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.</span><span class="sxs-lookup"><span data-stu-id="a901b-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="a901b-119">V případě chování až po krátkého okruhu jsou následující ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="a901b-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```