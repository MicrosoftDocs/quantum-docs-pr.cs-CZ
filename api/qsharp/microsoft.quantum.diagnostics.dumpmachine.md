---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853423"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="3c7ac-102">DumpMachine – funkce</span><span class="sxs-lookup"><span data-stu-id="3c7ac-102">DumpMachine function</span></span>

<span data-ttu-id="3c7ac-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3c7ac-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3c7ac-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3c7ac-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3c7ac-105">Vypíše stav aktuálního cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="3c7ac-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="3c7ac-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="3c7ac-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="3c7ac-107">Umístění: t</span><span class="sxs-lookup"><span data-stu-id="3c7ac-107">location : 'T</span></span>

<span data-ttu-id="3c7ac-108">Poskytuje informace o tom, kde se má vygenerovat výpis paměti počítače.</span><span class="sxs-lookup"><span data-stu-id="3c7ac-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c7ac-109">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c7ac-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="3c7ac-110">Žádné</span><span class="sxs-lookup"><span data-stu-id="3c7ac-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3c7ac-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3c7ac-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c7ac-112">'S</span><span class="sxs-lookup"><span data-stu-id="3c7ac-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="3c7ac-113">Poznámky</span><span class="sxs-lookup"><span data-stu-id="3c7ac-113">Remarks</span></span>

<span data-ttu-id="3c7ac-114">Tato metoda umožňuje vypsat informace o aktuálním stavu cílového počítače do souboru nebo jiného umístění.</span><span class="sxs-lookup"><span data-stu-id="3c7ac-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="3c7ac-115">Vlastní vygenerované informace a sémantika `location` jsou specifické pro každý cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="3c7ac-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="3c7ac-116">Poskytnutí prázdné řazené kolekce členů jako umístění ( `()` ) nebo pouhého vynechání `location` parametru obvykle znamená, že výstup bude vygenerován do konzoly.</span><span class="sxs-lookup"><span data-stu-id="3c7ac-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="3c7ac-117">U místních úplných simulátorů distribuovaných jako součást vývojové sady pro plnění stavových prostředí očekává Tato metoda řetězec s cestou k souboru, ve kterém bude zapisovat funkci Wave jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudy pravděpodobnosti měření odpovídajícího stavu.</span><span class="sxs-lookup"><span data-stu-id="3c7ac-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>