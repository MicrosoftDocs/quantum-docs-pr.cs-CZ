---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698093"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="cb14d-102">EqualityFactCP – funkce</span><span class="sxs-lookup"><span data-stu-id="cb14d-102">EqualityFactCP function</span></span>

<span data-ttu-id="cb14d-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cb14d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cb14d-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb14d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb14d-105">Vyhodnotí, že komplexní číslo má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="cb14d-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cb14d-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cb14d-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="cb14d-107">skutečnost: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="cb14d-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="cb14d-108">Hodnota, která má být kontrolována.</span><span class="sxs-lookup"><span data-stu-id="cb14d-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="cb14d-109">očekáváno: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="cb14d-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="cb14d-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="cb14d-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="cb14d-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cb14d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cb14d-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="cb14d-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb14d-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb14d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

