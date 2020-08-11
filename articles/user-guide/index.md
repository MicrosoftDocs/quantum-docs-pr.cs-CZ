---
title: Uživatelská příručka jazyka Q#
description: Přehled účelu a obsahu uživatelské příručky
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fae2949bdcab0c3735b40ef029d70bf7ea3fb9f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869626"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="86077-103">Uživatelská příručka jazyka Q#</span><span class="sxs-lookup"><span data-stu-id="86077-103">The Q# User Guide</span></span>

<span data-ttu-id="86077-104">Vítá vás uživatelská příručka jazyka Q#!</span><span class="sxs-lookup"><span data-stu-id="86077-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="86077-105">V různých tématech této příručky najdete podrobný popis základních konceptů jazyka Q# a všechny informace, které potřebujete k psaní kvantových programů.</span><span class="sxs-lookup"><span data-stu-id="86077-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="86077-106">Obsah uživatelské příručky</span><span class="sxs-lookup"><span data-stu-id="86077-106">User Guide Contents</span></span>

- <span data-ttu-id="86077-107">[Základy Q#](xref:microsoft.quantum.guide.basics): Úvodní přehled účelu a funkcí programovacího jazyka Q#.</span><span class="sxs-lookup"><span data-stu-id="86077-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="86077-108">[Způsoby spuštění programu v Q#Q#](xref:microsoft.quantum.guide.host-programs): Popisuje, jak se spustí program v Q#, a poskytuje přehled různých způsobů volání programu: z příkazového řádku, v aplikacích Jupyter Notebook s podporou Q# nebo z klasického hostitelského programu napsaného v Pythonu nebo v jazyce .NET.</span><span class="sxs-lookup"><span data-stu-id="86077-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is executed, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="no-locq-language"></a><span data-ttu-id="86077-109">Jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="86077-109">Q# Language</span></span>

- <span data-ttu-id="86077-110">[Typy v Q#](xref:microsoft.quantum.guide.types): Vysvětluje model typů v jazyce Q# a popisuje syntaxi pro určování typů a práci s nimi.</span><span class="sxs-lookup"><span data-stu-id="86077-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="86077-111">[Výrazy typu:](xref:microsoft.quantum.guide.expressions) Podrobně popisuje, jak určovat hodnoty jednotlivých typů v jazyce Q#, odkazovat na ně, kombinovat je a pracovat s nimi.</span><span class="sxs-lookup"><span data-stu-id="86077-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-no-locq"></a><span data-ttu-id="86077-112">Používání akce Q#</span><span class="sxs-lookup"><span data-stu-id="86077-112">Using Q#</span></span>

- <span data-ttu-id="86077-113">[Struktura souborů v Q#](xref:microsoft.quantum.guide.filestructure): Popisuje strukturu a syntaxi souboru `*.qs` v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="86077-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="86077-114">[Operace a funkce:](xref:microsoft.quantum.guide.operationsfunctions) Podrobně popisuje dva volatelné typy jazyka Q# – *operace*, které zahrnují akci s qubitovými registry, a *funkce*, které pracují výhradně s klasickými informacemi.</span><span class="sxs-lookup"><span data-stu-id="86077-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="86077-115">Tady uvidíte, jak je definovat a volat, včetně sdružených a řízených verzí kvantových operací.</span><span class="sxs-lookup"><span data-stu-id="86077-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="86077-116">[Proměnné:](xref:microsoft.quantum.guide.variables) Popisuje roli proměnných v programech v jazyce Q# a jejich efektivní využití.</span><span class="sxs-lookup"><span data-stu-id="86077-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="86077-117">Tady najdete například informace o rozsazích vazeb, rozdílech mezi neměnnými a proměnlivými proměnnými a postupu jejich přiřazení nebo změně jejich přiřazení.</span><span class="sxs-lookup"><span data-stu-id="86077-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="86077-118">[Práce s qubity:](xref:microsoft.quantum.guide.qubits) Popisuje funkce jazyka Q# sloužící k adresování jednotlivých qubitů a systémů qubitů, konkrétně jejich přidělování a měření a provádění operací s nimi.</span><span class="sxs-lookup"><span data-stu-id="86077-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="86077-119">[Tok řízení:](xref:microsoft.quantum.guide.controlflow) Podrobně popisuje programovací vzory toku řízení, které jsou k dispozici v jazyce Q# a mezi které patří řada standardních technik (podmíněné spouštění, smyčky for a while atd.) a také vzor Repeat-Until-Success specifický pro kvantové výpočty.</span><span class="sxs-lookup"><span data-stu-id="86077-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional execution, for loops, while loops) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="86077-120">[Testování a ladění:](xref:microsoft.quantum.guide.testingdebugging) Podrobně popisuje některé techniky k zajištění, že váš kód dělá to, co by měl.</span><span class="sxs-lookup"><span data-stu-id="86077-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="86077-121">Z důvodu obecné neprůhlednosti kvantových informací může ladění kvantového programu vyžadovat specializované techniky.</span><span class="sxs-lookup"><span data-stu-id="86077-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="86077-122">Naštěstí jazyk Q# podporuje mnoho technik klasického ladění, na které jsou programátoři zvyklí, a také ty, které jsou specifické pro kvantové výpočty.</span><span class="sxs-lookup"><span data-stu-id="86077-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="86077-123">Patří mezi ně vytváření a spouštění testů jednotek v jazyce Q#, vkládání *kontrolních výrazů* pro hodnoty a pravděpodobnosti do kódu a funkce `Dump`, které vypisují stavy cílových počítačů.</span><span class="sxs-lookup"><span data-stu-id="86077-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="86077-124">Tyto funkce se dají použít společně s naším simulátorem celkového stavu k ladění určitých částí výpočtů obcházením některých kvantových omezení (např. [teorému o nemožnosti klonování](xref:microsoft.quantum.concepts.pauli)).</span><span class="sxs-lookup"><span data-stu-id="86077-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="86077-125">Kvantové simulátory a estimátory prostředků</span><span class="sxs-lookup"><span data-stu-id="86077-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="86077-126">[Kvantové simulátory a hostitelské aplikace:](xref:microsoft.quantum.machines) Přehled různých dostupných simulátorů a také obecného modelu spouštění mezi hostitelským programem a cílovými počítači.</span><span class="sxs-lookup"><span data-stu-id="86077-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general execution model between host programs and target machines.</span></span>

- <span data-ttu-id="86077-127">[Simulátor celkového stavu:](xref:microsoft.quantum.machines.full-state-simulator) Cílový počítač, který simuluje celkový kvantový stav.</span><span class="sxs-lookup"><span data-stu-id="86077-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="86077-128">Tento simulátor je užitečný při úplném spouštění nebo ladění menších programů (méně než pár desítek qubitů).</span><span class="sxs-lookup"><span data-stu-id="86077-128">Useful for fully executing or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="86077-129">[Estimátor prostředků:](xref:microsoft.quantum.machines.resources-estimator) Odhaduje prostředky potřebné ke spuštění konkrétní instance operace Q# na kvantovém počítači.</span><span class="sxs-lookup"><span data-stu-id="86077-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="86077-130">[Simulátor trasování:](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Spouští kvantové programy, aniž by ve skutečnosti simuloval stav kvantového počítače, a díky tomu může spouštět kvantové programy využívající tisíce qubitů.</span><span class="sxs-lookup"><span data-stu-id="86077-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="86077-131">Tento simulátor je užitečný při ladění klasického kódu v rámci kvantového programu a také při odhadu potřebných prostředků.</span><span class="sxs-lookup"><span data-stu-id="86077-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="86077-132">[Simulátor Toffoli:](xref:microsoft.quantum.machines.toffoli-simulator) Kvantový simulátor pro zvláštní účely, který je možné používat s miliony qubitů, ale pouze pro programy s omezenou sadou kvantových operací (konkrétně operací X, CNOT a vícenásobně řízených operací X).</span><span class="sxs-lookup"><span data-stu-id="86077-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="86077-133">Stručné referenční stránky</span><span class="sxs-lookup"><span data-stu-id="86077-133">Quick Reference Pages</span></span>

- <span data-ttu-id="86077-134">[Příkazy magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Stručná referenční stránka pro příkazy magic IQ# v aplikací Jupyter Notebook s podporou Q#.</span><span class="sxs-lookup"><span data-stu-id="86077-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
