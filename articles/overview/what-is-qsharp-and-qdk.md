---
title: Co je programovací jazyk Q# a sada QDK?
description: Přečtěte si víc o sadě Microsoft Quantum Development Kit, programovacím jazyku Q# a vytváření kvantových programů.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 21adfcc1c5321d87665adb39a3c838bbda0b8861
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834563"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a><span data-ttu-id="95208-103">Co je programovací jazyk Q# a sada QDK?</span><span class="sxs-lookup"><span data-stu-id="95208-103">What are the Q# programming language and QDK?</span></span>

<span data-ttu-id="95208-104">Q# je opensourcový programovací jazyk Microsoftu pro vývoj a spouštění kvantových algoritmů.</span><span class="sxs-lookup"><span data-stu-id="95208-104">Q# is Microsoft’s open-source programming language for developing and running quantum algorithms.</span></span> <span data-ttu-id="95208-105">Je součástí sady Quantum Development Kit (QDK), která zahrnuje [knihovny Q#](xref:microsoft.quantum.libraries), [kvantové simulátory](xref:microsoft.quantum.machines), [rozšíření pro další programovací prostředí](xref:microsoft.quantum.install) a [dokumentaci k rozhraní API](xref:microsoft.quantum.apiref-intro).</span><span class="sxs-lookup"><span data-stu-id="95208-105">It’s part of the Quantum Development Kit (QDK), which includes [Q# libraries](xref:microsoft.quantum.libraries), [quantum simulators](xref:microsoft.quantum.machines), [extensions for other programming environments](xref:microsoft.quantum.install), and [API documentation](xref:microsoft.quantum.apiref-intro).</span></span> <span data-ttu-id="95208-106">Kromě standardní knihovny Q# zahrnuje QDK i knihovny pro chemii, strojové učení a numerické výpočty.</span><span class="sxs-lookup"><span data-stu-id="95208-106">In addition to the Standard Q# library, the QDK includes Chemistry, Machine Learning, and Numeric libraries.</span></span>

<span data-ttu-id="95208-107">Jako programovací jazyk přebírá Q# známé prvky z Pythonu, C# a F# a podporuje základní procedurální model psaní programů se smyčkami, podmínkami a běžnými datovými typy.</span><span class="sxs-lookup"><span data-stu-id="95208-107">As a programming language, Q# draws familiar elements from Python, C#, and F# and supports a basic procedural model for writing programs with loops, if/then statements, and common data types.</span></span> <span data-ttu-id="95208-108">Zavádí také nové datové struktury a operace specifické pro kvantové výpočty.</span><span class="sxs-lookup"><span data-stu-id="95208-108">It also introduces new quantum-specific data structures and operations.</span></span>

## <a name="what-can-i-do-with-the-qdk"></a><span data-ttu-id="95208-109">Co mohu s QDK dělat?</span><span class="sxs-lookup"><span data-stu-id="95208-109">What can I do with the QDK?</span></span>

<span data-ttu-id="95208-110">QDK je plnohodnotná vývojová sady pro jazyk Q#, kterou můžete používat s běžnými nástroji a jazyky při vývoji kvantových aplikací, které pak můžete spouštět v různých prostředích.</span><span class="sxs-lookup"><span data-stu-id="95208-110">The QDK is a full-featured development kit for Q# that you can use with common tools and languages to develop quantum applications that you can run in various environments.</span></span> <span data-ttu-id="95208-111">Programy v Q# lze spouštět jako konzolové aplikace, prostřednictvím aplikací Jupyter Notebook nebo v rámci hostitelského programu v Pythonu nebo .NET.</span><span class="sxs-lookup"><span data-stu-id="95208-111">Q# programs can run as a console application, through Jupyter Notebooks, or use a Python or .NET host program.</span></span>

### <a name="develop-in-common-tools-and-environments"></a><span data-ttu-id="95208-112">Vývoj ve známých nástrojích a prostředích</span><span class="sxs-lookup"><span data-stu-id="95208-112">Develop in common tools and environments</span></span>

