---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698060"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="50031-102">NearEqualityFactD – funkce</span><span class="sxs-lookup"><span data-stu-id="50031-102">NearEqualityFactD function</span></span>

<span data-ttu-id="50031-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="50031-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="50031-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50031-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50031-105">Vyhodnotí, že klasická hodnota s plovoucí desetinnou čárkou má očekávanou hodnotu až na malou toleranci 1E-10.</span><span class="sxs-lookup"><span data-stu-id="50031-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="50031-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="50031-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="50031-107">skutečnost: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50031-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50031-108">Číslo, které má být zkontrolováno.</span><span class="sxs-lookup"><span data-stu-id="50031-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="50031-109">očekáváno: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50031-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50031-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="50031-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50031-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50031-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="50031-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="50031-112">Remarks</span></span>

<span data-ttu-id="50031-113">To je ekvivalentní <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> s tolerancí pevně zakódované $10 ^ {-10} $.</span><span class="sxs-lookup"><span data-stu-id="50031-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>