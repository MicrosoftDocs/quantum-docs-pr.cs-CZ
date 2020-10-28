---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704312"
---
# <a name="controlledonint-function"></a><span data-ttu-id="28b6a-102">ControlledOnInt – funkce</span><span class="sxs-lookup"><span data-stu-id="28b6a-102">ControlledOnInt function</span></span>

<span data-ttu-id="28b6a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28b6a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28b6a-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28b6a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28b6a-105">Vrátí operátor s jednotkou, který používá Oracle v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadanému kladnému celému číslu.</span><span class="sxs-lookup"><span data-stu-id="28b6a-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="28b6a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="28b6a-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="28b6a-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28b6a-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28b6a-108">Kladné celé číslo.</span><span class="sxs-lookup"><span data-stu-id="28b6a-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="28b6a-109">Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="28b6a-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="28b6a-110">Operátor s jednotkou.</span><span class="sxs-lookup"><span data-stu-id="28b6a-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="28b6a-111">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="28b6a-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="28b6a-112">Jednotkový operátor, který je použit `oracle` v cílovém registru, pokud stav registru ovládacího prvku odpovídá stavu číslo `numberState` .</span><span class="sxs-lookup"><span data-stu-id="28b6a-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="28b6a-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="28b6a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28b6a-114">'S</span><span class="sxs-lookup"><span data-stu-id="28b6a-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="28b6a-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="28b6a-115">Remarks</span></span>

<span data-ttu-id="28b6a-116">Hodnota `numberState` je interpretována pomocí kódování ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="28b6a-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>