---
uid: Microsoft.Quantum.Logical.Conditioned
title: Podmíněně – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707056"
---
# <a name="conditioned-function"></a><span data-ttu-id="2d430-102">Podmíněně – funkce</span><span class="sxs-lookup"><span data-stu-id="2d430-102">Conditioned function</span></span>

<span data-ttu-id="2d430-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2d430-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2d430-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2d430-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2d430-105">Vrátí jednu ze dvou hodnot v závislosti na hodnotě logické podmínky.</span><span class="sxs-lookup"><span data-stu-id="2d430-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="2d430-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2d430-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="2d430-107">podmínka: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2d430-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2d430-108">Podmínka sloužící k řízení, který vstup je vrácen.</span><span class="sxs-lookup"><span data-stu-id="2d430-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="2d430-109">Hodnotu ifTrue: 'T</span><span class="sxs-lookup"><span data-stu-id="2d430-109">ifTrue : 'T</span></span>

<span data-ttu-id="2d430-110">Hodnota, která má být vrácena, pokud `condition` je `true` .</span><span class="sxs-lookup"><span data-stu-id="2d430-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="2d430-111">Hodnotu IfFalse: 'T</span><span class="sxs-lookup"><span data-stu-id="2d430-111">ifFalse : 'T</span></span>

<span data-ttu-id="2d430-112">Hodnota, která má být vrácena, pokud `condition` je `false` .</span><span class="sxs-lookup"><span data-stu-id="2d430-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="2d430-113">Výstup: 'T</span><span class="sxs-lookup"><span data-stu-id="2d430-113">Output : 'T</span></span>

<span data-ttu-id="2d430-114">`ifTrue` Pokud `condition` je `true` , a `ifFalse` jinak.</span><span class="sxs-lookup"><span data-stu-id="2d430-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2d430-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2d430-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2d430-116">'S</span><span class="sxs-lookup"><span data-stu-id="2d430-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2d430-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2d430-117">Remarks</span></span>

<span data-ttu-id="2d430-118">Na rozdíl od `?|` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.</span><span class="sxs-lookup"><span data-stu-id="2d430-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="2d430-119">V případě chování až po krátkého okruhu jsou následující ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="2d430-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```