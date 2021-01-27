---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Operace ApplyPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844742"
---
# <a name="applypauli-operation"></a><span data-ttu-id="73e7b-102">Operace ApplyPauli</span><span class="sxs-lookup"><span data-stu-id="73e7b-102">ApplyPauli operation</span></span>

<span data-ttu-id="73e7b-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="73e7b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="73e7b-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73e7b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73e7b-105">Pomocí operátoru qubit Pauli použije odpovídající operaci na registraci.</span><span class="sxs-lookup"><span data-stu-id="73e7b-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="73e7b-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="73e7b-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="73e7b-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="73e7b-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="73e7b-108">Qubit Pauli operátor reprezentovaný jako pole operátorů s jedním qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="73e7b-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="73e7b-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73e7b-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="73e7b-110">Zaregistrujte se na použití dané operace Pauli na.</span><span class="sxs-lookup"><span data-stu-id="73e7b-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="73e7b-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73e7b-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="73e7b-112">Příklad</span><span class="sxs-lookup"><span data-stu-id="73e7b-112">Example</span></span>

<span data-ttu-id="73e7b-113">Následují ekvivalenty:</span><span class="sxs-lookup"><span data-stu-id="73e7b-113">The following are equivalent:</span></span>

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

<span data-ttu-id="73e7b-114">a</span><span class="sxs-lookup"><span data-stu-id="73e7b-114">and</span></span>

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```