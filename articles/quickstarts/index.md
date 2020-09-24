---
title: Nastavení sady Microsoft Quantum Development Kit (QDK)
description: Zjistěte, jak nastavit sadu Microsoft Quantum Development Kit pro různá prostředí.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834478"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="8660c-103">Nastavení sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="8660c-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="8660c-104">Naučte se nastavit sadu Microsoft Quantum Development Kit (QDK) pro vaše prostředí, abyste mohli začít s kvantovým programováním.</span><span class="sxs-lookup"><span data-stu-id="8660c-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="8660c-105">Sada QDK obsahuje tyto komponenty:</span><span class="sxs-lookup"><span data-stu-id="8660c-105">The QDK consists of:</span></span>

- <span data-ttu-id="8660c-106">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="8660c-106">The Q# programming language</span></span>
- <span data-ttu-id="8660c-107">Sada knihoven, které abstrahují komplexní funkce v Q#</span><span class="sxs-lookup"><span data-stu-id="8660c-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="8660c-108">Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#</span><span class="sxs-lookup"><span data-stu-id="8660c-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="8660c-109">Nástroje pro usnadnění vývoje</span><span class="sxs-lookup"><span data-stu-id="8660c-109">Tools to facilitate your development</span></span>

<span data-ttu-id="8660c-110">Programy v Q# je možné spustit jako samostatné aplikace s využitím nástroje Visual Studio Code nebo sady Visual Studio, prostřednictvím aplikací Jupyter Notebook s jádrem IQ# Jupyter nebo spárované s hostitelským programem napsaným v Pythonu nebo v jazyce .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="8660c-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="8660c-111">Programy v Q# můžete také spouštět online s využitím [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) nebo [Dockeru](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="8660c-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="8660c-112">Možnosti pro nastavení QDK</span><span class="sxs-lookup"><span data-stu-id="8660c-112">Options for setting up the QDK</span></span>

<span data-ttu-id="8660c-113">Sadu QDK můžete využít třemi způsoby:</span><span class="sxs-lookup"><span data-stu-id="8660c-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="8660c-114">Místní instalace sady QDK</span><span class="sxs-lookup"><span data-stu-id="8660c-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="8660c-115">Použití sady QDK online</span><span class="sxs-lookup"><span data-stu-id="8660c-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="8660c-116">Použití image Dockeru pro QDK</span><span class="sxs-lookup"><span data-stu-id="8660c-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="8660c-117">Místní instalace sady QDK</span><span class="sxs-lookup"><span data-stu-id="8660c-117">Install the QDK locally</span></span>

<span data-ttu-id="8660c-118">Kód v Q# můžete vyvíjet ve většině oblíbených integrovaných vývojových prostředí. Q# se dá také integrovat s dalšími jazyky, jako je Python a .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="8660c-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="8660c-119">**VS Code<br>(2019 nebo novější)**</span><span class="sxs-lookup"><span data-stu-id="8660c-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="8660c-120">**Visual Studio<br>(2019 nebo novější)**</span><span class="sxs-lookup"><span data-stu-id="8660c-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="8660c-121">**Poznámkové bloky Jupyter**</span><span class="sxs-lookup"><span data-stu-id="8660c-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="8660c-122">**Příkazový řádek**</span><span class="sxs-lookup"><span data-stu-id="8660c-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="8660c-123">**OS**</span><span class="sxs-lookup"><span data-stu-id="8660c-123">**OS**</span></span> |<span data-ttu-id="8660c-124">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="8660c-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="8660c-125">Jen ve Windows</span><span class="sxs-lookup"><span data-stu-id="8660c-125">Windows only</span></span> |<span data-ttu-id="8660c-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="8660c-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="8660c-127">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="8660c-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="8660c-128">**Q# samostatně**</span><span class="sxs-lookup"><span data-stu-id="8660c-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="8660c-129">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="8660c-130">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="8660c-131">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="8660c-132">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="8660c-133">**Q# a Python**</span><span class="sxs-lookup"><span data-stu-id="8660c-133">**Q#  and Python**</span></span> |[<span data-ttu-id="8660c-134">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="8660c-135">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="8660c-136">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="8660c-137">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="8660c-138">**Q# a .NET (C#, F#)**</span><span class="sxs-lookup"><span data-stu-id="8660c-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="8660c-139">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="8660c-140">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="8660c-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="8660c-141">&#10006;</span></span> |[<span data-ttu-id="8660c-142">Instalace</span><span class="sxs-lookup"><span data-stu-id="8660c-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="8660c-143">Použití sady QDK online</span><span class="sxs-lookup"><span data-stu-id="8660c-143">Use the QDK Online</span></span>

<span data-ttu-id="8660c-144">Pomocí následujících možností můžete také vyvíjet kód v Q#, aniž byste v místním prostředí cokoli instalovali:</span><span class="sxs-lookup"><span data-stu-id="8660c-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="8660c-145">Prostředek</span><span class="sxs-lookup"><span data-stu-id="8660c-145">Resource</span></span>|<span data-ttu-id="8660c-146">Výhody</span><span class="sxs-lookup"><span data-stu-id="8660c-146">Advantages</span></span>|<span data-ttu-id="8660c-147">Omezení</span><span class="sxs-lookup"><span data-stu-id="8660c-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="8660c-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="8660c-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="8660c-149">Bohaté vývojové prostředí online</span><span class="sxs-lookup"><span data-stu-id="8660c-149">A rich online development environment</span></span>  |<span data-ttu-id="8660c-150">Vyžaduje plán a předplatné Azure.</span><span class="sxs-lookup"><span data-stu-id="8660c-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="8660c-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="8660c-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="8660c-152">Bezplatné online prostředí poznámkových bloků</span><span class="sxs-lookup"><span data-stu-id="8660c-152">Free online notebook experience</span></span> |<span data-ttu-id="8660c-153">Bez trvalosti</span><span class="sxs-lookup"><span data-stu-id="8660c-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="8660c-154">Použití sady QDK s Dockerem</span><span class="sxs-lookup"><span data-stu-id="8660c-154">Use the QDK with Docker</span></span>

<span data-ttu-id="8660c-155">Naši image Dockeru pro QDK můžete využít v místní instalaci Dockeru nebo v cloudu prostřednictvím libovolné knihovny, která podporuje image Dockeru, například ACI.</span><span class="sxs-lookup"><span data-stu-id="8660c-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="8660c-156">Image Dockeru pro IQ# si můžete stáhnout tady: https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="8660c-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="8660c-157">Docker můžete také využít spolu se vzdáleným vývojovým kontejnerem nástroje Visual Studio Code k rychlému definování vývojových prostředí.</span><span class="sxs-lookup"><span data-stu-id="8660c-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="8660c-158">Další informace o vývojových kontejnerech nástroje VS Code najdete tady: https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="8660c-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8660c-159">Další kroky</span><span class="sxs-lookup"><span data-stu-id="8660c-159">Next steps</span></span>

<span data-ttu-id="8660c-160">Pracovní postupy pro každé z těchto nastavení jsou popsány a porovnány v tématu [Způsoby spuštění programu v Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="8660c-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
