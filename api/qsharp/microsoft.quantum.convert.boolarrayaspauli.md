---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834238"
---
# <a name="boolarrayaspauli-function"></a><span data-ttu-id="aff2f-102">BoolArrayAsPauli – funkce</span><span class="sxs-lookup"><span data-stu-id="aff2f-102">BoolArrayAsPauli function</span></span>

<span data-ttu-id="aff2f-103">Obor názvů: [Microsoft. provedl. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="aff2f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="aff2f-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aff2f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aff2f-105">V případě bitového řetězce vrátí operátor qubit Pauli, který je reprezentován jako pole operátorů s jedním qubit Pauli.</span><span class="sxs-lookup"><span data-stu-id="aff2f-105">Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="aff2f-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="aff2f-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="aff2f-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="aff2f-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="aff2f-108">Pauli operátor, který se má použít pro qubits, kde `bitsApply == bits[idx]` .</span><span class="sxs-lookup"><span data-stu-id="aff2f-108">Pauli operator to apply to qubits where `bitsApply == bits[idx]`.</span></span>


### <a name="bitapply--bool"></a><span data-ttu-id="aff2f-109">bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aff2f-109">bitApply : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="aff2f-110">Pokud je tato hodnota bit, použijte Pauli.</span><span class="sxs-lookup"><span data-stu-id="aff2f-110">apply Pauli if bit is this value.</span></span>


### <a name="bits--bool"></a><span data-ttu-id="aff2f-111">bity: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="aff2f-111">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="aff2f-112">Pole Boolean.</span><span class="sxs-lookup"><span data-stu-id="aff2f-112">Boolean array.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="aff2f-113">Výstup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="aff2f-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="aff2f-114">Poznámky</span><span class="sxs-lookup"><span data-stu-id="aff2f-114">Remarks</span></span>

<span data-ttu-id="aff2f-115">Pole Boolean a registr s police musí mít stejnou délku.</span><span class="sxs-lookup"><span data-stu-id="aff2f-115">The Boolean array and the quantum register must be of equal length.</span></span>