---
title: Simulátor Toffolich procesorů – pro vývojová prostředí
description: Přečtěte si o simulátoru Microsoft QDKe Toffoli, ke speciálnímu simulátoru pro každý účel, který je možné použít s miliony qubits.
author: alan-geller
ms.author: ageller
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 036896a33fa02db671a5fd07421160df164bd41d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690783"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="d8a5f-103">Simulátor QDK (Toffoliing Development Kit)</span><span class="sxs-lookup"><span data-stu-id="d8a5f-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="d8a5f-104">Simulátor QDK Toffoli je simulátor pro zvláštní účely s omezeným oborem a podporuje pouze `X` operace, `CNOT` a s více řízenými neřízenými hodnotami `X` .</span><span class="sxs-lookup"><span data-stu-id="d8a5f-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="d8a5f-105">K dispozici je všechny klasické logiky a výpočty.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="d8a5f-106">I když je simulátor Toffoliější s omezenou funkčností než [simulátor úplného stavu](xref:microsoft.quantum.machines.full-state-simulator), je výhodou možnost simulovat mnohem více qubits.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="d8a5f-107">Simulátor Toffoli se dá použít s miliony qubits, zatímco kompletní simulátor stavu je omezený na přibližně 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="d8a5f-108">To je užitečné, například pomocí Oracle pro vyhodnocení logických funkcí – můžou být implementovány pomocí omezené sady podporovaných algoritmů a testovány na velký počet qubits.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="d8a5f-109">Vyvolání simulátoru Toffoli</span><span class="sxs-lookup"><span data-stu-id="d8a5f-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="d8a5f-110">Simulátor Toffoli vystavíte prostřednictvím `ToffoliSimulator` třídy.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="d8a5f-111">Další podrobnosti najdete v tématu [způsoby spuštění Q# programu](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="d8a5f-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="d8a5f-112">Vyvolání simulátoru Toffoli z C #</span><span class="sxs-lookup"><span data-stu-id="d8a5f-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="d8a5f-113">Stejně jako u jiných cílových počítačů nejdřív vytvoříte instanci třídy `ToffoliSimulator` a předáte ji jako první parametr metody `Run` příslušné operace.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="d8a5f-114">Na rozdíl od třídy `QuantumSimulator` ale třída `ToffoliSimulator` neimplementuje rozhraní <xref:System.IDisposable>, a proto ji není nutné uzavírat příkazem `using`.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="d8a5f-115">Vyvolání simulátoru Toffoli z Pythonu</span><span class="sxs-lookup"><span data-stu-id="d8a5f-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="d8a5f-116">Použijte metodu [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) z knihovny Pythonu s importovanou Q# operací:</span><span class="sxs-lookup"><span data-stu-id="d8a5f-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="d8a5f-117">Volání simulátoru Toffoli z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="d8a5f-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="d8a5f-118">Při spuštění Q# programu z příkazového řádku použijte parametr **--simulátor** (nebo **-s** ) k zadání cílového počítače simulátoru Toffoli.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="d8a5f-119">Následující příkaz spustí program pomocí Estimator prostředků:</span><span class="sxs-lookup"><span data-stu-id="d8a5f-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="d8a5f-120">Vyvolání simulátoru Toffoli z notebooků Juptyer</span><span class="sxs-lookup"><span data-stu-id="d8a5f-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="d8a5f-121">Q#Spusťte operaci pomocí příkazu I Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) Q# .</span><span class="sxs-lookup"><span data-stu-id="d8a5f-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="d8a5f-122">Podporované operace</span><span class="sxs-lookup"><span data-stu-id="d8a5f-122">Supported operations</span></span>

<span data-ttu-id="d8a5f-123">Simulátor Toffoli podporuje:</span><span class="sxs-lookup"><span data-stu-id="d8a5f-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="d8a5f-124">Rotace a exponentiated Pauls, například `R` a `Exp` , když se výsledná operace rovná `X` nebo matice identity.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="d8a5f-125">Operace měření a [vyhodnocení](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) , ale pouze v Pauli `Z` .</span><span class="sxs-lookup"><span data-stu-id="d8a5f-125">Measurement and [assert](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="d8a5f-126">Všimněte si, že pravděpodobnost operace měření je vždy **rovna 0** nebo **1** . simulátor Toffoli neobsahuje náhodnost.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-126">Note that a measurement operation's probability is always either **0** or **1** ; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="d8a5f-127">`DumpMachine` a `DumpRegister` funkce.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="d8a5f-128">Obě funkce výstupují aktuální `Z` stav jednotlivých qubit, jeden qubit na řádek.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="d8a5f-129">Určení počtu qubits</span><span class="sxs-lookup"><span data-stu-id="d8a5f-129">Specifying the number of qubits</span></span>

<span data-ttu-id="d8a5f-130">Ve výchozím nastavení `ToffoliSimulator` instance přiděluje prostor pro 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="d8a5f-131">Pokud váš algoritmus vyžaduje více qubits, můžete určit počet qubit zadáním hodnoty `qubitCount` parametru konstruktoru.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="d8a5f-132">Každý další qubit vyžaduje jenom jeden bajt paměti, takže se neúčtují žádné významné náklady na přeodhadování počtu qubits, které budete potřebovat.</span><span class="sxs-lookup"><span data-stu-id="d8a5f-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="d8a5f-133">Příklad:</span><span class="sxs-lookup"><span data-stu-id="d8a5f-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="d8a5f-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="d8a5f-134">See also</span></span>

- [<span data-ttu-id="d8a5f-135">Estimatory prostředků</span><span class="sxs-lookup"><span data-stu-id="d8a5f-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="d8a5f-136">Simulátor trasování doby využití</span><span class="sxs-lookup"><span data-stu-id="d8a5f-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="d8a5f-137">Simulátor plného stavu pro plný stav</span><span class="sxs-lookup"><span data-stu-id="d8a5f-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 