---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 5f5d7dc6e08a13fbdc45f9d11c93c29cfcf90bf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223625"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="3bf00-102">BigEndianAsLittleEndian – funkce</span><span class="sxs-lookup"><span data-stu-id="3bf00-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="3bf00-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3bf00-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3bf00-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bf00-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bf00-105">Převede `BigEndian` qubit registraci na `LittleEndian` qubit registr vrácením řazení qubit.</span><span class="sxs-lookup"><span data-stu-id="3bf00-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="3bf00-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3bf00-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="3bf00-107">vstup: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="3bf00-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="3bf00-108">Qubit registr ve `BigEndian` formátu.</span><span class="sxs-lookup"><span data-stu-id="3bf00-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="3bf00-109">Výstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3bf00-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3bf00-110">Qubit registr ve `LittleEndian` formátu.</span><span class="sxs-lookup"><span data-stu-id="3bf00-110">Qubit register in `LittleEndian` format.</span></span>