---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operace MeasureIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698721"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="3c208-102">Operace MeasureIdentity</span><span class="sxs-lookup"><span data-stu-id="3c208-102">MeasureIdentity operation</span></span>

<span data-ttu-id="3c208-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="3c208-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="3c208-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c208-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c208-105">Měří operátor identity v registru qubits.</span><span class="sxs-lookup"><span data-stu-id="3c208-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="3c208-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3c208-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="3c208-107">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3c208-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3c208-108">Registr, který se má měřit</span><span class="sxs-lookup"><span data-stu-id="3c208-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="3c208-109">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="3c208-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="3c208-110">Výsledná hodnota `Zero` .</span><span class="sxs-lookup"><span data-stu-id="3c208-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3c208-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3c208-111">Remarks</span></span>

<span data-ttu-id="3c208-112">Vzhledem k tomu, že $ \boldone $ má pouze eigenvalue $1 $, a nemá negativní eigenvalue, tato operace vždy vrátí hodnotu `Zero` odpovídající eigenvalue $ + 1 = (-1) ^ 0 $ a nezpůsobí sbalení stavu `register` .</span><span class="sxs-lookup"><span data-stu-id="3c208-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="3c208-113">Sám o sobě tato operace není užitečná, ale je užitečná v kontextu procesu tomography, protože poskytuje informace o uchovávání sledování v rámci procesu.</span><span class="sxs-lookup"><span data-stu-id="3c208-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="3c208-114">Konkrétně cílový počítač se ztrátovou měřením by měl tuto operaci nahradit skutečným měřením $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="3c208-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>