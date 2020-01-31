---
title: 'Vývoj pomocí poznámkových bloků Q # Jupyter'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831065"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="a833b-102">Vývoj pomocí poznámkových bloků Q # Jupyter</span><span class="sxs-lookup"><span data-stu-id="a833b-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="a833b-103">Nainstalujte QDK pro vývoj operací Q # v poznámkových blocích Q # Jupyter.</span><span class="sxs-lookup"><span data-stu-id="a833b-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="a833b-104">Jupyter poznámkové bloky umožňují místní provádění kódu společně s pokyny, poznámkami a dalšími obsahy.</span><span class="sxs-lookup"><span data-stu-id="a833b-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="a833b-105">Toto prostředí je ideální pro psaní kódu Q # s vloženými vysvětleními nebo s využitím výpočetních interaktivních kurzů.</span><span class="sxs-lookup"><span data-stu-id="a833b-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="a833b-106">Podívejte se, co všechno k vytváření vlastních poznámkových bloků v Q# potřebujete.</span><span class="sxs-lookup"><span data-stu-id="a833b-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="a833b-107">IQ# (anglicky se vyslovuje i-q-sharp) je rozšíření sady .NET Core SDK primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a simulaci operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="a833b-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="a833b-108">V poznámkových blocích Q # Jupyter můžete spustit pouze kód Q # a operace nelze volat z externích hostitelských programů (např. Python nebo C# Files).</span><span class="sxs-lookup"><span data-stu-id="a833b-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="a833b-109">Toto prostředí není vhodné, pokud je vaším cílem kombinování externího programu klasického hostitele s programem.</span><span class="sxs-lookup"><span data-stu-id="a833b-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="a833b-110">Požadavky</span><span class="sxs-lookup"><span data-stu-id="a833b-110">Pre-requisites</span></span>

    - <span data-ttu-id="a833b-111">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="a833b-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="a833b-112">Poznámkový blok Jupyter</span><span class="sxs-lookup"><span data-stu-id="a833b-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="a833b-113">.NET Core SDK 3,1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="a833b-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="a833b-114">Nainstalujte balíček `iqsharp`.</span><span class="sxs-lookup"><span data-stu-id="a833b-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="a833b-115">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="a833b-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="a833b-116">Spusťte následující příkaz, kterým se spustí server poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="a833b-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="a833b-117">Otevřete kopii poznámkového bloku Jupyter a vložte adresu URL poskytnutou příkazovým řádkem do prohlížeče.</span><span class="sxs-lookup"><span data-stu-id="a833b-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="a833b-118">Vytvořte poznámkový blok Jupyter s použitím jádra Q# a do první buňky poznámkového bloku přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="a833b-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="a833b-119">Spusťte tuto buňku poznámkového bloku:</span><span class="sxs-lookup"><span data-stu-id="a833b-119">Run this cell of the notebook:</span></span>

        ![Buňka poznámkového bloku Jupyter s využitím kódu Q#](~/media/install-guide-jupyter.png)

        <span data-ttu-id="a833b-121">Ve výstupu buňky by se měl zobrazit text `SayHello`.</span><span class="sxs-lookup"><span data-stu-id="a833b-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="a833b-122">Při spouštění v poznámkových blocích Jupyter se kompiluje kód v jazyku Q# a výstupem poznámkového bloku jsou názvy nalezených operací.</span><span class="sxs-lookup"><span data-stu-id="a833b-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="a833b-123">V nové buňce spusťte právě vytvořenou operaci (v simulátoru) pomocí příkazu `%simulate`:</span><span class="sxs-lookup"><span data-stu-id="a833b-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![Buňka poznámkového bloku Jupyter s využitím příkazu magic %simulate](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="a833b-125">Měla by se zobrazit zpráva vytištěná na obrazovce spolu s výsledkem operace, kterou jste vyvolali (tady vidíte prázdné řazené kolekce členů `()`, protože naše operace jednoduše vrátí `Unit` typ).</span><span class="sxs-lookup"><span data-stu-id="a833b-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="whats-next"></a><span data-ttu-id="a833b-126">A co dál?</span><span class="sxs-lookup"><span data-stu-id="a833b-126">What's next?</span></span>

<span data-ttu-id="a833b-127">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="a833b-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
