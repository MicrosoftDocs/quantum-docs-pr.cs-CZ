---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Operace LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704032"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="573df-102">Operace LogicalANDMeasAndFix</span><span class="sxs-lookup"><span data-stu-id="573df-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="573df-103">Obor názvů: [Microsoft.. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="573df-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="573df-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="573df-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="573df-105">Vypočítá logickou a více qubits.</span><span class="sxs-lookup"><span data-stu-id="573df-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="573df-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="573df-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="573df-107">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="573df-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="573df-108">Qubits vstup do vícenásobného vstupu a brány.</span><span class="sxs-lookup"><span data-stu-id="573df-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="573df-109">cíl: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="573df-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="573df-110">Qubit, na který výstup a se zapisuje.</span><span class="sxs-lookup"><span data-stu-id="573df-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="573df-111">Předpokládá se, že se vždycky spustí ve stavu $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="573df-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="573df-112">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="573df-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="573df-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="573df-113">Remarks</span></span>

<span data-ttu-id="573df-114">Pokud `ctrlRegister` má přesně $2 $ qubits, jedná se o ekvivalent `CCNOT` operace, ale fáze se fází $e ^ {i \ pi/2} $ v $ \ket {001} $ a $-e ^ {i \ pi/2} $ v $ \ket {101} $ a $ \ket {011} $.</span><span class="sxs-lookup"><span data-stu-id="573df-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="573df-115">Sousedícít je také metoda měření a opravy, která je inverzní k původní operaci pouze ve zvláštních případech (viz odkazy), ale používá méně T-bran.</span><span class="sxs-lookup"><span data-stu-id="573df-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="573df-116">Odkazy</span><span class="sxs-lookup"><span data-stu-id="573df-116">References</span></span>

- [<span data-ttu-id="573df-117">*Craig Gidney* , 1709,06648</span><span class="sxs-lookup"><span data-stu-id="573df-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)