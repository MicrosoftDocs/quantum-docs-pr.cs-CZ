---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: e33d25899580a127171fb45a92d77cfdb5003a21
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201899"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="8916b-102">EqualityFactC – funkce</span><span class="sxs-lookup"><span data-stu-id="8916b-102">EqualityFactC function</span></span>

<span data-ttu-id="8916b-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8916b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8916b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8916b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8916b-105">Vyhodnotí, že komplexní číslo má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="8916b-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="8916b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="8916b-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="8916b-107">skutečnost: [komplexní](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="8916b-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="8916b-108">Hodnota, která má být kontrolována.</span><span class="sxs-lookup"><span data-stu-id="8916b-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="8916b-109">očekáváno: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="8916b-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="8916b-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="8916b-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="8916b-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="8916b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="8916b-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="8916b-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8916b-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8916b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

