---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Operace ApplyControlledOnBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841946"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="27211-102">Operace ApplyControlledOnBitString</span><span class="sxs-lookup"><span data-stu-id="27211-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="27211-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27211-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27211-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27211-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27211-105">Aplikuje v cílovém registru jednotnou operaci řízenou v určitém stavu určeném příslušnou bitovou maskou.</span><span class="sxs-lookup"><span data-stu-id="27211-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="27211-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="27211-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="27211-107">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="27211-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="27211-108">Bitový řetězec, na kterém se má řídit daná Jednotková operace.</span><span class="sxs-lookup"><span data-stu-id="27211-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="27211-109">Oracle: t => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="27211-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="27211-110">Jednotná operace, která se má použít v cílovém registru.</span><span class="sxs-lookup"><span data-stu-id="27211-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="27211-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="27211-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="27211-112">Každé z nich registruje registraci řízení aplikací `oracle` .</span><span class="sxs-lookup"><span data-stu-id="27211-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="27211-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="27211-113">targetRegister : 'T</span></span>

<span data-ttu-id="27211-114">Cílový registr, který má být předán `oracle` jako vstup.</span><span class="sxs-lookup"><span data-stu-id="27211-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27211-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27211-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="27211-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="27211-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27211-117">'S</span><span class="sxs-lookup"><span data-stu-id="27211-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="27211-118">Poznámky</span><span class="sxs-lookup"><span data-stu-id="27211-118">Remarks</span></span>

<span data-ttu-id="27211-119">Vzor zadaný pomocí `bits` může být kratší než `controlRegister` , v takovém případě je další qubits ovládacího prvku ignorováno (to znamená, že není kontrolováno na $ \ket {0} $ ani $ \ket {1} $).</span><span class="sxs-lookup"><span data-stu-id="27211-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="27211-120">Pokud `bits` je delší než `controlRegister` , je vyvolána chyba.</span><span class="sxs-lookup"><span data-stu-id="27211-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="27211-121">Například `bits = [0,1,0,0,1]` to znamená, že `oracle` se použije pouze v případě, že `controlRegister` je ve stavu $ \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="27211-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>