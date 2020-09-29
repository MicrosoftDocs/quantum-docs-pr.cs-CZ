---
title: Vývoj s využitím Q# a .NET
description: Naučte se vytvářet aplikace v Q# pomocí jazyků .NET.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8733918daa02afaea0fc1994d5f0851d4be9b93
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834325"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="d397c-103">Vývoj s využitím Q# a .NET</span><span class="sxs-lookup"><span data-stu-id="d397c-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="d397c-104">Jazyk Q# je navržený tak, aby dobře spolupracoval s jazyky používanými v prostředí .NET, jako je C# nebo F#.</span><span class="sxs-lookup"><span data-stu-id="d397c-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="d397c-105">V této příručce vám ukážeme, jak použít Q# s hostitelským programem napsaným v jazyce .NET.</span><span class="sxs-lookup"><span data-stu-id="d397c-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="d397c-106">Nejprve vytvoříme aplikaci v jazyce Q# a hostitele .NET, a potom ukážeme, jak volat Q# z tohoto hostitele.</span><span class="sxs-lookup"><span data-stu-id="d397c-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d397c-107">Požadavky</span><span class="sxs-lookup"><span data-stu-id="d397c-107">Prerequisites</span></span>

- <span data-ttu-id="d397c-108">Nainstalujte sadu Quantum Development Kit [pro práci s projekty v Q#](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="d397c-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="d397c-109">Vytvoření knihovny Q# a hostitele .NET</span><span class="sxs-lookup"><span data-stu-id="d397c-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="d397c-110">Prvním krokem je vytvoření projektů pro vaši knihovnu Q# a pro hostitele .NET, který bude volat operace a funkce definované ve vaší knihovně Q#.</span><span class="sxs-lookup"><span data-stu-id="d397c-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="d397c-111">Postupujte podle pokynů na kartě odpovídající vašemu vývojovému prostředí.</span><span class="sxs-lookup"><span data-stu-id="d397c-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="d397c-112">Pokud používáte jiný editor než Visual Studio nebo VS Code, jednoduše postupujte podle kroků pro příkazový řádek.</span><span class="sxs-lookup"><span data-stu-id="d397c-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="d397c-113">Visual Studio Code nebo příkazový řádek</span><span class="sxs-lookup"><span data-stu-id="d397c-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="d397c-114">Vytvoření nové knihovny Q#</span><span class="sxs-lookup"><span data-stu-id="d397c-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="d397c-115">Vytvořte nový projekt konzoly C# nebo F#.</span><span class="sxs-lookup"><span data-stu-id="d397c-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="d397c-116">Přidejte knihovnu Q# jako referenci z hostitelského programu.</span><span class="sxs-lookup"><span data-stu-id="d397c-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="d397c-117">[Volitelné] Vytvořte řešení pro oba projekty.</span><span class="sxs-lookup"><span data-stu-id="d397c-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="d397c-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d397c-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="d397c-119">Vytvoření nové knihovny Q#</span><span class="sxs-lookup"><span data-stu-id="d397c-119">Create a new Q# library</span></span>
  - <span data-ttu-id="d397c-120">Přejděte do části **Soubor** -> **Nový** -> **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="d397c-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="d397c-121">Do vyhledávacího pole zadejte Q#.</span><span class="sxs-lookup"><span data-stu-id="d397c-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="d397c-122">Vyberte **knihovnu Q#** .</span><span class="sxs-lookup"><span data-stu-id="d397c-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="d397c-123">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="d397c-123">Select **Next**</span></span>
  - <span data-ttu-id="d397c-124">Vyberte název a umístění knihovny.</span><span class="sxs-lookup"><span data-stu-id="d397c-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="d397c-125">**Nezaškrtávejte** možnost „umístit projekt a řešení ve stejném adresáři“.</span><span class="sxs-lookup"><span data-stu-id="d397c-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="d397c-126">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="d397c-126">Select **Create**</span></span>
- <span data-ttu-id="d397c-127">Vytvoření nového hostitelského programu C# nebo F#</span><span class="sxs-lookup"><span data-stu-id="d397c-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="d397c-128">Přejděte na **Soubor** → **Nový** → **Projekt**</span><span class="sxs-lookup"><span data-stu-id="d397c-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="d397c-129">Vyberte „Konzolová aplikace (.NET Core)“ pro C# nebo F#.</span><span class="sxs-lookup"><span data-stu-id="d397c-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="d397c-130">Vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="d397c-130">Select **Next**</span></span>
  - <span data-ttu-id="d397c-131">V části *řešení*vyberte „přidat do řešení“.</span><span class="sxs-lookup"><span data-stu-id="d397c-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="d397c-132">Zvolte název hostitelského programu.</span><span class="sxs-lookup"><span data-stu-id="d397c-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="d397c-133">Vyberte **Vytvořit**.</span><span class="sxs-lookup"><span data-stu-id="d397c-133">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="d397c-134">Volání Q# z .NET</span><span class="sxs-lookup"><span data-stu-id="d397c-134">Calling into Q# from .NET</span></span>

<span data-ttu-id="d397c-135">Jakmile budete mít projekty nastavené podle výše uvedených pokynů, můžete z konzolové aplikace zavolat program v Q#.</span><span class="sxs-lookup"><span data-stu-id="d397c-135">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="d397c-136">Kompilátor Q# vytvoří třídy .NET pro každou operaci a funkci Q#, které umožní spouštění kvantových programů v simulátoru.</span><span class="sxs-lookup"><span data-stu-id="d397c-136">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="d397c-137">Například [ukázka interoperability .NET](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) obsahuje následující příklad operace Q#:</span><span class="sxs-lookup"><span data-stu-id="d397c-137">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="d397c-138">K volání této operace z prostředí .NET na kvantovém simulátoru můžete použít metodu `Run` z třídy .NET `RunAlgorithm`, generované kompilátorem Q#:</span><span class="sxs-lookup"><span data-stu-id="d397c-138">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="d397c-139">C#</span><span class="sxs-lookup"><span data-stu-id="d397c-139">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="d397c-140">F#</span><span class="sxs-lookup"><span data-stu-id="d397c-140">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="d397c-141">Další kroky</span><span class="sxs-lookup"><span data-stu-id="d397c-141">Next steps</span></span>

<span data-ttu-id="d397c-142">Když teď máte sadu Quantum Development Kit konfigurovanou pro aplikace v Q# i pro spolupráci s prostředím .NET, můžete začít psát svůj [první kvantový program](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="d397c-142">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
