---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Operace ApplyPauliFromBitString
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841589"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="41b05-102">Operace ApplyPauliFromBitString</span><span class="sxs-lookup"><span data-stu-id="41b05-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="41b05-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41b05-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41b05-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41b05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41b05-105">Aplikuje operátor Pauli na každou qubit v poli, pokud odpovídající bit logického pole odpovídá danému vstupu.</span><span class="sxs-lookup"><span data-stu-id="41b05-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="41b05-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="41b05-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="41b05-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="41b05-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="41b05-108">Operátor Pauli, který se má použít na `qubits[idx]` WHERE `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="41b05-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="41b05-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="41b05-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="41b05-110">Pokud je tato hodnota bit, použijte Pauli.</span><span class="sxs-lookup"><span data-stu-id="41b05-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="41b05-111">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="41b05-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="41b05-112">Logický registr určující, který odpovídající qubit v `qubits` by měl být provozován</span><span class="sxs-lookup"><span data-stu-id="41b05-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="41b05-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="41b05-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="41b05-114">Registrování v registru, ve kterém se selektivně použijí zadaný Pauli operátor</span><span class="sxs-lookup"><span data-stu-id="41b05-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="41b05-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41b05-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="41b05-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="41b05-116">Remarks</span></span>

<span data-ttu-id="41b05-117">Pole Boolean a registr s police musí mít stejnou délku.</span><span class="sxs-lookup"><span data-stu-id="41b05-117">The Boolean array and the quantum register must be of equal length.</span></span>