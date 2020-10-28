---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 8c2e6150a839bb0cd4c311c821b78a080288cd22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707209"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="ae704-102">LittleEndianAsBigEndian – funkce</span><span class="sxs-lookup"><span data-stu-id="ae704-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="ae704-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ae704-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ae704-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae704-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae704-105">Převede `LittleEndian` qubit registraci na `BigEndian` qubit registr vrácením řazení qubit.</span><span class="sxs-lookup"><span data-stu-id="ae704-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="ae704-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="ae704-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="ae704-107">vstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ae704-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ae704-108">Qubit registr ve `LittleEndian` formátu.</span><span class="sxs-lookup"><span data-stu-id="ae704-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="ae704-109">Výstup: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="ae704-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="ae704-110">Qubit registr ve `BigEndian` formátu.</span><span class="sxs-lookup"><span data-stu-id="ae704-110">Qubit register in `BigEndian` format.</span></span>