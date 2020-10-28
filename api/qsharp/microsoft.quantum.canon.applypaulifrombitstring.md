---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Operace ApplyPauliFromBitString
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: 09754accb92c1339b781003e5722e3c8f5884e6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705105"
---
# <a name="applypaulifrombitstring-operation"></a><span data-ttu-id="09ff8-102">Operace ApplyPauliFromBitString</span><span class="sxs-lookup"><span data-stu-id="09ff8-102">ApplyPauliFromBitString operation</span></span>

<span data-ttu-id="09ff8-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09ff8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09ff8-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09ff8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09ff8-105">Aplikuje operátor Pauli na každou qubit v poli, pokud odpovídající bit logického pole odpovídá danému vstupu.</span><span class="sxs-lookup"><span data-stu-id="09ff8-105">Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.</span></span>

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="09ff8-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="09ff8-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="09ff8-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="09ff8-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="09ff8-108">Operátor Pauli, který se má použít na `qubits[idx]` WHERE `bitsApply == bits[idx]`</span><span class="sxs-lookup"><span data-stu-id="09ff8-108">Pauli operator to apply to `qubits[idx]` where `bitsApply == bits[idx]`</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="09ff8-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="09ff8-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="09ff8-110">Pokud je tato hodnota bit, použijte Pauli.</span><span class="sxs-lookup"><span data-stu-id="09ff8-110">apply Pauli if bit is this value</span></span>


### <a name="bits--bool"></a><span data-ttu-id="09ff8-111">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="09ff8-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="09ff8-112">Logický registr určující, který odpovídající qubit v `qubits` by měl být provozován</span><span class="sxs-lookup"><span data-stu-id="09ff8-112">Boolean register specifying which corresponding qubit in `qubits` should be operated on</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="09ff8-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="09ff8-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="09ff8-114">Registrování v registru, ve kterém se selektivně použijí zadaný Pauli operátor</span><span class="sxs-lookup"><span data-stu-id="09ff8-114">Quantum register on which to selectively apply the specified Pauli operator</span></span>



## <a name="output--unit"></a><span data-ttu-id="09ff8-115">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09ff8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="09ff8-116">Poznámky</span><span class="sxs-lookup"><span data-stu-id="09ff8-116">Remarks</span></span>

<span data-ttu-id="09ff8-117">Pole Boolean a registr s police musí mít stejnou délku.</span><span class="sxs-lookup"><span data-stu-id="09ff8-117">The Boolean array and the quantum register must be of equal length.</span></span>