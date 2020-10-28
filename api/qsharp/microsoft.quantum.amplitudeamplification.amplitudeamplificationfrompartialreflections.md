---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707773"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="3bec7-102">AmplitudeAmplificationFromPartialReflections – funkce</span><span class="sxs-lookup"><span data-stu-id="3bec7-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="3bec7-103">Obor názvů: [Microsoft. AmplitudeAmplification.](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="3bec7-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="3bec7-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3bec7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3bec7-105">Amplituda amplitud na základě částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="3bec7-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="3bec7-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3bec7-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="3bec7-107">fáze: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="3bec7-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="3bec7-108">Fáze částečných odrazů</span><span class="sxs-lookup"><span data-stu-id="3bec7-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="3bec7-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="3bec7-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="3bec7-110">Operátor reflexe o počátečním stavu</span><span class="sxs-lookup"><span data-stu-id="3bec7-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="3bec7-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="3bec7-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="3bec7-112">Operátor reflexe pro cílový stav</span><span class="sxs-lookup"><span data-stu-id="3bec7-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="3bec7-113">Výstup: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="3bec7-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="3bec7-114">Operace, která implementuje zesílení amplitud pomocí částečných odrazů.</span><span class="sxs-lookup"><span data-stu-id="3bec7-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="3bec7-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3bec7-115">Remarks</span></span>

<span data-ttu-id="3bec7-116">Zesílení amplitud je zvláštní případ oblivious zesílení amplitud, kde nejsou žádné systémové qubits a oblivious Oracle je nastavená na identity.</span><span class="sxs-lookup"><span data-stu-id="3bec7-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="3bec7-117">Ve většině případů `startQubits` je inicializován ve stavu $ \ket{\text{start}} \_ $1, což je eigenstate $-$1 pro `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="3bec7-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>