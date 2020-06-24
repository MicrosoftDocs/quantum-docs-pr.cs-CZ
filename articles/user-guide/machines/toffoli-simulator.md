---
title: Simulátor Toffoli pro vývoj pro všechna ta
description: Přečtěte si o simulátoru Microsoft QDKe Toffoli, ke speciálnímu simulátoru pro každý účel, který je možné použít s miliony qubits.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274681"
---
# <a name="quantum-development-kit-toffoli-simulator"></a><span data-ttu-id="25202-103">Simulátor Toffoli pro vývoj pro všechna ta</span><span class="sxs-lookup"><span data-stu-id="25202-103">Quantum Development Kit Toffoli Simulator</span></span>

<span data-ttu-id="25202-104">Vývojová sada pro všechna provozní prostředí poskytuje simulátor Toffoli, což je simulátor pro zvláštní účely, který může simulovat algoritmy pro procesory, které jsou omezené na X, CNOT a s více řízenými operacemi X, a to znamená, že jsou k dispozici všechny klasické logiky a výpočty.</span><span class="sxs-lookup"><span data-stu-id="25202-104">The Quantum Development Kit provides a Toffoli simulator, which is a special-purpose simulator that can simulate quantum algorithms that are limited to X, CNOT, and multi-controlled X quantum operations (all classical logic and computations are available).</span></span>

<span data-ttu-id="25202-105">I když je simulátor Toffoli mnohem větší omezení operace, než je [úplný stav simulátoru](xref:microsoft.quantum.machines.full-state-simulator), může simulovat mnohem více qubits.</span><span class="sxs-lookup"><span data-stu-id="25202-105">While the Toffoli simulator is much more restricted in operation than the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), it can simulate far more qubits.</span></span>
<span data-ttu-id="25202-106">Simulátor Toffoli se dá použít s miliony qubits, zatímco úplný stav simulátoru se obecně omezí na přibližně 30.</span><span class="sxs-lookup"><span data-stu-id="25202-106">The Toffoli simulator can be used with millions of qubits, while the full state simulator is generally limited to about 30.</span></span>
<span data-ttu-id="25202-107">Může spouštět a ladit omezené sady algoritmů pro plnění, které jsou napsané v Q # ve vašem počítači. například Oracle pro vyhodnocení logických funkcí lze implementovat pomocí těchto bran a tak testovat v různých velkých číslech qubits pomocí tohoto simulátoru.</span><span class="sxs-lookup"><span data-stu-id="25202-107">It can execute and debug a limited set of quantum algorithms written in Q# on your computer; for instance, oracles that evaluate Boolean functions can be implemented using these gates and so tested on vary large numbers of qubits using this simulator.</span></span>

<span data-ttu-id="25202-108">Tento simulátor při přístavování se zveřejňuje prostřednictvím `ToffoliSimulator` třídy.</span><span class="sxs-lookup"><span data-stu-id="25202-108">This quantum simulator is exposed via the `ToffoliSimulator` class.</span></span>
<span data-ttu-id="25202-109">Chcete-li použít simulátor, jednoduše vytvořte instanci této třídy a předejte ji `Run` metodě operace, kterou chcete provést, spolu se zbytkem parametrů:</span><span class="sxs-lookup"><span data-stu-id="25202-109">To use the simulator, simply create an instance of this class and pass it to the `Run` method of the quantum operation you want to execute along with the rest of the parameters:</span></span>

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a><span data-ttu-id="25202-110">Jiné operace</span><span class="sxs-lookup"><span data-stu-id="25202-110">Other Operations</span></span>

<span data-ttu-id="25202-111">`ToffoliSimulator`Podporuje rotace a Exponentiated Pauls, například `R` a `Exp` , pokud se výsledná operace rovná `X` nebo k identitě.</span><span class="sxs-lookup"><span data-stu-id="25202-111">The `ToffoliSimulator` supports rotations and exponentiated Paulis, such as `R` and `Exp`, when the resulting operation is equal to `X` or to the identity.</span></span>

<span data-ttu-id="25202-112">Měření a vyhodnocení jsou podporovány, ale pouze v Pauli `Z` .</span><span class="sxs-lookup"><span data-stu-id="25202-112">Measurement and assert are supported, but only in the Pauli `Z` basis.</span></span>
<span data-ttu-id="25202-113">Všimněte si, že pravděpodobnost některých měření je vždy rovna 0 nebo 1. simulátor Toffoli neobsahuje náhodnost.</span><span class="sxs-lookup"><span data-stu-id="25202-113">Note that the probability of some measurement is always either 0 or 1; there is no randomness in the Toffoli simulator.</span></span>

<span data-ttu-id="25202-114">`DumpMachine`a `DumpRegister` jsou podporované.</span><span class="sxs-lookup"><span data-stu-id="25202-114">`DumpMachine` and `DumpRegister` are supported.</span></span>
<span data-ttu-id="25202-115">Nastavují výstup na `Z` základě aktuálního stavu každého qubit, jeden qubit na řádek.</span><span class="sxs-lookup"><span data-stu-id="25202-115">They both output the current `Z`-basis state of each qubit, one qubit per line.</span></span>

## <a name="qubitcount"></a><span data-ttu-id="25202-116">QubitCount</span><span class="sxs-lookup"><span data-stu-id="25202-116">QubitCount</span></span>

<span data-ttu-id="25202-117">Ve výchozím nastavení `ToffoliSimulator` přiděluje prostor pro 65 536 qubits.</span><span class="sxs-lookup"><span data-stu-id="25202-117">By default, the `ToffoliSimulator` allocates space for 65,536 qubits.</span></span>
<span data-ttu-id="25202-118">Pokud váš algoritmus vyžaduje více než toto, můžete změnit počet qubit zadáním hodnoty `qubitCount` parametru konstruktoru.</span><span class="sxs-lookup"><span data-stu-id="25202-118">If your algorithm requires more than this, you can change the qubit count by providing a value for the `qubitCount` parameter to the constructor.</span></span>
<span data-ttu-id="25202-119">Každý další qubit vyžaduje další bajt paměti, takže se neúčtují žádné významné náklady na přeodhad počtu qubits, které budete potřebovat.</span><span class="sxs-lookup"><span data-stu-id="25202-119">Each additional qubit requires an additional byte of memory, so there is no significant cost to overestimating the number of qubits you'll need.</span></span>

<span data-ttu-id="25202-120">Příklad:</span><span class="sxs-lookup"><span data-stu-id="25202-120">For example:</span></span>

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
