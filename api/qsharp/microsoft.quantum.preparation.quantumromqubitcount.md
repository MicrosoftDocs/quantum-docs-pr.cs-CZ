---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708193"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="38090-102">QuantumROMQubitCount – funkce</span><span class="sxs-lookup"><span data-stu-id="38090-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="38090-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="38090-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="38090-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38090-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38090-105">Vrátí celkový počet qubits, které musí být přiděleny k operaci vrácené funkcí `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="38090-105">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="38090-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="38090-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="38090-107">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="38090-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="38090-108">Cílová chyba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="38090-108">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="38090-109">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="38090-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="38090-110">Počet koeficientů, které jsou zadány v `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="38090-110">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="38090-111">Výstup: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="38090-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="38090-112">První parametr</span><span class="sxs-lookup"><span data-stu-id="38090-112">First parameter</span></span>

<span data-ttu-id="38090-113">Řazená kolekce členů `(x,(y,z))` `x = y + z` , kde je celkový počet přidělených qubits, `y` je počet qubits pro `LittleEndian` registr a `z` počet qubitsů paměti.</span><span class="sxs-lookup"><span data-stu-id="38090-113">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>