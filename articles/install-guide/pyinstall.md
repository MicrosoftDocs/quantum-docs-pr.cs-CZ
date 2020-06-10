---
title: 'Vývoj pomocí Q # a Pythonu'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630286"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="5e566-102">Vývoj pomocí Q # a Pythonu</span><span class="sxs-lookup"><span data-stu-id="5e566-102">Develop with Q# and Python</span></span>

<span data-ttu-id="5e566-103">Nainstalujte QDK pro vývoj hostitelských programů v Pythonu, aby se volaly operace Q #.</span><span class="sxs-lookup"><span data-stu-id="5e566-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="5e566-104">Požadavky</span><span class="sxs-lookup"><span data-stu-id="5e566-104">Prerequisites</span></span>

    - <span data-ttu-id="5e566-105">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="5e566-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="5e566-106">Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="5e566-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="5e566-107">.NET Core SDK 3,1</span><span class="sxs-lookup"><span data-stu-id="5e566-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="5e566-108">Nainstalujte `qsharp` balíček, balíček Pythonu, který umožňuje spolupráci mezi Q # a Pythonem.</span><span class="sxs-lookup"><span data-stu-id="5e566-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="5e566-109">Nainstalujte SWEETIQ #, jádro používané v Jupyter a Pythonu, které poskytuje základní funkce pro kompilaci a provádění operací Q #.</span><span class="sxs-lookup"><span data-stu-id="5e566-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="5e566-110">Pokud se během kroku zobrazí chyba `dotnet iqsharp install` , otevřete nové okno terminálu a zkuste to znovu.</span><span class="sxs-lookup"><span data-stu-id="5e566-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="5e566-111">Pokud to pořád nefunguje, zkuste vyhledat nainstalovaný `dotnet-iqsharp` Nástroj (ve Windows, `dotnet-iqsharp.exe` ) a spusťte:</span><span class="sxs-lookup"><span data-stu-id="5e566-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="5e566-112">kde `/path/to/dotnet-iqsharp` by měla být nahrazena absolutní cestou k `dotnet-iqsharp` nástroji v systému souborů.</span><span class="sxs-lookup"><span data-stu-id="5e566-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="5e566-113">Obvykle se tato složka nachází `.dotnet/tools` ve složce vašeho profilu uživatele.</span><span class="sxs-lookup"><span data-stu-id="5e566-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="5e566-114">I když v jakémkoli integrovaném vývojovém prostředí můžete použít Q # s Pythonem, důrazně doporučujeme pro vaše aplikace pro Q # + Python používat rozhraní IDE Visual Studio Code (VS Code).</span><span class="sxs-lookup"><span data-stu-id="5e566-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="5e566-115">Pomocí Visual Studio Code a rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím.</span><span class="sxs-lookup"><span data-stu-id="5e566-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="5e566-116">Nainstalovat [vs Code](https://code.visualstudio.com/download) (Windows, Linux a Mac)</span><span class="sxs-lookup"><span data-stu-id="5e566-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="5e566-117">Nainstalujte [rozšíření QDK pro vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="5e566-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="5e566-118">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="5e566-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="5e566-119">Vytvořte minimální operaci v jazyku Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:</span><span class="sxs-lookup"><span data-stu-id="5e566-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="5e566-120">Vytvořte program v Pythonu s názvem `hello_world.py`, který bude volat operaci `SayHello()` jazyka Q#:</span><span class="sxs-lookup"><span data-stu-id="5e566-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="5e566-121">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="5e566-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="5e566-122">Ověřte výstup.</span><span class="sxs-lookup"><span data-stu-id="5e566-122">Verify the output.</span></span> <span data-ttu-id="5e566-123">Výstupem programu by měly být následující řádky:</span><span class="sxs-lookup"><span data-stu-id="5e566-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="5e566-124">Pomocí poznámkových bloků Python Jupyter můžete také napsat klasický program v Pythonu a v buňkách volat operace Q #.</span><span class="sxs-lookup"><span data-stu-id="5e566-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="5e566-125">Kód Pythonu je pouze běžný program v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="5e566-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e566-126">Další kroky</span><span class="sxs-lookup"><span data-stu-id="5e566-126">Next steps</span></span>

<span data-ttu-id="5e566-127">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="5e566-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
