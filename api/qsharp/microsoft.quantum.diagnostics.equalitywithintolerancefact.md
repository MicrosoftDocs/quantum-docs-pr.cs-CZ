---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698088"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="3fd48-102">EqualityWithinToleranceFact – funkce</span><span class="sxs-lookup"><span data-stu-id="3fd48-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="3fd48-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3fd48-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3fd48-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3fd48-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3fd48-105">Představuje deklaraci identity, že klasická hodnota s plovoucí desetinnou čárkou má očekávanou hodnotu až do dané absolutní tolerance.</span><span class="sxs-lookup"><span data-stu-id="3fd48-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="3fd48-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3fd48-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="3fd48-107">skutečnost: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3fd48-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3fd48-108">Číslo, které má být zkontrolováno.</span><span class="sxs-lookup"><span data-stu-id="3fd48-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="3fd48-109">očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3fd48-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3fd48-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="3fd48-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="3fd48-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3fd48-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3fd48-112">Absolutní tolerance rozdílu mezi skutečnými a očekávanými hodnotami.</span><span class="sxs-lookup"><span data-stu-id="3fd48-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3fd48-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3fd48-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

