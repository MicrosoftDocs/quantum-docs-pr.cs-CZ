---
title: Přispívání ukázek do Microsoft QDK
description: Naučte se, jak přispívat vzorový kód do Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024147"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="73daa-103">Přispívání ukázek do vývojové sady pro všechna ta</span><span class="sxs-lookup"><span data-stu-id="73daa-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="73daa-104">Pokud vás zajímá přispívání kódu do [úložiště ukázek](https://github.com/Microsoft/Quantum), Děkujeme za to, že komunita pro vývoj všech stavů je lepší.</span><span class="sxs-lookup"><span data-stu-id="73daa-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="73daa-105">Úložiště ukázek pro danou sadu pro vývojová prostředí</span><span class="sxs-lookup"><span data-stu-id="73daa-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="73daa-106">Abychom vám pomohli připravit váš příspěvek tak, aby co nejvíce pomohl, je vhodné si rychle prohlédnout, jak je úložiště ukázek vymezeno:</span><span class="sxs-lookup"><span data-stu-id="73daa-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="73daa-107">To znamená, že ukázky v [úložišti Microsoft/](https://github.com/microsoft/Quantum) probíhají v členění podle oblasti předmětu do různých složek, jako je `algorithms/`, `arithmetic/`nebo `characterization/`.</span><span class="sxs-lookup"><span data-stu-id="73daa-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="73daa-108">Každá ukázka v rámci složky pro každou oblast obsahuje jednu složku, která shromažďuje vše, co si uživatel bude muset prozkoumat a použít tuto ukázku.</span><span class="sxs-lookup"><span data-stu-id="73daa-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="73daa-109">Princip strukturování ukázek</span><span class="sxs-lookup"><span data-stu-id="73daa-109">How Samples are Structured</span></span>

<span data-ttu-id="73daa-110">Podívejte se na soubory, které tvoří každou složku, a pojďme se podrobně na ukázku [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) .</span><span class="sxs-lookup"><span data-stu-id="73daa-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="73daa-111">File</span><span class="sxs-lookup"><span data-stu-id="73daa-111">File</span></span>              | <span data-ttu-id="73daa-112">Popis</span><span class="sxs-lookup"><span data-stu-id="73daa-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="73daa-113">Projekt Q # použitý k sestavení ukázky s .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="73daa-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="73daa-114">Operace a funkce Q # pro ukázku</span><span class="sxs-lookup"><span data-stu-id="73daa-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="73daa-115">C#hostitelský program použitý ke spuštění ukázky</span><span class="sxs-lookup"><span data-stu-id="73daa-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="73daa-116">Hostitelský program Pythonu použitý ke spuštění ukázky</span><span class="sxs-lookup"><span data-stu-id="73daa-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="73daa-117">Dokumentace k tomu, co ukázka dělá a jak ji používat</span><span class="sxs-lookup"><span data-stu-id="73daa-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="73daa-118">Ne všechny ukázky budou mít přesně stejnou sadu souborů (např.: některé ukázky můžou být C#pouze v případě, že jiné můžou mít hostitele v Pythonu nebo některé ukázky mohou vyžadovat, aby soubory auxillary data fungovaly).</span><span class="sxs-lookup"><span data-stu-id="73daa-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="73daa-119">Anatomie užitečného souboru READme</span><span class="sxs-lookup"><span data-stu-id="73daa-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="73daa-120">Jedním z zvláště důležitých souborů je ale `README.md` soubor, jak si uživatelé musí začít s ukázkou.</span><span class="sxs-lookup"><span data-stu-id="73daa-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="73daa-121">Každý `README.md` by měl začít s některými metadaty, které pomáhají docs.microsoft.com/samples najít váš příspěvek.</span><span class="sxs-lookup"><span data-stu-id="73daa-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="73daa-122">Podívejte se, jak se vykresluje ukázka chsh-Game.</span><span class="sxs-lookup"><span data-stu-id="73daa-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="73daa-123">Tato metadata se poskytují jako [YAML záhlaví](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) , které určuje, jaké jazyky vaše ukázka pokrývá (obvykle se `qsharp`, `csharp`a `python`) a jaké produkty vaše ukázka pokrývá (obvykle jenom `qdk`).</span><span class="sxs-lookup"><span data-stu-id="73daa-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="73daa-124">Pro zobrazení ukázky na docs.microsoft.com/samples se vyžaduje klíč `page_type: sample` v hlavičce.</span><span class="sxs-lookup"><span data-stu-id="73daa-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="73daa-125">Podobně jsou klíče `product` a `language` důležité pro pomoc uživatelům při hledání a spouštění ukázky.</span><span class="sxs-lookup"><span data-stu-id="73daa-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="73daa-126">Pak je užitečné poskytnout krátký úvod, který říká, co dělá vaše nová Ukázka:</span><span class="sxs-lookup"><span data-stu-id="73daa-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="73daa-127">Uživatelé vaší ukázky budou také považovat za informace o tom, co potřebují ke spuštění (např.: uživatelé potřebují jenom vývojářskou vývojovou sadu, nebo potřebují další software, jako je Node. js?):</span><span class="sxs-lookup"><span data-stu-id="73daa-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="73daa-128">U všech to je tak možné sdělit uživatelům, jak spustit ukázku:</span><span class="sxs-lookup"><span data-stu-id="73daa-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="73daa-129">Nakonec je vhodné sdělit uživatelům, co každý soubor ve vaší ukázce dělá, a kde můžou získat další informace:</span><span class="sxs-lookup"><span data-stu-id="73daa-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="73daa-130">Nezapomeňte místo toho použít absolutní adresy URL, protože se při vykreslování na docs.microsoft.com/samples zobrazí vaše ukázka na jiné adrese URL.</span><span class="sxs-lookup"><span data-stu-id="73daa-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
