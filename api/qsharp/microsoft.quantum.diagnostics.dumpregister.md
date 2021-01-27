---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister – funkce
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829233"
---
# <a name="dumpregister-function"></a><span data-ttu-id="2ed1a-102">DumpRegister – funkce</span><span class="sxs-lookup"><span data-stu-id="2ed1a-102">DumpRegister function</span></span>

<span data-ttu-id="2ed1a-103">Obor názvů: [Microsoft. prověří. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2ed1a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2ed1a-104">Balíček: [Microsoft. ProQSharpme. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2ed1a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2ed1a-105">Vypíše stav aktuálního cílového počítače přidružený k danému qubits.</span><span class="sxs-lookup"><span data-stu-id="2ed1a-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2ed1a-106">Vstup</span><span class="sxs-lookup"><span data-stu-id="2ed1a-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="2ed1a-107">Umístění: t</span><span class="sxs-lookup"><span data-stu-id="2ed1a-107">location : 'T</span></span>

<span data-ttu-id="2ed1a-108">Poskytuje informace o tom, kde vygeneruje výpis stavu.</span><span class="sxs-lookup"><span data-stu-id="2ed1a-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2ed1a-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2ed1a-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2ed1a-110">Seznam qubitsů, které se mají ohlásit</span><span class="sxs-lookup"><span data-stu-id="2ed1a-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ed1a-111">Výstup: [jednotka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ed1a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="2ed1a-112">Žádné</span><span class="sxs-lookup"><span data-stu-id="2ed1a-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2ed1a-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2ed1a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2ed1a-114">'S</span><span class="sxs-lookup"><span data-stu-id="2ed1a-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2ed1a-115">Poznámky</span><span class="sxs-lookup"><span data-stu-id="2ed1a-115">Remarks</span></span>

<span data-ttu-id="2ed1a-116">Tato metoda umožňuje vypsat informace přidružené ke stavu daného qubits do souboru nebo do jiného umístění.</span><span class="sxs-lookup"><span data-stu-id="2ed1a-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="2ed1a-117">Vlastní vygenerované informace a sémantika `location` jsou specifické pro každý cílový počítač.</span><span class="sxs-lookup"><span data-stu-id="2ed1a-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="2ed1a-118">Poskytnutí prázdné řazené kolekce členů jako umístění ( `()` ) však obvykle znamená, že výstup bude vygenerován do konzoly.</span><span class="sxs-lookup"><span data-stu-id="2ed1a-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="2ed1a-119">U místních úplných simulátorů distribuovaných jako součást vývojové sady pro plnění stavových prostředí očekává Tato metoda řetězec s cestou k souboru, ve kterém bude zapisovat stav daného qubits (tj. funkce Wave odpovídajícího subsystému) jako jednorozměrné pole komplexních čísel, kde každý prvek představuje amplitudy pravděpodobnosti měření odpovídajícího stavu.</span><span class="sxs-lookup"><span data-stu-id="2ed1a-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="2ed1a-120">Pokud jsou zadané qubits entangled s jinými qubit a jejich stav nelze oddělit, pouze hlásí, že qubits je entangled.</span><span class="sxs-lookup"><span data-stu-id="2ed1a-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>