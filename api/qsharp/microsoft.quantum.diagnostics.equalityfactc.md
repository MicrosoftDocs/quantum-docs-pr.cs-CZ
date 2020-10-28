---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698097"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="2867c-102">EqualityFactC – funkce</span><span class="sxs-lookup"><span data-stu-id="2867c-102">EqualityFactC function</span></span>

<span data-ttu-id="2867c-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2867c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2867c-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2867c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2867c-105">Vyhodnotí, že komplexní číslo má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="2867c-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2867c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2867c-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="2867c-107">skutečnost: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="2867c-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="2867c-108">Hodnota, která má být kontrolována.</span><span class="sxs-lookup"><span data-stu-id="2867c-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="2867c-109">očekáváno: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="2867c-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="2867c-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="2867c-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2867c-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2867c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2867c-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="2867c-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2867c-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2867c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

