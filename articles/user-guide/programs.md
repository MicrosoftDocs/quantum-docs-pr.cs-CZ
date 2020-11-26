---
title: 'Q # Introdution'
description: 'Rychlé představení programů v programu Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233484"
---
# <a name="q-quantum-programming-language"></a><span data-ttu-id="e3943-103">Q # programový jazyk</span><span class="sxs-lookup"><span data-stu-id="e3943-103">Q# Quantum Programming Language</span></span>

<span data-ttu-id="e3943-104">Vše, co potřebujete znát o programovacím jazyce Q #, je podrobně popsané v [Průvodci jazyk q #](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="e3943-104">Everything you need to know about the Q# programming language is detailed in the [Q# language guide](xref:microsoft.quantum.qsharp.index).</span></span> <span data-ttu-id="e3943-105">Stejně jako cokoli ostatní, je náš [proces návrhu](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) v našem jazyce open source a Vítejte na příspěvcích.</span><span class="sxs-lookup"><span data-stu-id="e3943-105">Like anything else, our [language design process](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) is open source and we welcome contributions.</span></span>
<span data-ttu-id="e3943-106">Další informace o základech a motivaci za Q # najdete v tématu [Proč musíme q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="e3943-106">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>  
<span data-ttu-id="e3943-107">Q # se dodává jako součást QDK (pro vývoj na více instancí), kde najdete rychlý přehled, [co je to QDK?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="e3943-107">Q# is shipped as part of the Quantum Development Kit (QDK) For a quick overview, check out [What is the QDK?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="e3943-108">Co je program pro vydaných hodnot?</span><span class="sxs-lookup"><span data-stu-id="e3943-108">What is a quantum program?</span></span>

<span data-ttu-id="e3943-109">Program pro práci s více částmi se může zobrazit jako konkrétní sada klasických podprocesů, které při volání provádějí výpočet prostřednictvím práce se systémem program napsaný v Q # nemodeluje přímo stav nečinnosti, ale místo toho popisuje, jak počítač klasického ovládacího prvku komunikuje s qubits.</span><span class="sxs-lookup"><span data-stu-id="e3943-109">A quantum program can be seen as a particular set of classical subroutines which, when called, perform a computation by interacting with a quantum system; a program written in Q# does not directly model the quantum state, but rather describes how a classical control computer interacts with qubits.</span></span>
<span data-ttu-id="e3943-110">To nám umožní zcela nezávislá informace o tom, co *je* stav bez nároku na každém cílovém počítači, což může mít různé interpretace v závislosti na počítači.</span><span class="sxs-lookup"><span data-stu-id="e3943-110">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="e3943-111">Důležité je, že Q # nemá možnost introspect se do stavu qubit nebo jiných vlastností příslušnosti, což zaručuje, že program Q # může být fyzicky spuštěný v počítači s taktem.</span><span class="sxs-lookup"><span data-stu-id="e3943-111">An important consequence of that is that Q# has no ability to introspect into the state of a qubit or other properties of quantum mechanics directly, which guarantees that a Q# program can be physically executed on a quantum computer.</span></span>
<span data-ttu-id="e3943-112">Místo toho může program volat operace, jako je například [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) extrakce klasických informací z qubit.</span><span class="sxs-lookup"><span data-stu-id="e3943-112">Instead, a program can call operations such as [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) to extract classical information from a qubit.</span></span>

<span data-ttu-id="e3943-113">Po přidělení může být qubit předán operacím a funkcím, které jsou také označovány jako *volatelné*.</span><span class="sxs-lookup"><span data-stu-id="e3943-113">Once allocated, a qubit can be passed to operations and functions, also referred to as *callables*.</span></span> <span data-ttu-id="e3943-114">V některých případech to znamená, že program Q # může s qubit provádět. Všechny přímé akce ve stavu qubit jsou definovány *vnitřními* voláními, jako jsou například [`X`](xref:Microsoft.Quantum.Intrinsic.X) a [`H`](xref:Microsoft.Quantum.Intrinsic.H) – tj. volat, jejichž implementace nejsou definovány v rámci Q #, ale místo toho jsou definovány cílovým počítačem.</span><span class="sxs-lookup"><span data-stu-id="e3943-114">In some sense, this is all that a Q# program can do with a qubit; Any direct actions on state of a qubit are all defined by *intrinsic* callables such as [`X`](xref:Microsoft.Quantum.Intrinsic.X) and [`H`](xref:Microsoft.Quantum.Intrinsic.H) - i.e. callables whose implementations are not defined within Q# but are instead defined by the target machine.</span></span> <span data-ttu-id="e3943-115">Díky *tomu* se tyto operace skutečně provádějí jenom v cílovém počítači, který používáme ke spuštění konkrétního programu Q #.</span><span class="sxs-lookup"><span data-stu-id="e3943-115">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>

<span data-ttu-id="e3943-116">Pokud například spustíte program na našem simulátoru, simulátor provede odpovídající matematické operace do simulovaného systému pro [nastavování](xref:microsoft.quantum.machines.full-state-simulator).</span><span class="sxs-lookup"><span data-stu-id="e3943-116">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="e3943-117">Ale pokud je cílový počítač skutečným počítačem, který se blíží k budoucnosti, volání takových operací v Q # nasměruje počítač s příznakem do provozu, aby provedl odpovídající *reálné* operace v *reálném* systému doby provozu (například přesně časované laserové Pulse).</span><span class="sxs-lookup"><span data-stu-id="e3943-117">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="e3943-118">Program Q # znovu sloučí tyto operace, jak jsou definovány cílovým počítačem, a vytvoří tak nové operace vyšší úrovně, které budou vyjadřovat výpočetní procesory.</span><span class="sxs-lookup"><span data-stu-id="e3943-118">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="e3943-119">V tomto případě Q # usnadňuje vyjádření logiky podkladových a hybridních životních stojí – klasických algoritmů, a to i v souvislosti se strukturou cílového počítače nebo simulátoru.</span><span class="sxs-lookup"><span data-stu-id="e3943-119">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

<span data-ttu-id="e3943-120">Jednoduchým příkladem je následující program, který přiděluje jeden qubit ve stavu $ \ket {0} $, pak na něj použije operaci Hadamard `H` a měří výsledek na `PauliZ` základě.</span><span class="sxs-lookup"><span data-stu-id="e3943-120">A simple example is the following program, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

<span data-ttu-id="e3943-121">Naše hlavní množství [katas](https://github.com/microsoft/QuantumKatas#introduction) poskytují dobrý úvod k [výpočetním koncepcím](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , jako jsou běžné operace s více operačními systémy a způsobu manipulace s qubits.</span><span class="sxs-lookup"><span data-stu-id="e3943-121">Our [Quantum Katas](https://github.com/microsoft/QuantumKatas#introduction) give a good introduction on [Quantum Computing Concepts](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) such as common quantum operations and how to manipulate qubits.</span></span> <span data-ttu-id="e3943-122">Další příklady najdete také v [vnitřních operacích a funkcích](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="e3943-122">More examples can also be found in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span>



