---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201763"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="34e0f-102">EqualityFactR – funkce</span><span class="sxs-lookup"><span data-stu-id="34e0f-102">EqualityFactR function</span></span>

<span data-ttu-id="34e0f-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="34e0f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="34e0f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34e0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34e0f-105">Vyhodnotí, že klasická proměnná výsledku má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="34e0f-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="34e0f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="34e0f-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="34e0f-107">skutečnost: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="34e0f-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="34e0f-108">Proměnná, která se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="34e0f-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="34e0f-109">očekáváno __: <Result> neplatné__</span><span class="sxs-lookup"><span data-stu-id="34e0f-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="34e0f-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="34e0f-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="34e0f-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="34e0f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="34e0f-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="34e0f-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="34e0f-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34e0f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

