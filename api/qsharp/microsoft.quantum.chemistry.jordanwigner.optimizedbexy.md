---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: Operace OptimizedBEXY
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 3530e62671e16cfb5500c56c8e5e477dbb56e67e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224849"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="a76e6-102">Operace OptimizedBEXY</span><span class="sxs-lookup"><span data-stu-id="a76e6-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="a76e6-103">Obor názvů: [Microsoft. JordanWigner. chemie.](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="a76e6-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="a76e6-104">Balíček: [Microsoft.. chemie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a76e6-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a76e6-105">Jednotková $U $, která používá řetězec Pauli v $ (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 $ on qubits $0.. p $ podmíněně v indexu $z \in \{ 0, 1 \} $ a $p $.</span><span class="sxs-lookup"><span data-stu-id="a76e6-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="a76e6-106">To znamená $ $ \begin{align} U\ket {z} \ KET {p} \ KET {\ psí} = \ket{z}\ket{p} (X ^ {z + 1} \_ py ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a76e6-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a76e6-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="a76e6-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="a76e6-108">pauliBasis: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a76e6-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a76e6-109">Pokud je tento qubit ve stavu $ \ket {0} $, použije se $X $.</span><span class="sxs-lookup"><span data-stu-id="a76e6-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="a76e6-110">Pokud je ve stavu $ \ket {1} $, použije se $Y $.</span><span class="sxs-lookup"><span data-stu-id="a76e6-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="a76e6-111">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a76e6-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a76e6-112">Stav $ \ket{p} $ tohoto registru určuje qubit, na kterém je použita $X $ nebo $Y $.</span><span class="sxs-lookup"><span data-stu-id="a76e6-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="a76e6-113">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a76e6-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a76e6-114">Registr qubits, na kterých se používají operátory Pauli</span><span class="sxs-lookup"><span data-stu-id="a76e6-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a76e6-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a76e6-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="a76e6-116">Reference</span><span class="sxs-lookup"><span data-stu-id="a76e6-116">References</span></span>

- <span data-ttu-id="a76e6-117">Kódování elektronického spektra v Okruhech v případě využití lineární T, Babbush, Craig Gidney, Dominic W. bobulovin, Nathan Wiebe, Jarrod McClean, Alexandru bledější, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="a76e6-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>