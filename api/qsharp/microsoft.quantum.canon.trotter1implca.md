---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Operace Trotter1ImplCA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1b4e0a9597f4f30b8e92ef91ff0780e7c7ecdc9b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204789"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="39054-102">Operace Trotter1ImplCA</span><span class="sxs-lookup"><span data-stu-id="39054-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="39054-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39054-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39054-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39054-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39054-105">Implementace prvního řádu Trotter – Suzuki integrátor.</span><span class="sxs-lookup"><span data-stu-id="39054-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="39054-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="39054-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="39054-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39054-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39054-108">Počet operací rozloženého na časové kroky.</span><span class="sxs-lookup"><span data-stu-id="39054-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="39054-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="39054-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="39054-110">Operace, která přijímá vstup indexu (typ `Int` ) a vstupní čas (typ) `Double` a registr (typ) `'T` pro rozklad.</span><span class="sxs-lookup"><span data-stu-id="39054-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="39054-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="39054-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="39054-112">Multiplikátor velikosti každého kroku simulace.</span><span class="sxs-lookup"><span data-stu-id="39054-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="39054-113">cíl: t</span><span class="sxs-lookup"><span data-stu-id="39054-113">target : 'T</span></span>

<span data-ttu-id="39054-114">Registrovaná pole, na kterých operace působí.</span><span class="sxs-lookup"><span data-stu-id="39054-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39054-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39054-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="39054-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="39054-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39054-117">'S</span><span class="sxs-lookup"><span data-stu-id="39054-117">'T</span></span>

<span data-ttu-id="39054-118">Typ, na který má každý krok reagovat; obvykle buď `Qubit[]` nebo `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="39054-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>