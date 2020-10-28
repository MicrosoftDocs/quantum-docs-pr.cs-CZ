---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Operace ApplyToLittleEndian
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: d94a9969a3f827d594946ab8ca6cd4672da7ef7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708697"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="7f193-102">Operace ApplyToLittleEndian</span><span class="sxs-lookup"><span data-stu-id="7f193-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="7f193-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7f193-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7f193-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f193-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f193-105">Aplikuje operaci na základní qubits, která vytváří registr s malým endian.</span><span class="sxs-lookup"><span data-stu-id="7f193-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="7f193-106">Tato operace je označená jako interní, protože registr Little-endian má hodnotu neprůhledný, takže se jedná jenom o podrobnosti implementace.</span><span class="sxs-lookup"><span data-stu-id="7f193-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="7f193-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="7f193-107">Input</span></span>

### <a name="bareop--qubit--unit-adj--ctl"></a><span data-ttu-id="7f193-108">bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="7f193-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="7f193-109">registrovat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7f193-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="7f193-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f193-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

