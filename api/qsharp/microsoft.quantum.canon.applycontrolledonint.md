---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operace ApplyControlledOnInt
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705432"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="27a9f-102">Operace ApplyControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="27a9f-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="27a9f-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27a9f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27a9f-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27a9f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27a9f-105">Aplikuje jednotnou operaci v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadanému kladnému celému číslu.</span><span class="sxs-lookup"><span data-stu-id="27a9f-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="27a9f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="27a9f-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="27a9f-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27a9f-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27a9f-108">Nezáporné celé číslo, na kterém `oracle` by měla být operace řízena.</span><span class="sxs-lookup"><span data-stu-id="27a9f-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="27a9f-109">Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="27a9f-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="27a9f-110">Jednotná operace, která se má řídit.</span><span class="sxs-lookup"><span data-stu-id="27a9f-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="27a9f-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="27a9f-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="27a9f-112">Každé z nich registruje registraci řízení aplikací `oracle` .</span><span class="sxs-lookup"><span data-stu-id="27a9f-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="27a9f-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="27a9f-113">targetRegister : 'T</span></span>

<span data-ttu-id="27a9f-114">Registrace, na které se má použít `oracle` .</span><span class="sxs-lookup"><span data-stu-id="27a9f-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27a9f-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27a9f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="27a9f-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="27a9f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27a9f-117">'S</span><span class="sxs-lookup"><span data-stu-id="27a9f-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="27a9f-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="27a9f-118">Remarks</span></span>

<span data-ttu-id="27a9f-119">Hodnota `numberState` je interpretována pomocí kódování ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="27a9f-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="27a9f-120">`numberState` musí být maximálně $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="27a9f-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="27a9f-121">Například `numberState = 537` to znamená, že `oracle` se použije pouze v případě, že `controlRegister` je ve stavu $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="27a9f-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>