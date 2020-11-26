---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 3cdcd18f06bf43d109c9f5e69f319f9d33b96bfc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222741"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="db655-102">LittleEndianAsBigEndian – funkce</span><span class="sxs-lookup"><span data-stu-id="db655-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="db655-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="db655-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="db655-104">Balíček: [Microsoft.. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db655-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db655-105">Převede `LittleEndian` qubit registraci na `BigEndian` qubit registr vrácením řazení qubit.</span><span class="sxs-lookup"><span data-stu-id="db655-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="db655-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="db655-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="db655-107">vstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="db655-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="db655-108">Qubit registr ve `LittleEndian` formátu.</span><span class="sxs-lookup"><span data-stu-id="db655-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="db655-109">Výstup: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="db655-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="db655-110">Qubit registr ve `BigEndian` formátu.</span><span class="sxs-lookup"><span data-stu-id="db655-110">Qubit register in `BigEndian` format.</span></span>