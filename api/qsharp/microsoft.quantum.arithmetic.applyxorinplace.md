---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operace ApplyXorInPlace
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210106"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="511aa-102">Operace ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="511aa-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="511aa-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="511aa-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="511aa-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="511aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="511aa-105">Aplikuje operaci bitové operace-XOR mezi klasickým celým číslem a celým číslem reprezentovaným registrem qubits.</span><span class="sxs-lookup"><span data-stu-id="511aa-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="511aa-106">Popis</span><span class="sxs-lookup"><span data-stu-id="511aa-106">Description</span></span>

<span data-ttu-id="511aa-107">Aplikuje `X` operace na qubits v registru s malým endian na základě 1 bitů v celé číslo.</span><span class="sxs-lookup"><span data-stu-id="511aa-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="511aa-108">Poznamenejte si `value` a nechť y unsigned integer kódovaný v a `target` pak `InPlaceXorLE` provede operaci určenou následující mapou: $ \ket{y}\rightarrow \ket{y\oplus a} $, kde $ \oplus $ je BITOVÝ exkluzivní operátor OR.</span><span class="sxs-lookup"><span data-stu-id="511aa-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="511aa-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="511aa-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="511aa-110">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="511aa-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="511aa-111">Celé číslo, které je považováno za nezáporné.</span><span class="sxs-lookup"><span data-stu-id="511aa-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="511aa-112">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="511aa-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="511aa-113">Registr v případě příznaku, který se používá k uložení `value` v kódování Little endian.</span><span class="sxs-lookup"><span data-stu-id="511aa-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="511aa-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="511aa-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

