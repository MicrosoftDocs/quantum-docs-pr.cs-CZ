---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853337"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="6b28e-102">EqualityFactR – funkce</span><span class="sxs-lookup"><span data-stu-id="6b28e-102">EqualityFactR function</span></span>

<span data-ttu-id="6b28e-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6b28e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6b28e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b28e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b28e-105">Vyhodnotí, že klasická proměnná výsledku má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="6b28e-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6b28e-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="6b28e-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="6b28e-107">skutečnost: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="6b28e-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="6b28e-108">Proměnná, která se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="6b28e-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="6b28e-109">očekáváno __: <Result> neplatné__</span><span class="sxs-lookup"><span data-stu-id="6b28e-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="6b28e-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="6b28e-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="6b28e-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6b28e-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6b28e-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="6b28e-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b28e-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b28e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

