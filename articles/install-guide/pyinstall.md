---
title: 'Vývoj pomocí Q # + Pythonu'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2020
ms.locfileid: "76830997"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="8bb54-102">Vývoj pomocí Q # + Pythonu</span><span class="sxs-lookup"><span data-stu-id="8bb54-102">Develop with Q# + Python</span></span>

<span data-ttu-id="8bb54-103">Nainstalujte QDK pro vývoj hostitelských programů v Pythonu, aby se volaly operace Q #.</span><span class="sxs-lookup"><span data-stu-id="8bb54-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="8bb54-104">Požadavky</span><span class="sxs-lookup"><span data-stu-id="8bb54-104">Pre-requisites</span></span>

    - <span data-ttu-id="8bb54-105">[Python](https://www.python.org/downloads/) 3.6 nebo novější</span><span class="sxs-lookup"><span data-stu-id="8bb54-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="8bb54-106">Správce balíčků Pythonu [PIP](https://pip.pypa.io/en/stable/installing)</span><span class="sxs-lookup"><span data-stu-id="8bb54-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="8bb54-107">.NET Core SDK 3,1 nebo novější</span><span class="sxs-lookup"><span data-stu-id="8bb54-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="8bb54-108">Nainstalujte balíček `qsharp`, balíček Pythonu, který umožňuje spolupráci mezi Q # a Pythonem.</span><span class="sxs-lookup"><span data-stu-id="8bb54-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="8bb54-109">Nainstalujte `iqsharp`, jádro používané v Jupyter a Pythonu, které poskytuje základní funkce pro kompilaci a provádění operací Q #.</span><span class="sxs-lookup"><span data-stu-id="8bb54-109">Install `iqsharp`, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="8bb54-110">I když v jakémkoli integrovaném vývojovém prostředí můžete použít Q # s Pythonem, důrazně doporučujeme pro vaše aplikace pro Q # + Python používat rozhraní IDE Visual Studio Code (VS Code).</span><span class="sxs-lookup"><span data-stu-id="8bb54-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="8bb54-111">Pomocí Visual Studio Code a rozšíření QDK Visual Studio Code získáte přístup k rozsáhlejším funkcím.</span><span class="sxs-lookup"><span data-stu-id="8bb54-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="8bb54-112">Nainstalovat [vs Code](https://code.visualstudio.com/download) (Windows, Linux a Mac)</span><span class="sxs-lookup"><span data-stu-id="8bb54-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="8bb54-113">Nainstalujte [rozšíření QDK pro vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="8bb54-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="8bb54-114">Ověřte instalaci vytvořením aplikace `Hello World`.</span><span class="sxs-lookup"><span data-stu-id="8bb54-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8bb54-115">Vytvořte minimální operaci v jazyku Q# tím, že vytvoříte soubor s názvem `Operation.qs` a do něj přidáte následující kód:</span><span class="sxs-lookup"><span data-stu-id="8bb54-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="8bb54-116">Vytvořte program v Pythonu s názvem `hello_world.py`, který bude volat operaci `SayHello()` jazyka Q#:</span><span class="sxs-lookup"><span data-stu-id="8bb54-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="8bb54-117">Spusťte program:</span><span class="sxs-lookup"><span data-stu-id="8bb54-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="8bb54-118">Ověřte výstup.</span><span class="sxs-lookup"><span data-stu-id="8bb54-118">Verify the output.</span></span> <span data-ttu-id="8bb54-119">Výstupem programu by měly být následující řádky:</span><span class="sxs-lookup"><span data-stu-id="8bb54-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="8bb54-120">Pomocí poznámkových bloků Python Jupyter můžete také napsat klasický program v Pythonu a v buňkách volat operace Q #.</span><span class="sxs-lookup"><span data-stu-id="8bb54-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="8bb54-121">Kód Pythonu je pouze běžný program v Pythonu.</span><span class="sxs-lookup"><span data-stu-id="8bb54-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="8bb54-122">A co dál?</span><span class="sxs-lookup"><span data-stu-id="8bb54-122">What's next?</span></span>

<span data-ttu-id="8bb54-123">Teď máte sadu Quantum Development Kit nainstalovanou v upřednostňovaném prostředí a můžete napsat a spustit [svůj první kvantový program](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="8bb54-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
