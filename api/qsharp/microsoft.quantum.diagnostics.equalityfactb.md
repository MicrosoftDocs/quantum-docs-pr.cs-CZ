---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201916"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="81e52-102">EqualityFactB – funkce</span><span class="sxs-lookup"><span data-stu-id="81e52-102">EqualityFactB function</span></span>

<span data-ttu-id="81e52-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="81e52-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="81e52-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81e52-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81e52-105">Vyhodnotí, že klasická proměnná bool má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="81e52-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="81e52-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="81e52-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="81e52-107">skutečnost: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="81e52-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="81e52-108">Proměnná, která se má zkontrolovat</span><span class="sxs-lookup"><span data-stu-id="81e52-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="81e52-109">očekáváno: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="81e52-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="81e52-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="81e52-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="81e52-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="81e52-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="81e52-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="81e52-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81e52-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81e52-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

