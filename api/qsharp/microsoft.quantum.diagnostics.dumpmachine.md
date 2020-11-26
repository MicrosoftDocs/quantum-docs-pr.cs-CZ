---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine – funkce
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: e7eb2dfce060b61e27deae31e3c1fc6dc3d7655c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202103"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="67a58-102">DumpMachine – funkce</span><span class="sxs-lookup"><span data-stu-id="67a58-102">DumpMachine function</span></span>

<span data-ttu-id="67a58-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="67a58-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="67a58-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="67a58-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="67a58-105">Vypíše stav aktuálního cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="67a58-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="67a58-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="67a58-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="67a58-107">Umístění: t</span><span class="sxs-lookup"><span data-stu-id="67a58-107">location : 'T</span></span>

<span data-ttu-id="67a58-108">Poskytuje informace o tom, kde se má vygenerovat výpis paměti počítače.</span><span class="sxs-lookup"><span data-stu-id="67a58-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67a58-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67a58-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="67a58-110">Žádné</span><span class="sxs-lookup"><span data-stu-id="67a58-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="67a58-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="67a58-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="67a58-112">'S</span><span class="sxs-lookup"><span data-stu-id="67a58-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="67a58-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="67a58-113">Remarks</span></span>

<span data-ttu-id="67a58-114">Tato metoda umožňuje vypsat informace o aktuálním stavu cílového počítače do souboru nebo jiného umístění.</span><span class="sxs-lookup"><span data-stu-id="67a58-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="67a58-115">Vlastní vygenerované informace a sémantika `location` jsou specifické pro každý cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="67a58-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="67a58-116">Poskytnutí prázdné řazené kolekce členů jako umístění ( `()` ) nebo pouhého vynechání `location` parametru obvykle znamená, že výstup bude vygenerován do konzoly.</span><span class="sxs-lookup"><span data-stu-id="67a58-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="67a58-117">U místních úplných simulátorů distribuovaných jako součást vývojové sady pro plnění stavových prostředí očekává Tato metoda řetězec s cestou k souboru, ve kterém bude zapisovat funkci Wave jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudy pravděpodobnosti měření odpovídajícího stavu.</span><span class="sxs-lookup"><span data-stu-id="67a58-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>