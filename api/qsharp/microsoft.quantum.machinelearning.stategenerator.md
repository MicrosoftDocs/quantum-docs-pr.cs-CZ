---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Uživatelem definovaný typ StateGenerator
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707965"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="56538-102">Uživatelem definovaný typ StateGenerator</span><span class="sxs-lookup"><span data-stu-id="56538-102">StateGenerator user defined type</span></span>

<span data-ttu-id="56538-103">Obor názvů: [Microsoft. MachineLearning.](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="56538-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="56538-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56538-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56538-105">Popisuje operaci, která připraví daný vstup na sekvenční třídění.</span><span class="sxs-lookup"><span data-stu-id="56538-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="56538-106">Pojmenované položky</span><span class="sxs-lookup"><span data-stu-id="56538-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="56538-107">NQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="56538-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="56538-108">Počet qubits, na kterých je definován kódovaný vstup.</span><span class="sxs-lookup"><span data-stu-id="56538-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="56538-109">Příprava: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [jednotky](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="56538-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="56538-110">Operace, která připraví kódovaný vstup v registru s malým počtem endian `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="56538-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>