---
title: Vývoj s využitím Q# a .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 714c15d9589095f0fe395fcd6941672167879dca
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885499"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="43528-102">Vývoj s využitím Q# a .NET</span><span class="sxs-lookup"><span data-stu-id="43528-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="43528-103">Jazyk Q# je navržen tak, aby dobře spolupracoval s jazyky používanými v prostředí .NET, jako je C# nebo F#.</span><span class="sxs-lookup"><span data-stu-id="43528-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="43528-104">V tomto tématu vám ukážeme, jak použít Q# s hostitelským programem napsaným v jazyce .NET.</span><span class="sxs-lookup"><span data-stu-id="43528-104">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="43528-105">Nejprve vytvoříme aplikaci v jazyce Q# a hostitele .NET, a potom ukážeme, jak volat Q# z hostitele.</span><span class="sxs-lookup"><span data-stu-id="43528-105">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43528-106">Požadavky</span><span class="sxs-lookup"><span data-stu-id="43528-106">Prerequisites</span></span>

- <span data-ttu-id="43528-107">Nainstalujte sadu Quantum Development Kit [pro práci s projekty Q# na příkazovém řádku](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="43528-107">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="43528-108">Vytvoření knihovny Q# a hostitele .NET</span><span class="sxs-lookup"><span data-stu-id="43528-108">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="43528-109">Prvním krokem je vytvoření projektů pro vaši knihovnu Q# a pro hostitele .NET, který bude volat operace a funkce definované ve vaší knihovně Q#.</span><span class="sxs-lookup"><span data-stu-id="43528-109">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="43528-110">Postupujte podle pokynů na kartě odpovídající vašemu vývojovému prostředí.</span><span class="sxs-lookup"><span data-stu-id="43528-110">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="43528-111">Pokud používáte jiný editor než Visual Studio nebo VS Code, jednoduše postupujte podle kroků pro příkazový řádek.</span><span class="sxs-lookup"><span data-stu-id="43528-111">If you are using an editor other than Visual Studio or VS Code, simply follow the command line steps.</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="43528-112">Visual Studio Code nebo Příkazový řádek</span><span class="sxs-lookup"><span data-stu-id="43528-112">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="43528-113">Vytvoření nové knihovny Q#</span><span class="sxs-lookup"><span data-stu-id="43528-113">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="43528-114">Vytvořte nový projekt konzoly C# nebo F#.</span><span class="sxs-lookup"><span data-stu-id="43528-114">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="43528-115">Přidejte knihovnu Q# jako referenci z hostitelského programu.</span><span class="sxs-lookup"><span data-stu-id="43528-115">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="43528-116">[Volitelné] Vytvořte řešení pro oba projekty.</span><span class="sxs-lookup"><span data-stu-id="43528-116">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="43528-117">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="43528-117">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="43528-118">Vytvoření nové knihovny Q#</span><span class="sxs-lookup"><span data-stu-id="43528-118">Create a new Q# library</span></span>
  - <span data-ttu-id="43528-119">Přejděte do části **Soubor** -> **Nový** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="43528-119">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="43528-120">Do vyhledávacího pole zadejte „Q#“.</span><span class="sxs-lookup"><span data-stu-id="43528-120">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="43528-121">Vyberte **Q# Library**.</span><span class="sxs-lookup"><span data-stu-id="43528-121">Select **Q# Library**</span></span>
  - <span data-ttu-id="43528-122">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="43528-122">Select **Next**</span></span>
  - <span data-ttu-id="43528-123">Vyberte název a umístění knihovny.</span><span class="sxs-lookup"><span data-stu-id="43528-123">Choose a name and location for your library</span></span>
  - <span data-ttu-id="43528-124">**Nezaškrtávejte** možnost „umístit projekt a řešení ve stejném adresáři“.</span><span class="sxs-lookup"><span data-stu-id="43528-124">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="43528-125">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="43528-125">Select **Create**</span></span>
- <span data-ttu-id="43528-126">Vytvoření nového hostitelského programu C# nebo F#</span><span class="sxs-lookup"><span data-stu-id="43528-126">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="43528-127">Přejděte na **Soubor** → **Nový** → **Projekt**</span><span class="sxs-lookup"><span data-stu-id="43528-127">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="43528-128">Vyberte „Konzolová aplikace (.NET Core)“ pro C# nebo F#.</span><span class="sxs-lookup"><span data-stu-id="43528-128">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="43528-129">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="43528-129">Select **Next**</span></span>
  - <span data-ttu-id="43528-130">V části *řešení*vyberte „přidat do řešení“.</span><span class="sxs-lookup"><span data-stu-id="43528-130">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="43528-131">Zvolte název hostitelského programu.</span><span class="sxs-lookup"><span data-stu-id="43528-131">Choose a name for your host program</span></span>
  - <span data-ttu-id="43528-132">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="43528-132">Select **Create**</span></span>

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="43528-133">Volání Q# z .NET</span><span class="sxs-lookup"><span data-stu-id="43528-133">Calling into Q# from .NET</span></span>

<span data-ttu-id="43528-134">Jakmile budete mít projekty nastavené podle výše uvedených pokynů, můžete z konzolové aplikace zavolat program Q#.</span><span class="sxs-lookup"><span data-stu-id="43528-134">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="43528-135">Kompilátor Q# vytvoří třídy .NET pro každou operaci a funkci Q#, které umožní spouštění kvantových programů v simulátoru.</span><span class="sxs-lookup"><span data-stu-id="43528-135">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="43528-136">Například [ukázka interoperability .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) obsahuje následující příklad operace Q#:</span><span class="sxs-lookup"><span data-stu-id="43528-136">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="43528-137">K volání této operace z prostředí .NET na kvantovém simulátoru můžete použít metodu `Run` z třídy .NET `RunAlgorithm`, generované kompilátorem Q#:</span><span class="sxs-lookup"><span data-stu-id="43528-137">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="43528-138">C#</span><span class="sxs-lookup"><span data-stu-id="43528-138">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="43528-139">F#</span><span class="sxs-lookup"><span data-stu-id="43528-139">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="43528-140">Další kroky</span><span class="sxs-lookup"><span data-stu-id="43528-140">Next steps</span></span>

<span data-ttu-id="43528-141">Když teď máte sadu Quantum Development Kit konfigurovanou pro programy Q# na příkazovém řádku i pro spolupráci s prostředím .NET, můžete začít psát [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="43528-141">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
