---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856798"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="67ea4-102">QuantumROMQubitCount – funkce</span><span class="sxs-lookup"><span data-stu-id="67ea4-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="67ea4-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="67ea4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="67ea4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67ea4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="67ea4-105">QuantumROMQubitCount se už nepoužívá.</span><span class="sxs-lookup"><span data-stu-id="67ea4-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="67ea4-106"><xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements>Místo toho ho použijte.</span><span class="sxs-lookup"><span data-stu-id="67ea4-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="67ea4-107">Vrátí celkový počet qubits, které musí být přiděleny k operaci vrácené funkcí `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="67ea4-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="67ea4-108">Vstup</span><span class="sxs-lookup"><span data-stu-id="67ea4-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="67ea4-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67ea4-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67ea4-110">Cílová chyba $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="67ea4-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="67ea4-111">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="67ea4-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="67ea4-112">Počet koeficientů, které jsou zadány v `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="67ea4-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="67ea4-113">Výstup: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="67ea4-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="67ea4-114">První parametr</span><span class="sxs-lookup"><span data-stu-id="67ea4-114">First parameter</span></span>

<span data-ttu-id="67ea4-115">Řazená kolekce členů `(x,(y,z))` `x = y + z` , kde je celkový počet přidělených qubits, `y` je počet qubits pro `LittleEndian` registr a `z` počet qubitsů paměti.</span><span class="sxs-lookup"><span data-stu-id="67ea4-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>