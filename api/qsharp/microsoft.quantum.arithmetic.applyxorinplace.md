---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: Operace ApplyXorInPlace
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843476"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="ddd64-102">Operace ApplyXorInPlace</span><span class="sxs-lookup"><span data-stu-id="ddd64-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="ddd64-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ddd64-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ddd64-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddd64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddd64-105">Aplikuje operaci bitové operace-XOR mezi klasickým celým číslem a celým číslem reprezentovaným registrem qubits.</span><span class="sxs-lookup"><span data-stu-id="ddd64-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ddd64-106">Popis</span><span class="sxs-lookup"><span data-stu-id="ddd64-106">Description</span></span>

<span data-ttu-id="ddd64-107">Aplikuje `X` operace na qubits v registru s malým endian na základě 1 bitů v celé číslo.</span><span class="sxs-lookup"><span data-stu-id="ddd64-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="ddd64-108">Poznamenejte si `value` a nechť y unsigned integer kódovaný v a `target` pak `InPlaceXorLE` provede operaci určenou následující mapou: $ \ket{y}\rightarrow \ket{y\oplus a} $, kde $ \oplus $ je BITOVÝ exkluzivní operátor OR.</span><span class="sxs-lookup"><span data-stu-id="ddd64-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="ddd64-109">Vstup</span><span class="sxs-lookup"><span data-stu-id="ddd64-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="ddd64-110">hodnota: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ddd64-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ddd64-111">Celé číslo, které je považováno za nezáporné.</span><span class="sxs-lookup"><span data-stu-id="ddd64-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="ddd64-112">cíl: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ddd64-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ddd64-113">Registr v případě příznaku, který se používá k uložení `value` v kódování Little endian.</span><span class="sxs-lookup"><span data-stu-id="ddd64-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ddd64-114">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddd64-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

