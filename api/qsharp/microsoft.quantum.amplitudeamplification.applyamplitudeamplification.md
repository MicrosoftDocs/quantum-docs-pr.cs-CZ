---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: Operace ApplyAmplitudeAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: 8fd5c3f20c5a5aaae140feaf3af02395bff77b9c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845882"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="25993-102">Operace ApplyAmplitudeAmplification</span><span class="sxs-lookup"><span data-stu-id="25993-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="25993-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="25993-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="25993-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25993-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25993-105">U daného registru aplikuje zesílení amplitud pomocí dané sady fází a Oracle, aby odrážely počáteční a konečné stavy.</span><span class="sxs-lookup"><span data-stu-id="25993-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="25993-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="25993-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="25993-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="25993-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="25993-108">Sada fází popisujících částečné odrazy u každého kroku algoritmu zesílení amplitud.</span><span class="sxs-lookup"><span data-stu-id="25993-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="25993-109">Příklad najdete v tématu @"microsoft.quantum.amplitudeamplification.standardreflectionphases" .</span><span class="sxs-lookup"><span data-stu-id="25993-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="25993-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="25993-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="25993-111">Oracle, který odpovídá počátečnímu stavu.</span><span class="sxs-lookup"><span data-stu-id="25993-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="25993-112">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="25993-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="25993-113">Oracle, který odráží informace o požadovaném konečném stavu.</span><span class="sxs-lookup"><span data-stu-id="25993-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="25993-114">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="25993-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="25993-115">Registrace, na které se má provést zesílení amplitudy</span><span class="sxs-lookup"><span data-stu-id="25993-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="25993-116">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="25993-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

