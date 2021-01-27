---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846177"
---
# <a name="emptyarray-function"></a><span data-ttu-id="53952-102">EmptyArray – funkce</span><span class="sxs-lookup"><span data-stu-id="53952-102">EmptyArray function</span></span>

<span data-ttu-id="53952-103">Obor názvů: [Microsoft. Forms. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="53952-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="53952-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="53952-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="53952-105">Vrátí prázdné pole daného typu.</span><span class="sxs-lookup"><span data-stu-id="53952-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="53952-106">Výstup: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="53952-106">Output : 'TElement[]</span></span>

<span data-ttu-id="53952-107">Prázdné pole</span><span class="sxs-lookup"><span data-stu-id="53952-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="53952-108">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="53952-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="53952-109">'TElement</span><span class="sxs-lookup"><span data-stu-id="53952-109">'TElement</span></span>

<span data-ttu-id="53952-110">Typ prvků pole.</span><span class="sxs-lookup"><span data-stu-id="53952-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="53952-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="53952-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```