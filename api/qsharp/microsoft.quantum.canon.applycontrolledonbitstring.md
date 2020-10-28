---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operace ApplyControlledOnBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705433"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="7c760-102">Operace ApplyControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="7c760-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="7c760-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c760-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c760-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c760-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c760-105">Aplikuje v cílovém registru jednotnou operaci řízenou v určitém stavu určeném příslušnou bitovou maskou.</span><span class="sxs-lookup"><span data-stu-id="7c760-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="7c760-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="7c760-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="7c760-107">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="7c760-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="7c760-108">Bitový řetězec, na kterém se má řídit daná Jednotková operace.</span><span class="sxs-lookup"><span data-stu-id="7c760-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="7c760-109">Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="7c760-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="7c760-110">Jednotná operace, která se má použít v cílovém registru.</span><span class="sxs-lookup"><span data-stu-id="7c760-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="7c760-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7c760-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7c760-112">Každé z nich registruje registraci řízení aplikací `oracle` .</span><span class="sxs-lookup"><span data-stu-id="7c760-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="7c760-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="7c760-113">targetRegister : 'T</span></span>

<span data-ttu-id="7c760-114">Cílový registr, který má být předán `oracle` jako vstup.</span><span class="sxs-lookup"><span data-stu-id="7c760-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7c760-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c760-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7c760-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7c760-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c760-117">'S</span><span class="sxs-lookup"><span data-stu-id="7c760-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="7c760-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="7c760-118">Remarks</span></span>

<span data-ttu-id="7c760-119">Vzor zadaný pomocí `bits` může být kratší než `controlRegister` , v takovém případě je další qubits ovládacího prvku ignorováno (to znamená, že není kontrolováno na $ \ket {0} $ ani $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="7c760-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="7c760-120">Pokud `bits` je delší než `controlRegister` , je vyvolána chyba.</span><span class="sxs-lookup"><span data-stu-id="7c760-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="7c760-121">Například `bits = [0,1,0,0,1]` to znamená, že `oracle` se použije pouze v případě, že `controlRegister` je ve stavu $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="7c760-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>