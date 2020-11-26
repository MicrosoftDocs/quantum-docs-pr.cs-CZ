---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Operace ApplyPauliFromBitString
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: cf4c99ec5134fac788cdd4c8a057258790152a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209056"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="26faa-102">Operace ApplyPauliFromBitString</span><span class="sxs-lookup"><span data-stu-id="26faa-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="26faa-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="26faa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="26faa-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26faa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26faa-105">Aplikuje operátor Pauli na každou qubit v poli, pokud odpovídající bit logického pole odpovídá danému vstupu.</span><span class="sxs-lookup"><span data-stu-id="26faa-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="26faa-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="26faa-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="26faa-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="26faa-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="26faa-108">Operátor Pauli, který se má použít na `qubits[idx]` WHERE `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="26faa-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="26faa-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26faa-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26faa-110">Pokud je tato hodnota bit, použijte Pauli.</span><span class="sxs-lookup"><span data-stu-id="26faa-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="26faa-111">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="26faa-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="26faa-112">Logický registr určující, který odpovídající qubit v `qubits` by měl být provozován</span><span class="sxs-lookup"><span data-stu-id="26faa-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="26faa-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="26faa-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="26faa-114">Registrování v registru, ve kterém se selektivně použijí zadaný Pauli operátor</span><span class="sxs-lookup"><span data-stu-id="26faa-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="26faa-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26faa-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="26faa-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="26faa-116">Remarks</span></span>

<span data-ttu-id="26faa-117">Pole Boolean a registr s police musí mít stejnou délku.</span><span class="sxs-lookup"><span data-stu-id="26faa-117">The Boolean array and the quantum register must be of equal length.</span></span>