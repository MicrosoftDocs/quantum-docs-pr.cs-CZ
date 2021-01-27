---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829176"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="1f710-102">EqualityFactCP – funkce</span><span class="sxs-lookup"><span data-stu-id="1f710-102">EqualityFactCP function</span></span>

<span data-ttu-id="1f710-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1f710-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1f710-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f710-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f710-105">Vyhodnotí, že komplexní číslo má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="1f710-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1f710-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="1f710-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="1f710-107">skutečnost: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1f710-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1f710-108">Hodnota, která má být kontrolována.</span><span class="sxs-lookup"><span data-stu-id="1f710-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="1f710-109">očekáváno: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="1f710-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="1f710-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="1f710-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="1f710-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1f710-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1f710-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="1f710-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f710-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f710-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

