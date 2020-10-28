---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: a8b4c65f8c32f7f9185f1dbdacf8fc75fd4573b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707822"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="25a26-102">BlockEncodingToReflection – funkce</span><span class="sxs-lookup"><span data-stu-id="25a26-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="25a26-103">Obor názvů: [Microsoft.. simulace](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="25a26-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="25a26-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25a26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25a26-105">Převede na `BlockEncoding` ekvivalentní `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="25a26-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="25a26-106">To znamená, že s ohledem na `BlockEncoding` jednotkové $U $, který kóduje nějaký operátor $H $ Interest, převede ho na `BlockEncodingReflection` $U $, který kóduje stejný operátor, ale také splňuje $U ' ^ \Dagger = U ' $.</span><span class="sxs-lookup"><span data-stu-id="25a26-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="25a26-107">Tím se zvýší velikost pomocného registru $U $ o jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="25a26-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="25a26-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="25a26-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="25a26-109">blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="25a26-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="25a26-110">`BlockEncoding`Jednotková $U $, která má být převedena na reflexi.</span><span class="sxs-lookup"><span data-stu-id="25a26-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="25a26-111">Výstup: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="25a26-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="25a26-112">Jednotková $U ' $ jednají společně na registrech `a` a `s` blokující kódování $H $ a splňuje $U ' ^ \Dagger = U ' $.</span><span class="sxs-lookup"><span data-stu-id="25a26-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="25a26-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="25a26-113">Remarks</span></span>

<span data-ttu-id="25a26-114">Tím se zvýší velikost pomocného registru $U $ o jeden qubit.</span><span class="sxs-lookup"><span data-stu-id="25a26-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="25a26-115">Odkazy</span><span class="sxs-lookup"><span data-stu-id="25a26-115">References</span></span>

- <span data-ttu-id="25a26-116">Simulace Hamiltonian podle Qubitization Guang vystoupí hao nízká, Petr L. Čuangština https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="25a26-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="25a26-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="25a26-117">See Also</span></span>

- [<span data-ttu-id="25a26-118">Microsoft. v. simulace. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="25a26-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="25a26-119">Microsoft. v. simulace. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="25a26-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)