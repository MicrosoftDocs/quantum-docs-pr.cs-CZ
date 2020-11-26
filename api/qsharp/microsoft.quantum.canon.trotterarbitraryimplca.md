---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Operace TrotterArbitraryImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 2abfbb9d51a98d8ede1b0835875a3771ffda0691
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204721"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="4bb5c-102">Operace TrotterArbitraryImplCA</span><span class="sxs-lookup"><span data-stu-id="4bb5c-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="4bb5c-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4bb5c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4bb5c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4bb5c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4bb5c-105">Rekurzivní implementace sudého a Trotterho integrátoru – Suzuki.</span><span class="sxs-lookup"><span data-stu-id="4bb5c-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4bb5c-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="4bb5c-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="4bb5c-107">pořadí: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4bb5c-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4bb5c-108">Pořadí Trotter-Suzuki integrátoru.</span><span class="sxs-lookup"><span data-stu-id="4bb5c-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="4bb5c-109">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4bb5c-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4bb5c-110">Počet operací rozloženého na časové kroky.</span><span class="sxs-lookup"><span data-stu-id="4bb5c-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="4bb5c-111">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="4bb5c-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4bb5c-112">Operace, která přijímá vstup indexu (typ `Int` ) a vstupní čas (typ) `Double` a registr (typ) `'T` pro rozklad.</span><span class="sxs-lookup"><span data-stu-id="4bb5c-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="4bb5c-113">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4bb5c-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4bb5c-114">Multiplikátor velikosti každého kroku simulace.</span><span class="sxs-lookup"><span data-stu-id="4bb5c-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="4bb5c-115">cíl: t</span><span class="sxs-lookup"><span data-stu-id="4bb5c-115">target : 'T</span></span>

<span data-ttu-id="4bb5c-116">Registrovaná pole, na kterých operace působí.</span><span class="sxs-lookup"><span data-stu-id="4bb5c-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4bb5c-117">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4bb5c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4bb5c-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4bb5c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4bb5c-119">'S</span><span class="sxs-lookup"><span data-stu-id="4bb5c-119">'T</span></span>

<span data-ttu-id="4bb5c-120">Typ, na který má každý krok reagovat; obvykle buď `Qubit[]` nebo `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="4bb5c-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>