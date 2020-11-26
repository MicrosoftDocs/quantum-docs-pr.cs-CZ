---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operace SelectZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224713"
---
# <a name="selectz-operation"></a><span data-ttu-id="fe3fa-102">Operace SelectZ</span><span class="sxs-lookup"><span data-stu-id="fe3fa-102">SelectZ operation</span></span>

<span data-ttu-id="fe3fa-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="fe3fa-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="fe3fa-105">Jednotková $U $, která aplikuje bránu $Z Pauli na qubits $p $ podmíněně ve stavu indexu $ \ket{p} $.</span><span class="sxs-lookup"><span data-stu-id="fe3fa-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="fe3fa-106">To znamená $ $ \begin{align} U\ket {p} \ KET {\ psí} = \ket{p}Z \_ p\ket {\ psí} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="fe3fa-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fe3fa-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="fe3fa-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="fe3fa-108">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fe3fa-109">Stav $ \ket{p} $ tohoto registru určuje qubit, na kterém je použita $Z $.</span><span class="sxs-lookup"><span data-stu-id="fe3fa-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="fe3fa-110">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fe3fa-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fe3fa-111">Registr qubits, na kterých se používají operátory Pauli</span><span class="sxs-lookup"><span data-stu-id="fe3fa-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe3fa-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe3fa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

