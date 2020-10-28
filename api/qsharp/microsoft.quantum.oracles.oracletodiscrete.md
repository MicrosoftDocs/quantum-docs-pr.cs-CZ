---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708757"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="00946-102">OracleToDiscrete – funkce</span><span class="sxs-lookup"><span data-stu-id="00946-102">OracleToDiscrete function</span></span>

<span data-ttu-id="00946-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="00946-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="00946-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00946-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00946-105">Vzhledem k tomu, že operace představující "černé pole" je Oracle, vrátí nediskrétní Oracle, který představuje "černý rámeček" Oracle se opakuje několikrát.</span><span class="sxs-lookup"><span data-stu-id="00946-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="00946-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="00946-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="00946-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="00946-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="00946-108">Operace, která má být exponentiated.</span><span class="sxs-lookup"><span data-stu-id="00946-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="00946-109">Výstup: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="00946-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="00946-110">Operace se částečně nastavila na "černém" poli Oracle, které představuje diskrétní čas Oracle.</span><span class="sxs-lookup"><span data-stu-id="00946-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>