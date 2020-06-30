---
title: Vývoj s využitím Q# a Pythonu
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274049"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="e8918-102">Vývoj s využitím Q# a Pythonu</span><span class="sxs-lookup"><span data-stu-id="e8918-102">Develop with Q# and Python</span></span>

<span data-ttu-id="e8918-103">Nainstalujte sadu QDK pro vývoj hostitelských programů v Pythonu, volajících operace v Q#.</span><span class="sxs-lookup"><span data-stu-id="e8918-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="e8918-104">Požadavky</span><span class="sxs-lookup"><span data-stu-id="e8918-104">Prerequisites</span></span>

    - <span data-ttu-id="e8918-105">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="e8918-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="e8918-106">Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="e8918-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="e8918-107">Sada .NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="e8918-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="e8918-108">Nainstalujte `qsharp` – balíček Pythonu, který umožňuje spolupráci mezi Q# a Pythonem.</span><span class="sxs-lookup"><span data-stu-id="e8918-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="e8918-109">Nainstalujte IQ# – jádro primárně využívané Jupyterem a Pythonem, které poskytuje základní funkce pro kompilaci a spouštění operací v jazyce Q#.</span><span class="sxs-lookup"><span data-stu-id="e8918-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="e8918-110">Pokud se během kroku `dotnet iqsharp install` zobrazí chyba, otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="e8918-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="e8918-111">Pokud to pořád nefunguje, zkuste najít nainstalovaný nástroj `dotnet-iqsharp` (ve Windows `dotnet-iqsharp.exe`) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="e8918-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="e8918-112">kde `/path/to/dotnet-iqsharp` nahraďte absolutní cestou k nástroji `dotnet-iqsharp` v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="e8918-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="e8918-113">Obvykle bude ve složce `.dotnet/tools` ve vašem uživatelském profilu.</span><span class="sxs-lookup"><span data-stu-id="e8918-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="e8918-114">I když Q# s Pythonem můžete použít v jakémkoli integrovaném vývojovém prostředí, důrazně doporučujeme pro vaše aplikace Q# + Python používat rozhraní IDE Visual Studio Code (VS Code).</span><span class="sxs-lookup"><span data-stu-id="e8918-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="e8918-115">Použitím sady Visual Studio Code a rozšíření QDK získáte přístup k rozsáhlejším funkcím.</span><span class="sxs-lookup"><span data-stu-id="e8918-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="e8918-116">Nainstalujte [VS Code](https://code.visualstudio.com/download) (Windows, Linux a Mac)</span><span class="sxs-lookup"><span data-stu-id="e8918-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="e8918-117">Nainstalujte [rozšíření QDK pro VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="e8918-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="e8918-118">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="e8918-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="e8918-119">Vytvořte minimální operaci v jazyku Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:</span><span class="sxs-lookup"><span data-stu-id="e8918-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="e8918-120">Vytvořte program v Pythonu s názvem `hello_world.py`, který bude volat operaci `SayHello()` jazyka Q#:</span><span class="sxs-lookup"><span data-stu-id="e8918-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="e8918-121">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="e8918-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="e8918-122">Ověřte výstup.</span><span class="sxs-lookup"><span data-stu-id="e8918-122">Verify the output.</span></span> <span data-ttu-id="e8918-123">Výstupem programu by měly být následující řádky:</span><span class="sxs-lookup"><span data-stu-id="e8918-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="e8918-124">Pomocí poznámkových bloků Jupyter v Pythonu můžete také napsat klasický program v Pythonu a v buňkách volat operace Q#.</span><span class="sxs-lookup"><span data-stu-id="e8918-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="e8918-125">Kód Pythonu je běžný program v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="e8918-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e8918-126">Další kroky</span><span class="sxs-lookup"><span data-stu-id="e8918-126">Next steps</span></span>

<span data-ttu-id="e8918-127">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="e8918-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
