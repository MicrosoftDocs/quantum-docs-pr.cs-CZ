---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operace CarryOutCoreCDKM
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 19a692a3b54a413f25a474c361e773ab6c65579e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223540"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="3956e-102">Operace CarryOutCoreCDKM</span><span class="sxs-lookup"><span data-stu-id="3956e-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="3956e-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3956e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3956e-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3956e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3956e-105">Základní operace v RippleCarryAdderCDKM, která se používá s výše uvedenou operací ApplyOuterCDKMAdder, tj. sdružená s touto operací k získání vnitřní operace RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="3956e-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="3956e-106">Tato operace vypočítá qubit a v rámci vstupu aplikuje sekvenci Nebran `ys` .</span><span class="sxs-lookup"><span data-stu-id="3956e-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3956e-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="3956e-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="3956e-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3956e-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3956e-109">První qubit registrace</span><span class="sxs-lookup"><span data-stu-id="3956e-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="3956e-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3956e-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3956e-111">Druhý qubit registr.</span><span class="sxs-lookup"><span data-stu-id="3956e-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="3956e-112">ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3956e-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3956e-113">Do této operace byla předána ancilla qubit použitá v RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="3956e-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="3956e-114">přenést: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3956e-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3956e-115">Proveďte qubit v operaci RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="3956e-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3956e-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3956e-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="3956e-117">Reference</span><span class="sxs-lookup"><span data-stu-id="3956e-117">References</span></span>

- <span data-ttu-id="3956e-118">Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton: "nové v rámci Ripple – přenést okruh", 2004.</span><span class="sxs-lookup"><span data-stu-id="3956e-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1