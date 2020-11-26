---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Operace ApplyToLittleEndian
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: 1194ac369d2d474330357d26dd22709e9c68dd6e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226481"
---
# <a name="applytolittleendian-operation"></a><span data-ttu-id="be51c-102">Operace ApplyToLittleEndian</span><span class="sxs-lookup"><span data-stu-id="be51c-102">ApplyToLittleEndian operation</span></span>

<span data-ttu-id="be51c-103">Obor názvů: [Microsoft. přípravno. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="be51c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="be51c-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be51c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be51c-105">Aplikuje operaci na základní qubits, která vytváří registr s malým endian.</span><span class="sxs-lookup"><span data-stu-id="be51c-105">Applies an operation to the underlying qubits making up a little-endian register.</span></span> <span data-ttu-id="be51c-106">Tato operace je označená jako interní, protože registr Little-endian má hodnotu neprůhledný, takže se jedná jenom o podrobnosti implementace.</span><span class="sxs-lookup"><span data-stu-id="be51c-106">This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.</span></span>

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="be51c-107">Vstup</span><span class="sxs-lookup"><span data-stu-id="be51c-107">Input</span></span>

### <a name="bareop--qubit--unit--is-adj--ctl"></a><span data-ttu-id="be51c-108">bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [jednotka](xref:microsoft.quantum.lang-ref.unit)  je ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="be51c-108">bareOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="register--littleendian"></a><span data-ttu-id="be51c-109">registrovat: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="be51c-109">register : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="be51c-110">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be51c-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

