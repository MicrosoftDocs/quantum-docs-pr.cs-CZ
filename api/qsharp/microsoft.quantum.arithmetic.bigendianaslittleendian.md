---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 65074b74bcc952efc8b2a9473b2a010bdda42990
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707417"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="9e078-102">BigEndianAsLittleEndian – funkce</span><span class="sxs-lookup"><span data-stu-id="9e078-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="9e078-103">Obor názvů: Microsoft. prostředníky [. aritmetické operace](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9e078-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9e078-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9e078-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9e078-105">Převede `BigEndian` qubit registraci na `LittleEndian` qubit registr vrácením řazení qubit.</span><span class="sxs-lookup"><span data-stu-id="9e078-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="9e078-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="9e078-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="9e078-107">vstup: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="9e078-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="9e078-108">Qubit registr ve `BigEndian` formátu.</span><span class="sxs-lookup"><span data-stu-id="9e078-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="9e078-109">Výstup: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9e078-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9e078-110">Qubit registr ve `LittleEndian` formátu.</span><span class="sxs-lookup"><span data-stu-id="9e078-110">Qubit register in `LittleEndian` format.</span></span>