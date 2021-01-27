---
uid: Microsoft.Quantum.Logical.Conditioned
title: Podmíněně – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817286"
---
# <a name="conditioned-function"></a><span data-ttu-id="4f58e-102">Podmíněně – funkce</span><span class="sxs-lookup"><span data-stu-id="4f58e-102">Conditioned function</span></span>

<span data-ttu-id="4f58e-103">Obor názvů: [Microsoft.. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4f58e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4f58e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f58e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f58e-105">Vrátí jednu ze dvou hodnot v závislosti na hodnotě logické podmínky.</span><span class="sxs-lookup"><span data-stu-id="4f58e-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="4f58e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4f58e-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="4f58e-107">podmínka: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4f58e-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4f58e-108">Podmínka sloužící k řízení, který vstup je vrácen.</span><span class="sxs-lookup"><span data-stu-id="4f58e-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="4f58e-109">Hodnotu ifTrue: 'T</span><span class="sxs-lookup"><span data-stu-id="4f58e-109">ifTrue : 'T</span></span>

<span data-ttu-id="4f58e-110">Hodnota, která má být vrácena, pokud `condition` je `true` .</span><span class="sxs-lookup"><span data-stu-id="4f58e-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="4f58e-111">Hodnotu IfFalse: 'T</span><span class="sxs-lookup"><span data-stu-id="4f58e-111">ifFalse : 'T</span></span>

<span data-ttu-id="4f58e-112">Hodnota, která má být vrácena, pokud `condition` je `false` .</span><span class="sxs-lookup"><span data-stu-id="4f58e-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="4f58e-113">Výstup: 'T</span><span class="sxs-lookup"><span data-stu-id="4f58e-113">Output : 'T</span></span>

<span data-ttu-id="4f58e-114">`ifTrue` Pokud `condition` je `true` , a `ifFalse` jinak.</span><span class="sxs-lookup"><span data-stu-id="4f58e-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4f58e-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4f58e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4f58e-116">'S</span><span class="sxs-lookup"><span data-stu-id="4f58e-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="4f58e-117">Poznámky</span><span class="sxs-lookup"><span data-stu-id="4f58e-117">Remarks</span></span>

<span data-ttu-id="4f58e-118">Na rozdíl od `?|` operátoru Tato funkce nemá krátký okruh, takže oba vstupy jsou plně vyhodnoceny.</span><span class="sxs-lookup"><span data-stu-id="4f58e-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="4f58e-119">V případě chování až po krátkého okruhu jsou následující ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="4f58e-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```