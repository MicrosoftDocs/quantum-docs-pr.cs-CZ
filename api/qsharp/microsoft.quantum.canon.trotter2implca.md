---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Operace Trotter2ImplCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 34b60934b67c19b2d1d718d68b85a2f0fffeab5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852023"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="f9ebe-102">Operace Trotter2ImplCA</span><span class="sxs-lookup"><span data-stu-id="f9ebe-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="f9ebe-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f9ebe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f9ebe-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9ebe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9ebe-105">Implementace druhého řádu Trotter – Suzuki integrátor.</span><span class="sxs-lookup"><span data-stu-id="f9ebe-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f9ebe-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="f9ebe-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="f9ebe-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9ebe-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9ebe-108">Počet operací rozloženého na časové kroky.</span><span class="sxs-lookup"><span data-stu-id="f9ebe-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="f9ebe-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f9ebe-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f9ebe-110">Operace, která přijímá vstup indexu (typ `Int` ) a vstupní čas (typ) `Double` a registr (typ) `'T` pro rozklad.</span><span class="sxs-lookup"><span data-stu-id="f9ebe-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="f9ebe-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f9ebe-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f9ebe-112">Multiplikátor velikosti každého kroku simulace.</span><span class="sxs-lookup"><span data-stu-id="f9ebe-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="f9ebe-113">cíl: t</span><span class="sxs-lookup"><span data-stu-id="f9ebe-113">target : 'T</span></span>

<span data-ttu-id="f9ebe-114">Registrovaná pole, na kterých operace působí.</span><span class="sxs-lookup"><span data-stu-id="f9ebe-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9ebe-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9ebe-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9ebe-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f9ebe-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9ebe-117">'S</span><span class="sxs-lookup"><span data-stu-id="f9ebe-117">'T</span></span>

<span data-ttu-id="f9ebe-118">Typ, na který má každý krok reagovat; obvykle buď `Qubit[]` nebo `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="f9ebe-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="f9ebe-119">Příklad</span><span class="sxs-lookup"><span data-stu-id="f9ebe-119">Example</span></span>

<span data-ttu-id="f9ebe-120">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="f9ebe-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(0, deltaT / 2.0, target);
```

<span data-ttu-id="f9ebe-121">a</span><span class="sxs-lookup"><span data-stu-id="f9ebe-121">and</span></span>

```qsharp
Trotter2ImplCA((2, op), deltaT, target);
```