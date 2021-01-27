---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 6c7f46c44f2a2427f702e463195f26660cb4fca1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840789"
---
# <a name="controlledonint-function"></a><span data-ttu-id="75f27-102">ControlledOnInt – funkce</span><span class="sxs-lookup"><span data-stu-id="75f27-102">ControlledOnInt function</span></span>

<span data-ttu-id="75f27-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="75f27-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="75f27-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75f27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75f27-105">Vrátí operátor s jednotkou, který používá Oracle v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadanému kladnému celému číslu.</span><span class="sxs-lookup"><span data-stu-id="75f27-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="75f27-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="75f27-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="75f27-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="75f27-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="75f27-108">Kladné celé číslo.</span><span class="sxs-lookup"><span data-stu-id="75f27-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="75f27-109">Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="75f27-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="75f27-110">Operátor s jednotkou.</span><span class="sxs-lookup"><span data-stu-id="75f27-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="75f27-111">Výstup: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="75f27-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="75f27-112">Jednotkový operátor, který je použit `oracle` v cílovém registru, pokud stav registru ovládacího prvku odpovídá stavu číslo `numberState` .</span><span class="sxs-lookup"><span data-stu-id="75f27-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="75f27-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="75f27-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="75f27-114">'S</span><span class="sxs-lookup"><span data-stu-id="75f27-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="75f27-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="75f27-115">Remarks</span></span>

<span data-ttu-id="75f27-116">Hodnota `numberState` je interpretována pomocí kódování ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="75f27-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>