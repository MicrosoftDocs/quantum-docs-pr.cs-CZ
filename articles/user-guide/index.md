---
title: Uživatelská příručka jazyka Q#
description: Přehled účelu a obsahu uživatelské příručky
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231753"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="573a4-103">Uživatelská příručka jazyka Q#</span><span class="sxs-lookup"><span data-stu-id="573a4-103">The Q# User Guide</span></span>

<span data-ttu-id="573a4-104">Vítá vás uživatelská příručka jazyka Q#!</span><span class="sxs-lookup"><span data-stu-id="573a4-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="573a4-105">V různých tématech této příručky uvádíme některé základy k vývoji kvantových programů pomocí jazyka Q#.</span><span class="sxs-lookup"><span data-stu-id="573a4-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="573a4-106">Úplnou specifikaci a dokumentaci programovacího jazyka Q# najdete v [příručce k jazyku Q#](xref:microsoft.quantum.qsharp.index).</span><span class="sxs-lookup"><span data-stu-id="573a4-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="573a4-107">Obsah uživatelské příručky</span><span class="sxs-lookup"><span data-stu-id="573a4-107">User Guide Contents</span></span>

- <span data-ttu-id="573a4-108">[Programy Q#](xref:microsoft.quantum.guide.programs): Rychlý úvod do kvantových programům v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="573a4-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="573a4-109">[Způsoby spuštění programu v Q#Q#](xref:microsoft.quantum.guide.host-programs): Popisuje, jak se spustí program v Q#, a poskytuje přehled různých způsobů volání programu: z příkazového řádku, v aplikacích Jupyter Notebook s podporou Q# nebo z klasického hostitelského programu napsaného v Pythonu nebo v jazyce .NET.</span><span class="sxs-lookup"><span data-stu-id="573a4-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="573a4-110">[Testování a ladění:](xref:microsoft.quantum.guide.testingdebugging) Podrobně popisuje některé techniky k zajištění, že váš kód dělá to, co by měl.</span><span class="sxs-lookup"><span data-stu-id="573a4-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="573a4-111">Z důvodu obecné neprůhlednosti kvantových informací může ladění kvantového programu vyžadovat specializované techniky.</span><span class="sxs-lookup"><span data-stu-id="573a4-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="573a4-112">Naštěstí jazyk Q# podporuje mnoho technik klasického ladění, na které jsou programátoři zvyklí, a také ty, které jsou specifické pro kvantové výpočty.</span><span class="sxs-lookup"><span data-stu-id="573a4-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="573a4-113">Patří mezi ně vytváření a spouštění testů jednotek v jazyce Q#, vkládání *kontrolních výrazů* pro hodnoty a pravděpodobnosti do kódu a funkce `Dump`, které vypisují stavy cílových počítačů.</span><span class="sxs-lookup"><span data-stu-id="573a4-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="573a4-114">Tyto funkce se dají použít společně s naším simulátorem celkového stavu k ladění určitých částí výpočtů obcházením některých kvantových omezení (např. [teorému o nemožnosti klonování](xref:microsoft.quantum.concepts.pauli)).</span><span class="sxs-lookup"><span data-stu-id="573a4-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="573a4-115">Kvantové simulátory a estimátory prostředků</span><span class="sxs-lookup"><span data-stu-id="573a4-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="573a4-116">[Kvantové simulátory a hostitelské aplikace:](xref:microsoft.quantum.machines) Přehled různých dostupných simulátorů a také způsobu, jakým hostitelské programy a cílové počítače spolupracují při spouštění programů v Q#.</span><span class="sxs-lookup"><span data-stu-id="573a4-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="573a4-117">[Simulátor celkového stavu:](xref:microsoft.quantum.machines.full-state-simulator) Cílový počítač, který simuluje celkový kvantový stav.</span><span class="sxs-lookup"><span data-stu-id="573a4-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="573a4-118">Tento simulátor je užitečný při úplném spouštění nebo ladění menších programů (méně než pár desítek qubitů).</span><span class="sxs-lookup"><span data-stu-id="573a4-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="573a4-119">[Estimátor prostředků:](xref:microsoft.quantum.machines.resources-estimator) Odhaduje prostředky potřebné ke spuštění konkrétní instance operace Q# na kvantovém počítači.</span><span class="sxs-lookup"><span data-stu-id="573a4-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="573a4-120">[Simulátor trasování:](xref:microsoft.quantum.machines.qc-trace-simulator.intro) Spouští kvantové programy, aniž by ve skutečnosti simuloval stav kvantového počítače, a díky tomu může spouštět kvantové programy využívající tisíce qubitů.</span><span class="sxs-lookup"><span data-stu-id="573a4-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="573a4-121">Tento simulátor je užitečný při ladění klasického kódu v rámci kvantového programu a také při odhadu potřebných prostředků.</span><span class="sxs-lookup"><span data-stu-id="573a4-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="573a4-122">[Simulátor Toffoli:](xref:microsoft.quantum.machines.toffoli-simulator) Kvantový simulátor pro zvláštní účely, který je možné používat s miliony qubitů, ale pouze pro programy s omezenou sadou kvantových operací (konkrétně operací X, CNOT a vícenásobně řízených operací X).</span><span class="sxs-lookup"><span data-stu-id="573a4-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="573a4-123">Stručné referenční stránky</span><span class="sxs-lookup"><span data-stu-id="573a4-123">Quick Reference Pages</span></span>

- <span data-ttu-id="573a4-124">[Příkazy magic IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): Stručná referenční stránka pro příkazy magic IQ# v aplikací Jupyter Notebook s podporou Q#.</span><span class="sxs-lookup"><span data-stu-id="573a4-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
