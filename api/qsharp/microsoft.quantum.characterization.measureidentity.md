---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operace MeasureIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851815"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="ed868-102">Operace MeasureIdentity</span><span class="sxs-lookup"><span data-stu-id="ed868-102">MeasureIdentity operation</span></span>

<span data-ttu-id="ed868-103">Obor názvů: [Microsoft.. Popis](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="ed868-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="ed868-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed868-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed868-105">Měří operátor identity v registru qubits.</span><span class="sxs-lookup"><span data-stu-id="ed868-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="ed868-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ed868-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="ed868-107">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ed868-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ed868-108">Registr, který se má měřit</span><span class="sxs-lookup"><span data-stu-id="ed868-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ed868-109">Výstup: __neplatný <Result>__</span><span class="sxs-lookup"><span data-stu-id="ed868-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ed868-110">Výsledná hodnota `Zero` .</span><span class="sxs-lookup"><span data-stu-id="ed868-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed868-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ed868-111">Remarks</span></span>

<span data-ttu-id="ed868-112">Vzhledem k tomu, že $ \boldone $ má pouze eigenvalue $1 $, a nemá negativní eigenvalue, tato operace vždy vrátí hodnotu `Zero` odpovídající eigenvalue $ + 1 = (-1) ^ 0 $ a nezpůsobí sbalení stavu `register` .</span><span class="sxs-lookup"><span data-stu-id="ed868-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="ed868-113">Sám o sobě tato operace není užitečná, ale je užitečná v kontextu procesu tomography, protože poskytuje informace o uchovávání sledování v rámci procesu.</span><span class="sxs-lookup"><span data-stu-id="ed868-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="ed868-114">Konkrétně cílový počítač se ztrátovou měřením by měl tuto operaci nahradit skutečným měřením $ \boldone $.</span><span class="sxs-lookup"><span data-stu-id="ed868-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>