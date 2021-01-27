---
title: Základní klasifikace s Machine Learningovou knihovnou
description: Naučte se spouštět sekvenční třídění na základě počtu počátečních a napsaných v Q# Machine Learning knihovně QDK Microsoft.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fe686a87fbdc610badc0bbcbc0bf7b065e0bce9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854051"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="e3c33-103">Základní klasifikace: klasifikace dat pomocí QDK</span><span class="sxs-lookup"><span data-stu-id="e3c33-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="e3c33-104">V tomto rychlém startu se dozvíte, jak spustit sekvenční třídění, které bylo napsáno Q# pomocí Machine Learning knihovny QDK.</span><span class="sxs-lookup"><span data-stu-id="e3c33-104">In this Quickstart, you will learn how to run a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="e3c33-105">V této příručce použijeme datovou sadu s poloviční měsíc pomocí struktury klasifikátoru definované v Q# .</span><span class="sxs-lookup"><span data-stu-id="e3c33-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3c33-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="e3c33-106">Prerequisites</span></span>

- <span data-ttu-id="e3c33-107">Sada Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="e3c33-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="e3c33-108">Vytvořte Q# projekt pro [hostitelský program Pythonu](xref:microsoft.quantum.install.python) nebo pro [hostitelský program C#](xref:microsoft.quantum.install.cs).</span><span class="sxs-lookup"><span data-stu-id="e3c33-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="e3c33-109">Hostitelský program</span><span class="sxs-lookup"><span data-stu-id="e3c33-109">Host program</span></span>

<span data-ttu-id="e3c33-110">Hostitelský program se skládá ze tří částí:</span><span class="sxs-lookup"><span data-stu-id="e3c33-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="e3c33-111">Načtěte datovou sadu a vyberte sadu počátečních parametrů pro váš model.</span><span class="sxs-lookup"><span data-stu-id="e3c33-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="e3c33-112">Spusťte školení a určete parametry a posun modelu.</span><span class="sxs-lookup"><span data-stu-id="e3c33-112">Run training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="e3c33-113">Ověří model a určí jeho přesnost.</span><span class="sxs-lookup"><span data-stu-id="e3c33-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="e3c33-114">Python s Visual Studio Code nebo příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="e3c33-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="e3c33-115">Pokud chcete spustit Q# klasifikátor z Pythonu, uložte následující kód jako `host.py` .</span><span class="sxs-lookup"><span data-stu-id="e3c33-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="e3c33-116">Nezapomeňte, že také potřebujete Q# soubor `Training.qs` , který je vysvětlen dále v tomto kurzu.</span><span class="sxs-lookup"><span data-stu-id="e3c33-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="e3c33-117">Pak můžete hostitelský program Pythonu spustit z příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="e3c33-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="e3c33-118">C# s Visual Studio Code nebo příkazovým řádkem</span><span class="sxs-lookup"><span data-stu-id="e3c33-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="e3c33-119">Chcete-li spustit Q# klasifikátor z C#, uložte následující kód jako `Host.cs` .</span><span class="sxs-lookup"><span data-stu-id="e3c33-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="e3c33-120">Nezapomeňte, že také potřebujete Q# soubor `Training.qs` , který je vysvětlen dále v tomto kurzu.</span><span class="sxs-lookup"><span data-stu-id="e3c33-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="e3c33-121">Pak můžete hostitelský program C# spustit z příkazového řádku:</span><span class="sxs-lookup"><span data-stu-id="e3c33-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="e3c33-122">C# s Visual Studiem 2019</span><span class="sxs-lookup"><span data-stu-id="e3c33-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="e3c33-123">Chcete-li spustit nový Q# program z c# v aplikaci Visual Studio, upravte `Host.cs` tak, aby obsahovalo následující kód jazyka c#.</span><span class="sxs-lookup"><span data-stu-id="e3c33-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="e3c33-124">Nezapomeňte, že také potřebujete Q# soubor `Training.qs` , který je vysvětlen dále v tomto kurzu.</span><span class="sxs-lookup"><span data-stu-id="e3c33-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="e3c33-125">Stiskněte klávesu F5 a program se spustí.</span><span class="sxs-lookup"><span data-stu-id="e3c33-125">Press F5, and the program will start to run.</span></span> <span data-ttu-id="e3c33-126">V novém okně se zobrazí následující výsledky:</span><span class="sxs-lookup"><span data-stu-id="e3c33-126">A new window will display the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="e3c33-127">\#Kód třídění Q</span><span class="sxs-lookup"><span data-stu-id="e3c33-127">Q\# classifier code</span></span>

<span data-ttu-id="e3c33-128">Teď se podíváme, jak se operace vyvolané hostitelským programem definují v tématu Q# .</span><span class="sxs-lookup"><span data-stu-id="e3c33-128">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="e3c33-129">Následující kód ukládáme do souboru s názvem `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="e3c33-129">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="e3c33-130">Nejdůležitější funkce a operace definované v kódu výše jsou:</span><span class="sxs-lookup"><span data-stu-id="e3c33-130">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="e3c33-131">`ClassifierStructure() : ControlledRotation[]` : v této funkci nastavíme strukturu modelu našeho okruhu přidáním vrstev řízených bran, které považujeme za.</span><span class="sxs-lookup"><span data-stu-id="e3c33-131">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="e3c33-132">Tento krok je podobný deklaraci vrstev neurons v sekvenčním modelu hloubkového učení.</span><span class="sxs-lookup"><span data-stu-id="e3c33-132">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="e3c33-133">`TrainHalfMoonModel() : (Double[], Double)` : Tato operace je základní částí kódu a definuje školení.</span><span class="sxs-lookup"><span data-stu-id="e3c33-133">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="e3c33-134">Tady načteme ukázky z datové sady zahrnuté do knihovny, nastavíme parametry Hyper a počáteční parametry pro školení a my zahájíme školení voláním operace `TrainSequentialClassifier` zahrnuté do knihovny.</span><span class="sxs-lookup"><span data-stu-id="e3c33-134">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="e3c33-135">Vytvoří výstup parametrů a posunu, který určuje klasifikátor.</span><span class="sxs-lookup"><span data-stu-id="e3c33-135">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="e3c33-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : Tato operace definuje proces ověření pro vyhodnocení modelu.</span><span class="sxs-lookup"><span data-stu-id="e3c33-136">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="e3c33-137">Tady načteme ukázky pro ověřování, počet měření na vzorek a toleranci.</span><span class="sxs-lookup"><span data-stu-id="e3c33-137">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="e3c33-138">Vyprodukuje počet chybných klasifikací na zvolené dávce vzorků pro ověření.</span><span class="sxs-lookup"><span data-stu-id="e3c33-138">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3c33-139">Další kroky</span><span class="sxs-lookup"><span data-stu-id="e3c33-139">Next steps</span></span>

<span data-ttu-id="e3c33-140">Nejprve můžete přehrát kód a zkusit změnit některé parametry, abyste viděli, jak ovlivní školení.</span><span class="sxs-lookup"><span data-stu-id="e3c33-140">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="e3c33-141">V dalším kurzu pak [Navrhněte vlastní třídění](xref:microsoft.quantum.libraries.machine-learning.design), kde se dozvíte, jak definovat strukturu třídění.</span><span class="sxs-lookup"><span data-stu-id="e3c33-141">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
