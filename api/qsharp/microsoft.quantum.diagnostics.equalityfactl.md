---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698089"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="eb475-102">EqualityFactL – funkce</span><span class="sxs-lookup"><span data-stu-id="eb475-102">EqualityFactL function</span></span>

<span data-ttu-id="eb475-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="eb475-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="eb475-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb475-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb475-105">Vyhodnotí, že klasická hodnota typu BigInt má očekávanou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="eb475-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="eb475-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="eb475-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="eb475-107">skutečnost: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eb475-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eb475-108">Číslo, které má být zkontrolováno.</span><span class="sxs-lookup"><span data-stu-id="eb475-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="eb475-109">očekáváno: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="eb475-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="eb475-110">Očekávaná hodnota.</span><span class="sxs-lookup"><span data-stu-id="eb475-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="eb475-111">zpráva: [řetězec](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="eb475-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="eb475-112">Řetězec zprávy o selhání, který se má použít při aktivaci kontrolního výrazu.</span><span class="sxs-lookup"><span data-stu-id="eb475-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb475-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb475-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