<span data-ttu-id="95208-113">Integrujte svůj vývoj kvantových programů do prostředí [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone) a [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter).</span><span class="sxs-lookup"><span data-stu-id="95208-113">Integrate your quantum development with [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone), and [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter).</span></span> <span data-ttu-id="95208-114">Použijte vestavěná rozhraní API ke spárování programů s hostitelskými jazyky [Python](xref:microsoft.quantum.install.python) a [.NET](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="95208-114">Use the built-in APIs for pairing your programs with [Python](xref:microsoft.quantum.install.python) and [.NET](xref:microsoft.quantum.install.cs) host languages.</span></span>

### <a name="try-quantum-operations-and-domain-specific-libraries"></a><span data-ttu-id="95208-115">Kvantové operace a knihovny pro konkrétní obory</span><span class="sxs-lookup"><span data-stu-id="95208-115">Try quantum operations and domain-specific libraries</span></span>

<span data-ttu-id="95208-116">Napište a vyzkoušejte kvantové algoritmy zkoumající superpozici, provázání a další kvantové operace.</span><span class="sxs-lookup"><span data-stu-id="95208-116">Write and test quantum algorithms to explore superposition, entanglement, and other quantum operations.</span></span> <span data-ttu-id="95208-117">Knihovny Q# umožňují spouštění složitých kvantových programů, aniž by bylo třeba navrhovat nízkoúrovňové sekvence operací.</span><span class="sxs-lookup"><span data-stu-id="95208-117">The Q# libraries enable you to run complex quantum operations without having to design low-level operation sequences.</span></span>

### <a name="run-programs-in-simulators"></a><span data-ttu-id="95208-118">Spouštění programů v simulátorech</span><span class="sxs-lookup"><span data-stu-id="95208-118">Run programs in simulators</span></span>

<span data-ttu-id="95208-119">Kvantové programy je možné spouštět na plnostavovém kvantovém simulátoru, simulátoru Toffoli s omezeným rozsahem nebo v různých nástrojích pro odhad prostředků pro jazyk Q#.</span><span class="sxs-lookup"><span data-stu-id="95208-119">Run your quantum programs on a full-state quantum simulator, a limited-scope Toffoli simulator, or test your Q# code in different resource estimators.</span></span> 

## <a name="where-can-i-learn-more"></a><span data-ttu-id="95208-120">Kde získám další informace?</span><span class="sxs-lookup"><span data-stu-id="95208-120">Where can I learn more?</span></span>

|||
| ---- | ---- |
| <span data-ttu-id="95208-121">**Jsem v kvantových výpočtech nováčkem**</span><span class="sxs-lookup"><span data-stu-id="95208-121">**I'm new to quantum computing**</span></span> | <span data-ttu-id="95208-122">Seznamte se se základy kvantové fyziky a kvantových výpočtů v dokumentu [Klíčové koncepty](xref:microsoft.quantum.overview.understanding).</span><span class="sxs-lookup"><span data-stu-id="95208-122">Review some basics of quantum physics and quantum computing in [Key Concepts](xref:microsoft.quantum.overview.understanding).</span></span>|
| <span data-ttu-id="95208-123">**Chci proniknout do jazyka Q# hlouběji**</span><span class="sxs-lookup"><span data-stu-id="95208-123">**I want to dive deeper into the Q# language**</span></span> | <span data-ttu-id="95208-124">Seznamte se s typy, výrazy, proměnnými a strukturou kvantového programu v [Uživatelské příručce Q#](xref:microsoft.quantum.guide).</span><span class="sxs-lookup"><span data-stu-id="95208-124">Explore types, expressions, variables, and quantum program structure in the [Q# User Guide](xref:microsoft.quantum.guide).</span></span>|
| <span data-ttu-id="95208-125">**Chci jenom začít psát kvantové programy**</span><span class="sxs-lookup"><span data-stu-id="95208-125">**I just want to start writing quantum programs**</span></span> | <span data-ttu-id="95208-126">Nastavte si prostředí Q# a začněte psát kvantové programy s využitím [rychlých zprovoznění](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="95208-126">Set up your Q# environment and start writing quantum programs in [QuickStarts](xref:microsoft.quantum.install).</span></span>|

## <a name="how-does-no-locq-work"></a><span data-ttu-id="95208-127">Jak Q# funguje?</span><span class="sxs-lookup"><span data-stu-id="95208-127">How does Q# work?</span></span>

<span data-ttu-id="95208-128">Program v Q# je možné kompilovat do samostatné aplikace nebo volat z hostitelského programu napsaného v Pythonu nebo .NET.</span><span class="sxs-lookup"><span data-stu-id="95208-128">A Q# program can compile into a standalone application or be called by a host program that is written either in Python or a .NET language.</span></span>

<span data-ttu-id="95208-129">Když zkompilujete a spustíte program, vytvoří instanci kvantového simulátoru a předá mu váš kód Q#.</span><span class="sxs-lookup"><span data-stu-id="95208-129">When you compile and run the program, it creates an instance of the quantum simulator and passes the Q# code to it.</span></span> <span data-ttu-id="95208-130">Simulátor podle kódu Q# vytvoří simulované qubity a podle zadaných transformací bude manipulovat s jejich stavy.</span><span class="sxs-lookup"><span data-stu-id="95208-130">The simulator uses the Q# code to create qubits (simulations of quantum particles) and apply transformations to modify their state.</span></span> <span data-ttu-id="95208-131">Výsledky kvantových operací ze simulátoru se pak vrátí do programu.</span><span class="sxs-lookup"><span data-stu-id="95208-131">The results of the quantum operations in the simulator are then returned to the program.</span></span>  

<span data-ttu-id="95208-132">Izolování kódu Q# v simulátoru zajišťuje, že algoritmy budou odpovídat zákonům kvantové fyziky a budou správně fungovat i na kvantových počítačích.</span><span class="sxs-lookup"><span data-stu-id="95208-132">Isolating the Q# code in the simulator ensures that the algorithms follow the laws of quantum physics and can run correctly on quantum computers.</span></span>

![Tok kódu Qsharp](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a><span data-ttu-id="95208-134">Jak se sada QDK používá?</span><span class="sxs-lookup"><span data-stu-id="95208-134">How do I use the QDK?</span></span>

<span data-ttu-id="95208-135">Vše, co potřebujete k psaní a spouštění programů v Q#, včetně kompilátoru Q#, knihoven Q# a kvantových simulátorů, můžete nainstalovat a spouštět v místním počítači.</span><span class="sxs-lookup"><span data-stu-id="95208-135">Everything you need to write and run Q# programs, including the Q# compiler, the Q# libraries, and the quantum simulators, can be installed and run from your local computer.</span></span> <span data-ttu-id="95208-136">Časem budete moci spouštět své programy v Q# vzdáleně na skutečných kvantových počítačích, do té doby mohou poskytovat přesné a spolehlivé výsledky simulátory obsažené v sadě QDK.</span><span class="sxs-lookup"><span data-stu-id="95208-136">Eventually you will be able to run your Q# programs remotely on an actual quantum computer, but until then the quantum simulators provided with the QDK provide accurate and reliable results.</span></span>

- <span data-ttu-id="95208-137">Vývoj [aplikací v Q#](xref:microsoft.quantum.install.standalone) je nejrychlejším způsobem, jak začít.</span><span class="sxs-lookup"><span data-stu-id="95208-137">Developing [Q# applications](xref:microsoft.quantum.install.standalone) is the quickest way to get started.</span></span>

- <span data-ttu-id="95208-138">Kompilovat, simulovat a vizualizovat programy v Q# můžete také pomocí rozšíření [Jupyter Notebooks with Q#](xref:microsoft.quantum.install.jupyter).</span><span class="sxs-lookup"><span data-stu-id="95208-138">Run standalone [Jupyter Notebooks with IQ#](xref:microsoft.quantum.install.jupyter), a Jupyter extension for compiling, simulating, and visualizing Q# programs.</span></span>

- <span data-ttu-id="95208-139">Pokud znáte [Python](xref:microsoft.quantum.install.python), můžete ho použít jako hostitelskou platformu pro své první kvantové programy.</span><span class="sxs-lookup"><span data-stu-id="95208-139">If you are familiar with [Python](xref:microsoft.quantum.install.python), you can use it as a host programming platform to get started.</span></span> <span data-ttu-id="95208-140">Python je široce rozšířený nejen mezi vývojáři, ale i mezi vědci, výzkumníky a učiteli.</span><span class="sxs-lookup"><span data-stu-id="95208-140">Python enjoys widespread use not only among developers, but also scientists, researchers and teachers.</span></span>

- <span data-ttu-id="95208-141">Pokud již máte zkušenosti s [C#, F# nebo VB.NET](xref:microsoft.quantum.install.cs) a znáte vývojové prostředí Visual Studio, stačí do něj přidat jen několik rozšíření, abyste v něm mohli Q# používat.</span><span class="sxs-lookup"><span data-stu-id="95208-141">If you already have experience with [C#, F#, or VB.NET](xref:microsoft.quantum.install.cs) and are familiar with the Visual Studio development environment, there are just a few extensions you need to add to Visual Studio to prepare it for Q#.</span></span>  

## <a name="summary"></a><span data-ttu-id="95208-142">Souhrn</span><span class="sxs-lookup"><span data-stu-id="95208-142">Summary</span></span>

<span data-ttu-id="95208-143">Q# je opensourcový programovací jazyk pro vývoj kvantových programů.</span><span class="sxs-lookup"><span data-stu-id="95208-143">Q# is an open-source programming language for developing quantum programs.</span></span> <span data-ttu-id="95208-144">Obsahuje knihovny, které umožňují sestavování složitých kvantových operací, a simulátory pro přesné spouštění a testování programů.</span><span class="sxs-lookup"><span data-stu-id="95208-144">It has libraries that let you create complex quantum operations, and quantum simulators to accurately run and test your programs.</span></span> <span data-ttu-id="95208-145">Programy v Q# je možné spouštět jako samostatné aplikace nebo volat z hostitelského programu v Pythonu nebo .NET a můžete je psát, spouštět a testovat přímo v místním počítači.</span><span class="sxs-lookup"><span data-stu-id="95208-145">Q# programs can run as standalone apps or be called from a Python or .NET host program, and can be written, run, and tested from your local computer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95208-146">Další kroky</span><span class="sxs-lookup"><span data-stu-id="95208-146">Next Steps</span></span>

[<span data-ttu-id="95208-147">Lineární algebra pro kvantové výpočty</span><span class="sxs-lookup"><span data-stu-id="95208-147">Linear algebra for quantum computing</span></span>](xref:microsoft.quantum.overview.algebra)
