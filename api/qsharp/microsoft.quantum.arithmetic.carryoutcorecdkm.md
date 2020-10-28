---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operace CarryOutCoreCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707400"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="99d42-102">Operace CarryOutCoreCDKM</span><span class="sxs-lookup"><span data-stu-id="99d42-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="99d42-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="99d42-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="99d42-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99d42-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99d42-105">Základní operace v RippleCarryAdderCDKM, která se používá s výše uvedenou operací ApplyOuterCDKMAdder, tj. sdružená s touto operací k získání vnitřní operace RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="99d42-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="99d42-106">Tato operace vypočítá qubit a v rámci vstupu aplikuje sekvenci Nebran `ys` .</span><span class="sxs-lookup"><span data-stu-id="99d42-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="99d42-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="99d42-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="99d42-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="99d42-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="99d42-109">První qubit registrace</span><span class="sxs-lookup"><span data-stu-id="99d42-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="99d42-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="99d42-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="99d42-111">Druhý qubit registr.</span><span class="sxs-lookup"><span data-stu-id="99d42-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="99d42-112">ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="99d42-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="99d42-113">Do této operace byla předána ancilla qubit použitá v RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="99d42-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="99d42-114">přenést: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="99d42-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="99d42-115">Proveďte qubit v operaci RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="99d42-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99d42-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99d42-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="99d42-117">Odkazy</span><span class="sxs-lookup"><span data-stu-id="99d42-117">References</span></span>

- <span data-ttu-id="99d42-118">Steven A. Cuccaro, Tomáš G. Draper, Samuel A. Kutin, David Petrie Moulton: "nové v rámci Ripple – přenést okruh", 2004.</span><span class="sxs-lookup"><span data-stu-id="99d42-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1