---
title: Simulátor Toffolich procesorů – pro vývojová prostředí
description: Přečtěte si o simulátoru Microsoft QDKe Toffoli, ke speciálnímu simulátoru pro každý účel, který je možné použít s miliony qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: a6ceee592e628215511ec83475d9e25bf54674f7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870613"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a><span data-ttu-id="62524-103">Simulátor QDK (Toffoliing Development Kit)</span><span class="sxs-lookup"><span data-stu-id="62524-103">Quantum Development Kit (QDK) Toffoli simulator</span></span>

<span data-ttu-id="62524-104">Simulátor QDK Toffoli je simulátor pro zvláštní účely s omezeným oborem a podporuje pouze `X` operace, `CNOT` a s více řízenými neřízenými hodnotami `X` .</span><span class="sxs-lookup"><span data-stu-id="62524-104">The QDK Toffoli simulator is a special-purpose simulator with a limited scope and only supports `X`, `CNOT`, and multi-controlled `X` quantum operations.</span></span> <span data-ttu-id="62524-105">K dispozici je všechny klasické logiky a výpočty.</span><span class="sxs-lookup"><span data-stu-id="62524-105">All classical logic and computations are available.</span></span>

<span data-ttu-id="62524-106">I když je simulátor Toffoliější s omezenou funkčností než [simulátor úplného stavu](xref:microsoft.quantum.machines.full-state-simulator), je výhodou možnost simulovat mnohem více qubits.</span><span class="sxs-lookup"><span data-stu-id="62524-106">While the Toffoli simulator is more restricted in functionality than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it has the advantage of being able to simulate far more qubits.</span></span> <span data-ttu-id="62524-107">Simulátor Toffoli se dá použít s miliony qubits, zatímco kompletní simulátor stavu je omezený na přibližně 30 qubits.</span><span class="sxs-lookup"><span data-stu-id="62524-107">The Toffoli simulator can be used with millions of qubits, while the full state simulator is limited to about 30 qubits.</span></span> <span data-ttu-id="62524-108">To je užitečné, například pomocí Oracle pro vyhodnocení logických funkcí – můžou být implementovány pomocí omezené sady podporovaných algoritmů a testovány na velký počet qubits.</span><span class="sxs-lookup"><span data-stu-id="62524-108">This is useful, for example, with oracles that evaluate Boolean functions - they can be implemented using the limited set of supported algorithms and tested on a large number of qubits.</span></span>

## <a name="invoking-the-toffoli-simulator"></a><span data-ttu-id="62524-109">Vyvolání simulátoru Toffoli</span><span class="sxs-lookup"><span data-stu-id="62524-109">Invoking the Toffoli simulator</span></span>

