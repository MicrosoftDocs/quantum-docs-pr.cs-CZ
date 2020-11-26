---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Operace DumpOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202052"
---
# <a name="dumpoperation-operation"></a><span data-ttu-id="386f5-102">Operace DumpOperation</span><span class="sxs-lookup"><span data-stu-id="386f5-102">DumpOperation operation</span></span>

<span data-ttu-id="386f5-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="386f5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="386f5-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="386f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="386f5-105">V případě určité operace zobrazí diagnostiku operace, které jsou zpřístupněny aktuálním cílem provedení.</span><span class="sxs-lookup"><span data-stu-id="386f5-105">Given an operation, displays diagnostics about the operation that are made available by the current execution target.</span></span>

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="386f5-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="386f5-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="386f5-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="386f5-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="386f5-108">Počet qubits, na kterých daná operace funguje.</span><span class="sxs-lookup"><span data-stu-id="386f5-108">The number of qubits on which the given operation acts.</span></span>


### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="386f5-109">op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ.</span><span class="sxs-lookup"><span data-stu-id="386f5-109">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="386f5-110">Operace, která se má diagnostikovat</span><span class="sxs-lookup"><span data-stu-id="386f5-110">The operation that is to be diagnosed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="386f5-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="386f5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="386f5-112">Poznámky</span><span class="sxs-lookup"><span data-stu-id="386f5-112">Remarks</span></span>

<span data-ttu-id="386f5-113">Volání této operace nemá žádný pozorovatelný účinek v rámci Q #.</span><span class="sxs-lookup"><span data-stu-id="386f5-113">Calling this operation has no observable effect from within Q#.</span></span> <span data-ttu-id="386f5-114">Přesná diagnostika, která se zobrazí, je-li k, závisí na aktuálním cílovém spuštění a prostředí editoru.</span><span class="sxs-lookup"><span data-stu-id="386f5-114">The exact diagnostics that are displayed, if any, are dependent on the current execution target and editor environment.</span></span>
<span data-ttu-id="386f5-115">Například při použití v případě simulátoru s plným stavem se zobrazí jednotná matice, která se reprezentuje `op` .</span><span class="sxs-lookup"><span data-stu-id="386f5-115">For example, when used on the full-state quantum simulator, a unitary matrix used to represent `op` is displayed.</span></span>

<span data-ttu-id="386f5-116">Všimněte si, že při spuštění simulátorů, které připouštějí nejednoznačnost globální fáze (např. simulátor s plným stavem), se můžou vrátit reprezentace, která se může lišit až do globální fáze.</span><span class="sxs-lookup"><span data-stu-id="386f5-116">Note that, when run on simulators that admit a global phase ambiguity (e.g.: the full-state simulator), returned representations may vary up to a global phase.</span></span>

<span data-ttu-id="386f5-117">Podobně pořadí reprezentace řádků a sloupců se může lišit od konvencí používaných jednotlivými simulátory podporující tuto operaci.</span><span class="sxs-lookup"><span data-stu-id="386f5-117">Similarly, the ordering of rows and columns matrix representations may vary with the conventions used by each simulator supporting this operation.</span></span>