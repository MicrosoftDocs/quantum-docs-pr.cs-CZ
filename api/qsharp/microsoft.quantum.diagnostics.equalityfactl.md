---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201797"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="cf909-102">EqualityFactL – funkce</span><span class="sxs-lookup"><span data-stu-id="cf909-102">EqualityFactL function</span></span>

<span data-ttu-id="cf909-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cf909-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cf909-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cf909-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cf909-105">Vyhodnotí, že klasická hodnota typu BigInt má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="cf909-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cf909-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="cf909-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="cf909-107">skutečnost: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cf909-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cf909-108">Číslo, které má být zkontrolováno.</span><span class="sxs-lookup"><span data-stu-id="cf909-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="cf909-109">očekáváno: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cf909-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cf909-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="cf909-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="cf909-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cf909-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cf909-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="cf909-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf909-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf909-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

