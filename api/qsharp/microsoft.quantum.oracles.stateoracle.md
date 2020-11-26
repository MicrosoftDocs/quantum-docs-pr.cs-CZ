---
uid: Microsoft.Quantum.Oracles.StateOracle
title: Uživatelem definovaný typ StateOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226600"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="f0e0a-102">Uživatelem definovaný typ StateOracle</span><span class="sxs-lookup"><span data-stu-id="f0e0a-102">StateOracle user defined type</span></span>

<span data-ttu-id="f0e0a-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="f0e0a-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="f0e0a-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0e0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0e0a-105">Představuje Oracle pro přípravu stavu.</span><span class="sxs-lookup"><span data-stu-id="f0e0a-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="f0e0a-106">Vstupy pro Oracle $O $ jsou:</span><span class="sxs-lookup"><span data-stu-id="f0e0a-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="f0e0a-107">Celé číslo, které označuje příznak qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="f0e0a-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="f0e0a-108">Systém registruje $s $, ve kterém bude uložen požadovaný stav \ket{\psi} $ \_ s $.</span><span class="sxs-lookup"><span data-stu-id="f0e0a-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="f0e0a-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="f0e0a-109">Remarks</span></span>

<span data-ttu-id="f0e0a-110">Tento jazyk Oracle definovaný pomocí $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psí} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ funguje na výpočetním stavu na bázi výpočtů $ \ket {0} \_ {f} \ket {0} \_ s $, který vytvoří cílový stav $ \ket{\psi} s \_ $ s amplitudou $ \lambda $ v tomto případě příznakem $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="f0e0a-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="f0e0a-111">První parametr je index qubit registrace \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="f0e0a-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="f0e0a-112">Druhý parametr zahrnuje oba Registry.</span><span class="sxs-lookup"><span data-stu-id="f0e0a-112">The second parameter encompassed both registers.</span></span>