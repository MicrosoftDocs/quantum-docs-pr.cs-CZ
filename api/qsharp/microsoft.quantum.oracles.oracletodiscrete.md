---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842541"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="c6aae-102">OracleToDiscrete – funkce</span><span class="sxs-lookup"><span data-stu-id="c6aae-102">OracleToDiscrete function</span></span>

<span data-ttu-id="c6aae-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c6aae-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c6aae-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6aae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6aae-105">Vzhledem k tomu, že operace představující "černé pole" je Oracle, vrátí nediskrétní Oracle, který představuje "černý rámeček" Oracle se opakuje několikrát.</span><span class="sxs-lookup"><span data-stu-id="c6aae-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="c6aae-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="c6aae-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="c6aae-107">blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="c6aae-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c6aae-108">Operace, která má být exponentiated.</span><span class="sxs-lookup"><span data-stu-id="c6aae-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="c6aae-109">Výstup: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="c6aae-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="c6aae-110">Operace se částečně nastavila na "černém" poli Oracle, které představuje diskrétní čas Oracle.</span><span class="sxs-lookup"><span data-stu-id="c6aae-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>

## <a name="example"></a><span data-ttu-id="c6aae-111">Příklad</span><span class="sxs-lookup"><span data-stu-id="c6aae-111">Example</span></span>

<span data-ttu-id="c6aae-112">`OracleToDiscrete(U)(3, target)` odpovídá `U(target)` opakování třikrát.</span><span class="sxs-lookup"><span data-stu-id="c6aae-112">`OracleToDiscrete(U)(3, target)` is equivalent to `U(target)` repeated three times.</span></span>