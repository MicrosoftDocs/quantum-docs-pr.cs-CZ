---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine – funkce
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92698124"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="d45e2-102">DumpMachine – funkce</span><span class="sxs-lookup"><span data-stu-id="d45e2-102">DumpMachine function</span></span>

<span data-ttu-id="d45e2-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d45e2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d45e2-104">Balíček [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d45e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d45e2-105">Vypíše stav aktuálního cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="d45e2-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="d45e2-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="d45e2-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="d45e2-107">Umístění: t</span><span class="sxs-lookup"><span data-stu-id="d45e2-107">location : 'T</span></span>

<span data-ttu-id="d45e2-108">Poskytuje informace o tom, kde se má vygenerovat výpis paměti počítače.</span><span class="sxs-lookup"><span data-stu-id="d45e2-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d45e2-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d45e2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="d45e2-110">Žádné</span><span class="sxs-lookup"><span data-stu-id="d45e2-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d45e2-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d45e2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d45e2-112">'S</span><span class="sxs-lookup"><span data-stu-id="d45e2-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d45e2-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="d45e2-113">Remarks</span></span>

<span data-ttu-id="d45e2-114">Tato metoda umožňuje vypsat informace o aktuálním stavu cílového počítače do souboru nebo jiného umístění.</span><span class="sxs-lookup"><span data-stu-id="d45e2-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="d45e2-115">Vlastní vygenerované informace a sémantika `location` jsou specifické pro každý cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="d45e2-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="d45e2-116">Poskytnutí prázdné řazené kolekce členů jako umístění ( `()` ) nebo pouhého vynechání `location` parametru obvykle znamená, že výstup bude vygenerován do konzoly.</span><span class="sxs-lookup"><span data-stu-id="d45e2-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="d45e2-117">U místních úplných simulátorů distribuovaných jako součást vývojové sady pro plnění stavových prostředí očekává Tato metoda řetězec s cestou k souboru, ve kterém bude zapisovat funkci Wave jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudy pravděpodobnosti měření odpovídajícího stavu.</span><span class="sxs-lookup"><span data-stu-id="d45e2-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>