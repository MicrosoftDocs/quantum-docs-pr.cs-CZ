---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: 6ada2632974fddd6dd0fd8e4e6ab0866e4f29524
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201712"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="fd1c9-102">EqualityWithinToleranceFact – funkce</span><span class="sxs-lookup"><span data-stu-id="fd1c9-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="fd1c9-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fd1c9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fd1c9-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd1c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd1c9-105">Představuje deklaraci identity, že klasická hodnota s plovoucí desetinnou čárkou má očekávanou hodnotu až do dané absolutní tolerance.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="fd1c9-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="fd1c9-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="fd1c9-107">skutečnost: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fd1c9-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fd1c9-108">Číslo, které má být zkontrolováno.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="fd1c9-109">očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fd1c9-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fd1c9-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="fd1c9-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fd1c9-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fd1c9-112">Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.</span><span class="sxs-lookup"><span data-stu-id="fd1c9-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd1c9-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd1c9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

