---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Operace ApplyControlledOnInt
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3dd17e6bc913e84941a6b81f134e60536a4c4122
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219001"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="37e1a-102">Operace ApplyControlledOnInt</span><span class="sxs-lookup"><span data-stu-id="37e1a-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="37e1a-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="37e1a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="37e1a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37e1a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37e1a-105">Aplikuje jednotnou operaci v cílovém registru, pokud stav registru ovládacího prvku odpovídá zadanému kladnému celému číslu.</span><span class="sxs-lookup"><span data-stu-id="37e1a-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="37e1a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="37e1a-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="37e1a-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="37e1a-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="37e1a-108">Nezáporné celé číslo, na kterém `oracle` by měla být operace řízena.</span><span class="sxs-lookup"><span data-stu-id="37e1a-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="37e1a-109">Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="37e1a-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="37e1a-110">Jednotná operace, která se má řídit.</span><span class="sxs-lookup"><span data-stu-id="37e1a-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="37e1a-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="37e1a-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="37e1a-112">Každé z nich registruje registraci řízení aplikací `oracle` .</span><span class="sxs-lookup"><span data-stu-id="37e1a-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="37e1a-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="37e1a-113">targetRegister : 'T</span></span>

<span data-ttu-id="37e1a-114">Registrace, na které se má použít `oracle` .</span><span class="sxs-lookup"><span data-stu-id="37e1a-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37e1a-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37e1a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="37e1a-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="37e1a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37e1a-117">'S</span><span class="sxs-lookup"><span data-stu-id="37e1a-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="37e1a-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="37e1a-118">Remarks</span></span>

<span data-ttu-id="37e1a-119">Hodnota `numberState` je interpretována pomocí kódování ve formátu Little endian.</span><span class="sxs-lookup"><span data-stu-id="37e1a-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="37e1a-120">`numberState` musí být maximálně $2 ^ \texttt{Length (controlRegister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="37e1a-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="37e1a-121">Například `numberState = 537` to znamená, že `oracle` se použije pouze v případě, že `controlRegister` je ve stavu $ \ket {537} $.</span><span class="sxs-lookup"><span data-stu-id="37e1a-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>