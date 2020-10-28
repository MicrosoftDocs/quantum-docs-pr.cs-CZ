---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698085"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="aaaaf-102">EqualityFactR – funkce</span><span class="sxs-lookup"><span data-stu-id="aaaaf-102">EqualityFactR function</span></span>

<span data-ttu-id="aaaaf-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="aaaaf-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="aaaaf-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aaaaf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aaaaf-105">Vyhodnotí, že klasická proměnná výsledku má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="aaaaf-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="aaaaf-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="aaaaf-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="aaaaf-107">skutečnost: __neplatné <Result>__</span><span class="sxs-lookup"><span data-stu-id="aaaaf-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="aaaaf-108">Proměnná, která se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="aaaaf-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="aaaaf-109">očekáváno __: <Result> neplatné__</span><span class="sxs-lookup"><span data-stu-id="aaaaf-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="aaaaf-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="aaaaf-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="aaaaf-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="aaaaf-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="aaaaf-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="aaaaf-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aaaaf-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aaaaf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

