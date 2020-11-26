---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: Uživatelem definovaný typ ObliviousOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 2f92dcb28ec669229dfaf9bcb23eef9234552b8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193875"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="dde16-102">Uživatelem definovaný typ ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="dde16-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="dde16-103">Obor názvů: [Microsoft.... Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="dde16-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="dde16-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dde16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dde16-105">Představuje systém Oracle pro zesílení amplitud oblivious.</span><span class="sxs-lookup"><span data-stu-id="dde16-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="dde16-106">Vstupy pro Oracle $O $ jsou:</span><span class="sxs-lookup"><span data-stu-id="dde16-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="dde16-107">Registr ancilla $a $, na kterém $O $ funguje.</span><span class="sxs-lookup"><span data-stu-id="dde16-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="dde16-108">Registr systému $s $, na kterém se aplikuje požadovaná Jednotková $U $, po vybírání v registru $a $ se ve stavu $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="dde16-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="dde16-109">Poznámky</span><span class="sxs-lookup"><span data-stu-id="dde16-109">Remarks</span></span>

<span data-ttu-id="dde16-110">Tento jazyk Oracle definovaný pomocí $ $ O\ket {s} \_ a\ket {\ psí} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ funguje ve stavu ancilla $ \ket{s} \_ a, který implementuje jednotkové $U $ v jakémkoli stavu systému $ \ket{\psi} \_ s $ s amplitudou $ \lambda $ v souladu s příznakem $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="dde16-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="dde16-111">Prvním parametrem je qubit registr $ \ket{s} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="dde16-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="dde16-112">Druhým parametrem je qubit registr $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="dde16-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>