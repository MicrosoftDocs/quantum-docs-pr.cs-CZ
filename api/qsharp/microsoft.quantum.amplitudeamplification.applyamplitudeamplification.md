---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: Operace ApplyAmplitudeAmplification
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: 0b40f94633bb43df5e64cd16d5ac8e12bcd1cc4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191563"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="c2914-102">Operace ApplyAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="c2914-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="c2914-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="c2914-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="c2914-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2914-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2914-105">U daného registru aplikuje zesílení amplitud pomocí dané sady fází a Oracle, aby odrážely počáteční a konečné stavy.</span><span class="sxs-lookup"><span data-stu-id="c2914-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c2914-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c2914-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="c2914-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="c2914-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="c2914-108">Sada fází popisujících částečné odrazy u každého kroku algoritmu zesílení amplitud.</span><span class="sxs-lookup"><span data-stu-id="c2914-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="c2914-109">Příklad najdete v tématu @"microsoft.quantum.amplitudeamplification.standardreflectionphases" .</span><span class="sxs-lookup"><span data-stu-id="c2914-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="c2914-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="c2914-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="c2914-111">Oracle, který odpovídá počátečnímu stavu.</span><span class="sxs-lookup"><span data-stu-id="c2914-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="c2914-112">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="c2914-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="c2914-113">Oracle, který odráží informace o požadovaném konečném stavu.</span><span class="sxs-lookup"><span data-stu-id="c2914-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c2914-114">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c2914-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c2914-115">Registrace, na které se má provést zesílení amplitudy</span><span class="sxs-lookup"><span data-stu-id="c2914-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c2914-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2914-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

