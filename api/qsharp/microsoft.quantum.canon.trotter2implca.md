---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Operace Trotter2ImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698820"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="28cf1-102">Operace Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="28cf1-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="28cf1-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28cf1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28cf1-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28cf1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28cf1-105">Implementace druhého řádu Trotter – Suzuki integrátor.</span><span class="sxs-lookup"><span data-stu-id="28cf1-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="28cf1-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="28cf1-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="28cf1-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28cf1-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28cf1-108">Počet operací rozloženého na časové kroky.</span><span class="sxs-lookup"><span data-stu-id="28cf1-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="28cf1-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="28cf1-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="28cf1-110">Operace, která přijímá vstup indexu (typ `Int` ) a vstupní čas (typ) `Double` a registr (typ) `'T` pro rozklad.</span><span class="sxs-lookup"><span data-stu-id="28cf1-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="28cf1-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="28cf1-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="28cf1-112">Multiplikátor velikosti každého kroku simulace.</span><span class="sxs-lookup"><span data-stu-id="28cf1-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="28cf1-113">cíl: t</span><span class="sxs-lookup"><span data-stu-id="28cf1-113">target : 'T</span></span>

<span data-ttu-id="28cf1-114">Registrovaná pole, na kterých operace působí.</span><span class="sxs-lookup"><span data-stu-id="28cf1-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28cf1-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28cf1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="28cf1-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="28cf1-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28cf1-117">'S</span><span class="sxs-lookup"><span data-stu-id="28cf1-117">'T</span></span>

<span data-ttu-id="28cf1-118">Typ, na který má každý krok reagovat; obvykle buď `Qubit[]` nebo `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="28cf1-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>