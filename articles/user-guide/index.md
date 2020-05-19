---
title: Uživatelská příručka Q#
description: Přehled účelu a obsahu uživatelské příručky
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430607"
---
# <a name="the-q-user-guide"></a><span data-ttu-id="9a466-103">Uživatelská příručka Q#</span><span class="sxs-lookup"><span data-stu-id="9a466-103">The Q# User Guide</span></span>

<span data-ttu-id="9a466-104">Vítá vás uživatelská příručka Q#!</span><span class="sxs-lookup"><span data-stu-id="9a466-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="9a466-105">Tady najdete podrobný popis základních konceptů jazyka Q# a všechny informace, které potřebujete k psaní kvantových programů.</span><span class="sxs-lookup"><span data-stu-id="9a466-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="9a466-106">Obsah uživatelské příručky</span><span class="sxs-lookup"><span data-stu-id="9a466-106">User Guide Contents</span></span>

- <span data-ttu-id="9a466-107">[Základy jazyka Q#:](xref:microsoft.quantum.guide.basics) Úvodní přehled účelu a funkcí programovacího jazyka Q#.</span><span class="sxs-lookup"><span data-stu-id="9a466-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="9a466-108">Jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="9a466-108">Q# Language</span></span>

- <span data-ttu-id="9a466-109">[Typy v jazyce Q#:](xref:microsoft.quantum.guide.types) Vysvětluje model typů v jazyce Q# a popisuje syntaxi pro určování typů a práci s nimi.</span><span class="sxs-lookup"><span data-stu-id="9a466-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="9a466-110">[Výrazy typu:](xref:microsoft.quantum.guide.expressions) Podrobně popisuje, jak určovat hodnoty jednotlivých typů v jazyce Q#, odkazovat na ně, kombinovat je a pracovat s nimi.</span><span class="sxs-lookup"><span data-stu-id="9a466-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="9a466-111">Použití Q#</span><span class="sxs-lookup"><span data-stu-id="9a466-111">Using Q#</span></span>

- <span data-ttu-id="9a466-112">[Struktura souborů Q#:](xref:microsoft.quantum.guide.filestructure) Popisuje strukturu a syntaxi souboru Q# `*.qs`.</span><span class="sxs-lookup"><span data-stu-id="9a466-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="9a466-113">[Operace a funkce:](xref:microsoft.quantum.guide.operationsfunctions) Podrobně popisuje dva volatelné typy jazyka Q# – *operace*, které zahrnují akci s qubitovými registry, a *funkce*, které pracují výhradně s klasickými informacemi.</span><span class="sxs-lookup"><span data-stu-id="9a466-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="9a466-114">Tady uvidíte, jak je definovat a volat, včetně sdružených a řízených verzí kvantových operací.</span><span class="sxs-lookup"><span data-stu-id="9a466-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="9a466-115">[Proměnné:](xref:microsoft.quantum.guide.variables) Popisuje roli proměnných v programech v jazyce Q# a jejich efektivní využití.</span><span class="sxs-lookup"><span data-stu-id="9a466-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="9a466-116">Tady najdete například informace o rozsazích vazeb, rozdílech mezi neměnnými a proměnlivými proměnnými a postupu jejich přiřazení nebo změně jejich přiřazení.</span><span class="sxs-lookup"><span data-stu-id="9a466-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="9a466-117">[Práce s qubity:](xref:microsoft.quantum.guide.qubits) Popisuje funkce jazyka Q# sloužící k adresování jednotlivých qubitů a systémů qubitů.</span><span class="sxs-lookup"><span data-stu-id="9a466-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="9a466-118">Konkrétně to zahrnuje jejich přidělení, provádění operací s nimi a nakonec jejich měření.</span><span class="sxs-lookup"><span data-stu-id="9a466-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="9a466-119">[Tok řízení:](xref:microsoft.quantum.guide.controlflow) Podrobně popisuje programovací vzory toku řízení, které jsou k dispozici v Q# a mezi které patří řada standardních technik (podmíněné spouštění, smyčky for a while atd.) a také vzor Repeat-Until-Success specifický pro kvantové výpočty.</span><span class="sxs-lookup"><span data-stu-id="9a466-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="9a466-120">[Testování a ladění:](xref:microsoft.quantum.guide.testingdebugging) Podrobně popisuje některé techniky k zajištění, že váš kód dělá to, co by měl.</span><span class="sxs-lookup"><span data-stu-id="9a466-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="9a466-121">Z důvodu obecné neprůhlednosti kvantových informací může ladění kvantového programu vyžadovat specializované techniky.</span><span class="sxs-lookup"><span data-stu-id="9a466-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="9a466-122">Naštěstí jazyk Q# podporuje mnoho technik klasického ladění, na které jsou programátoři zvyklí, a také ty, které jsou specifické pro kvantové výpočty.</span><span class="sxs-lookup"><span data-stu-id="9a466-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="9a466-123">Patří mezi ně vytváření a spouštění testů jednotek v jazyce Q#, vkládání *kontrolních výrazů* pro hodnoty a pravděpodobnosti do kódu a funkce `Dump`, které vypisuje stav cílového počítače.</span><span class="sxs-lookup"><span data-stu-id="9a466-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="9a466-124">Tyto funkce se dají použít společně s naším simulátorem celkového stavu k ladění určitých částí výpočtů obcházením některých kvantových omezení (např. teorému o nemožnosti klonování).</span><span class="sxs-lookup"><span data-stu-id="9a466-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="9a466-125">Kvantové simulátory a estimátory prostředků</span><span class="sxs-lookup"><span data-stu-id="9a466-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="9a466-126">[Kvantové simulátory a hostitelské aplikace:](xref:microsoft.quantum.machines) Přehled různých dostupných simulátorů a také obecného modelu spouštění mezi hostitelským programem a cílovými počítači.</span><span class="sxs-lookup"><span data-stu-id="9a466-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="9a466-127">[Simulátor celkového stavu:](xref:microsoft.quantum.machines.full-state-simulator) Cílový počítač, který simuluje celkový kvantový stav.</span><span class="sxs-lookup"><span data-stu-id="9a466-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="9a466-128">Tento simulátor je užitečný při úplném spouštění nebo ladění menších programů (méně než pár desítek qubitů).</span><span class="sxs-lookup"><span data-stu-id="9a466-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="9a466-129">[Estimátor prostředků:](xref:microsoft.quantum.machines.resources-estimator) Odhaduje prostředky potřebné ke spuštění dané instance operace Q# na kvantovém počítači.</span><span class="sxs-lookup"><span data-stu-id="9a466-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="9a466-130">[Simulátor trasování:](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Spouští kvantové programy, aniž by ve skutečnosti simuloval stav kvantového počítače, a díky tomu může spouštět kvantové programy využívající tisíce qubitů.</span><span class="sxs-lookup"><span data-stu-id="9a466-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="9a466-131">Tento simulátor je užitečný při ladění klasického kódu v rámci kvantového programu a také při odhadu potřebných prostředků.</span><span class="sxs-lookup"><span data-stu-id="9a466-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="9a466-132">[Simulátor Toffoli:](xref:microsoft.quantum.machines.toffoli-simulator) Kvantový simulátor pro zvláštní účely, který je možné používat s miliony qubitů, ale pouze pro programy s omezenou sadou kvantových operací (konkrétně operací X, CNOT a vícenásobně řízených operací X).</span><span class="sxs-lookup"><span data-stu-id="9a466-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="9a466-133">Stručné referenční stránky</span><span class="sxs-lookup"><span data-stu-id="9a466-133">Quick Reference Pages</span></span>

- <span data-ttu-id="9a466-134">[Příkazy magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp) Stručná referenční stránka pro příkazy magic IQ# v rámci poznámkových bloků Jupyter v Q#.</span><span class="sxs-lookup"><span data-stu-id="9a466-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