<span data-ttu-id="62524-110">Simulátor Toffoli vystavíte prostřednictvím `ToffoliSimulator` třídy.</span><span class="sxs-lookup"><span data-stu-id="62524-110">You expose the Toffoli simulator via the `ToffoliSimulator` class.</span></span> <span data-ttu-id="62524-111">Další podrobnosti najdete v tématu [způsoby spuštění programu Q #](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="62524-111">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-toffoli-simulator-from-c"></a><span data-ttu-id="62524-112">Vyvolání simulátoru Toffoli z C #</span><span class="sxs-lookup"><span data-stu-id="62524-112">Invoking the Toffoli simulator from C#</span></span>

<span data-ttu-id="62524-113">Stejně jako u jiných cílových počítačů nejprve vytvoříte instanci `ToffoliSimulator` třídy a pak ji předáte jako první parametr `Run` metody operace.</span><span class="sxs-lookup"><span data-stu-id="62524-113">As with other target machines, you first create an instance of the `ToffoliSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="62524-114">Všimněte si, že na rozdíl od `QuantumSimulator` třídy `ToffoliSimulator` třída neimplementuje <xref:System.IDisposable> rozhraní, takže je nemusíte v rámci `using` příkazu uzavřít.</span><span class="sxs-lookup"><span data-stu-id="62524-114">Note that, unlike the `QuantumSimulator` class, the `ToffoliSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a><span data-ttu-id="62524-115">Vyvolání simulátoru Toffoli z Pythonu</span><span class="sxs-lookup"><span data-stu-id="62524-115">Invoking the Toffoli simulator from Python</span></span>

<span data-ttu-id="62524-116">Použijte metodu [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) z knihovny Pythonu s importovanou operací Q #:</span><span class="sxs-lookup"><span data-stu-id="62524-116">Use the [toffoli_simulate()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a><span data-ttu-id="62524-117">Volání simulátoru Toffoli z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="62524-117">Invoking the Toffoli simulator from the command line</span></span>

<span data-ttu-id="62524-118">Při spuštění programu Q # z příkazového řádku použijte parametr **--simulátor** (nebo **-s** ) k zadání cílového počítače simulátoru Toffoli.</span><span class="sxs-lookup"><span data-stu-id="62524-118">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the Toffoli simulator target machine.</span></span> <span data-ttu-id="62524-119">Následující příkaz spustí program pomocí Estimator prostředků:</span><span class="sxs-lookup"><span data-stu-id="62524-119">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a><span data-ttu-id="62524-120">Vyvolání simulátoru Toffoli z notebooků Juptyer</span><span class="sxs-lookup"><span data-stu-id="62524-120">Invoking the Toffoli simulator from Juptyer Notebooks</span></span>

<span data-ttu-id="62524-121">Pomocí příkazu SWEETIQ # Magic [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) spusťte operaci Q #.</span><span class="sxs-lookup"><span data-stu-id="62524-121">Use the IQ# magic command [%toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) to run the Q# operation.</span></span>

```
%toffoli myOperation
```

## <a name="supported-operations"></a><span data-ttu-id="62524-122">Podporované operace</span><span class="sxs-lookup"><span data-stu-id="62524-122">Supported operations</span></span>

<span data-ttu-id="62524-123">Simulátor Toffoli podporuje:</span><span class="sxs-lookup"><span data-stu-id="62524-123">The Toffoli simulator supports:</span></span>

* <span data-ttu-id="62524-124">Rotace a exponentiated Pauls, například `R` a `Exp` , když se výsledná operace rovná `X` nebo matice identity.</span><span class="sxs-lookup"><span data-stu-id="62524-124">Rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation equals `X` or the identity matrix.</span></span>
* <span data-ttu-id="62524-125">Operace měření a [vyhodnocení](xref:microsoft.quantum.diagnostics.assertmeasurement) , ale pouze v Pauli `Z` .</span><span class="sxs-lookup"><span data-stu-id="62524-125">Measurement and [assert](xref:microsoft.quantum.diagnostics.assertmeasurement) operations, but only in the Pauli `Z` basis.</span></span> <span data-ttu-id="62524-126">Všimněte si, že pravděpodobnost operace měření je vždy **rovna 0** nebo **1**. simulátor Toffoli neobsahuje náhodnost.</span><span class="sxs-lookup"><span data-stu-id="62524-126">Note that a measurement operation's probability is always either **0** or **1**; there is no randomness in the Toffoli simulator.</span></span>
* <span data-ttu-id="62524-127">`DumpMachine`a `DumpRegister` funkce.</span><span class="sxs-lookup"><span data-stu-id="62524-127">`DumpMachine` and `DumpRegister` functions.</span></span>
<span data-ttu-id="62524-128">Obě funkce výstupují aktuální `Z` stav jednotlivých qubit, jeden qubit na řádek.</span><span class="sxs-lookup"><span data-stu-id="62524-128">Both functions output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="specifying-the-number-of-qubits"></a><span data-ttu-id="62524-129">Určení počtu qubits</span><span class="sxs-lookup"><span data-stu-id="62524-129">Specifying the number of qubits</span></span>

<span data-ttu-id="62524-130">Ve výchozím nastavení `ToffoliSimulator` instance přiděluje prostor pro 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="62524-130">By default, a `ToffoliSimulator` instance allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="62524-131">Pokud váš algoritmus vyžaduje více qubits, můžete určit počet qubit zadáním hodnoty `qubitCount` parametru konstruktoru.</span><span class="sxs-lookup"><span data-stu-id="62524-131">If your algorithm requires more qubits than this, you can specify the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="62524-132">Každý další qubit vyžaduje jenom jeden bajt paměti, takže se neúčtují žádné významné náklady na přeodhadování počtu qubits, které budete potřebovat.</span><span class="sxs-lookup"><span data-stu-id="62524-132">Each additional qubit requires only one byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="62524-133">Příklad:</span><span class="sxs-lookup"><span data-stu-id="62524-133">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a><span data-ttu-id="62524-134">Viz také</span><span class="sxs-lookup"><span data-stu-id="62524-134">See also</span></span>

- [<span data-ttu-id="62524-135">Estimatory prostředků</span><span class="sxs-lookup"><span data-stu-id="62524-135">Quantum Resources Estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="62524-136">Simulátor trasování doby využití</span><span class="sxs-lookup"><span data-stu-id="62524-136">Quantum Trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="62524-137">Simulátor plného stavu pro plný stav</span><span class="sxs-lookup"><span data-stu-id="62524-137">Quantum Full State simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 