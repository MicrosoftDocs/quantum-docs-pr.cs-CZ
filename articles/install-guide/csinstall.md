---
title: Vývoj s využitím Q# a .NET
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 155367dbb1373f00e2b0bd732a5319b32462c9f9
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426506"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="e8db0-102">Vývoj s využitím Q# a .NET</span><span class="sxs-lookup"><span data-stu-id="e8db0-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="e8db0-103">Q # je sestavený tak, aby se dobře hrál s jazyky .NET, jako je C# a F #.</span><span class="sxs-lookup"><span data-stu-id="e8db0-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="e8db0-104">V této příručce vám ukážeme, jak použít Q # s hostitelským programem napsaným v jazyce .NET.</span><span class="sxs-lookup"><span data-stu-id="e8db0-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8db0-105">Požadavky</span><span class="sxs-lookup"><span data-stu-id="e8db0-105">Prerequisites</span></span>

- <span data-ttu-id="e8db0-106">Nainstalujte sadu [pro vývoj pro více procesorů pro použití s projekty příkazového řádku Q #](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="e8db0-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="e8db0-107">Vytvoření knihovny Q # a hostitele .NET</span><span class="sxs-lookup"><span data-stu-id="e8db0-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="e8db0-108">Prvním krokem je vytvoření projektů pro knihovnu Q # a pro hostitele .NET, který bude volat operace a funkce definované ve vaší knihovně Q #.</span><span class="sxs-lookup"><span data-stu-id="e8db0-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="e8db0-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e8db0-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="e8db0-110">Vytvoření nové knihovny Q #</span><span class="sxs-lookup"><span data-stu-id="e8db0-110">Create a new Q# library</span></span>
  - <span data-ttu-id="e8db0-111">Přejít na **soubor**  ->  **Nový**  ->  **projekt**</span><span class="sxs-lookup"><span data-stu-id="e8db0-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="e8db0-112">Do vyhledávacího pole zadejte text "Q #"</span><span class="sxs-lookup"><span data-stu-id="e8db0-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="e8db0-113">Vybrat **knihovnu Q #**</span><span class="sxs-lookup"><span data-stu-id="e8db0-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="e8db0-114">Vybrat **Další**</span><span class="sxs-lookup"><span data-stu-id="e8db0-114">Select **Next**</span></span>
  - <span data-ttu-id="e8db0-115">Zvolit název a umístění knihovny</span><span class="sxs-lookup"><span data-stu-id="e8db0-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="e8db0-116">Ujistěte se, že není **zaškrtnuté** možnost "umístit projekt a řešení ve stejném adresáři".</span><span class="sxs-lookup"><span data-stu-id="e8db0-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="e8db0-117">Vyberte **vytvořit** .</span><span class="sxs-lookup"><span data-stu-id="e8db0-117">Select **Create**</span></span>
- <span data-ttu-id="e8db0-118">Vytvořit nový hostitelský program C# nebo F #</span><span class="sxs-lookup"><span data-stu-id="e8db0-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="e8db0-119">Přejít na **soubor** → **Nový** → **projekt**</span><span class="sxs-lookup"><span data-stu-id="e8db0-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="e8db0-120">Vyberte Konzolová aplikace (.NET Core) pro C# nebo F. #</span><span class="sxs-lookup"><span data-stu-id="e8db0-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="e8db0-121">Vybrat **Další**</span><span class="sxs-lookup"><span data-stu-id="e8db0-121">Select **Next**</span></span>
  - <span data-ttu-id="e8db0-122">V části *řešení*vyberte Přidat do řešení.</span><span class="sxs-lookup"><span data-stu-id="e8db0-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="e8db0-123">Vyberte název hostitelského programu</span><span class="sxs-lookup"><span data-stu-id="e8db0-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="e8db0-124">Vyberte **vytvořit** .</span><span class="sxs-lookup"><span data-stu-id="e8db0-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="e8db0-125">Visual Studio Code nebo příkazový řádek</span><span class="sxs-lookup"><span data-stu-id="e8db0-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="e8db0-126">Vytvoření nové knihovny Q #</span><span class="sxs-lookup"><span data-stu-id="e8db0-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="e8db0-127">Vytvoření nového projektu konzoly C# nebo F #</span><span class="sxs-lookup"><span data-stu-id="e8db0-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="e8db0-128">Přidání knihovny Q # jako odkazu z hostitelského programu</span><span class="sxs-lookup"><span data-stu-id="e8db0-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="e8db0-129">Volitelné Vytvoření řešení pro oba projekty</span><span class="sxs-lookup"><span data-stu-id="e8db0-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="e8db0-130">Volání do Q # z .NET</span><span class="sxs-lookup"><span data-stu-id="e8db0-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="e8db0-131">Jakmile budete mít projekty nastavené podle výše uvedených pokynů, můžete do aplikace v konzole .NET zavolat do Q #.</span><span class="sxs-lookup"><span data-stu-id="e8db0-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="e8db0-132">Kompilátor Q # vytvoří třídy .NET pro každou operaci Q # a funkci, která vám umožní spouštět v simulátoru své programy pro práci s více operačními systémy.</span><span class="sxs-lookup"><span data-stu-id="e8db0-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="e8db0-133">Například [Ukázka interoperability .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) zahrnuje následující příklad operace Q #:</span><span class="sxs-lookup"><span data-stu-id="e8db0-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="e8db0-134">Chcete-li volat tuto operaci z rozhraní .NET pro simulátor doby provozu, můžete použít `Run` metodu `RunAlgorithm` třídy .NET vygenerovanou kompilátorem Q #:</span><span class="sxs-lookup"><span data-stu-id="e8db0-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="e8db0-135">C#</span><span class="sxs-lookup"><span data-stu-id="e8db0-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="e8db0-136">F#</span><span class="sxs-lookup"><span data-stu-id="e8db0-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="e8db0-137">Další kroky</span><span class="sxs-lookup"><span data-stu-id="e8db0-137">Next steps</span></span>

<span data-ttu-id="e8db0-138">Když teď máte prostředí pro vývoj s využitím provozu pro Q # pro programy příkazového řádku Q a pro interoperabilitu s .NET, můžete napsat a spustit [svůj první program](xref:microsoft.quantum.quickstarts.qrng)pro práci s procesorem.</span><span class="sxs-lookup"><span data-stu-id="e8db0-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
