---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: Operace ApplyUnitary
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859162"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="d6bf4-102">Operace ApplyUnitary</span><span class="sxs-lookup"><span data-stu-id="d6bf4-102">ApplyUnitary operation</span></span>

<span data-ttu-id="d6bf4-103">Obor názvů: [Microsoft. Proshrnutí](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d6bf4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d6bf4-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6bf4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6bf4-105">Použije bránu definovanou 2 ^ n × 2 ^ n jednotkovou maticí.</span><span class="sxs-lookup"><span data-stu-id="d6bf4-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="d6bf4-106">Pokud matice není Jednotková nebo má nesprávnou velikost, dojde k chybě.</span><span class="sxs-lookup"><span data-stu-id="d6bf4-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d6bf4-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="d6bf4-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="d6bf4-108">jednotná: [komplexní](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="d6bf4-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="d6bf4-109">2 ^ n × 2 ^ n Jednotková matice popisující operaci.</span><span class="sxs-lookup"><span data-stu-id="d6bf4-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="d6bf4-110">Pokud matice není Jednotková nebo vhodná velikost, vyvolá výjimku.</span><span class="sxs-lookup"><span data-stu-id="d6bf4-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="d6bf4-111">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d6bf4-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d6bf4-112">Qubits, na které se má použít Registry Operations-Registry n.</span><span class="sxs-lookup"><span data-stu-id="d6bf4-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6bf4-113">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6bf4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

