---
title: Nastavení sady Microsoft Quantum Development Kit (QDK)
description: Zjistěte, jak nastavit sadu Microsoft Quantum Development Kit pro různá prostředí.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859030"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="7d79f-103">Nastavení sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="7d79f-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="7d79f-104">Naučte se nastavit sadu Microsoft Quantum Development Kit (QDK) pro vaše prostředí, abyste mohli začít s kvantovým programováním.</span><span class="sxs-lookup"><span data-stu-id="7d79f-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="7d79f-105">Sada QDK obsahuje tyto komponenty:</span><span class="sxs-lookup"><span data-stu-id="7d79f-105">The QDK consists of:</span></span>

- <span data-ttu-id="7d79f-106">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="7d79f-106">The Q# programming language</span></span>
- <span data-ttu-id="7d79f-107">Sada knihoven, které abstrahují komplexní funkce v Q#</span><span class="sxs-lookup"><span data-stu-id="7d79f-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="7d79f-108">Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#</span><span class="sxs-lookup"><span data-stu-id="7d79f-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="7d79f-109">Nástroje pro usnadnění vývoje</span><span class="sxs-lookup"><span data-stu-id="7d79f-109">Tools to facilitate your development</span></span>

<span data-ttu-id="7d79f-110">Programy v Q# je možné spustit jako samostatné aplikace s využitím nástroje Visual Studio Code nebo sady Visual Studio, prostřednictvím aplikací Jupyter Notebook s jádrem IQ# Jupyter nebo spárované s hostitelským programem napsaným v Pythonu nebo v jazyce .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="7d79f-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="7d79f-111">Programy v Q# můžete také spouštět online s využitím [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) nebo [Dockeru](#use-the-qdk-with-docker).</span><span class="sxs-lookup"><span data-stu-id="7d79f-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="7d79f-112">Možnosti pro nastavení QDK</span><span class="sxs-lookup"><span data-stu-id="7d79f-112">Options for setting up the QDK</span></span>

<span data-ttu-id="7d79f-113">Sadu QDK můžete využít třemi způsoby:</span><span class="sxs-lookup"><span data-stu-id="7d79f-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="7d79f-114">Místní instalace sady QDK</span><span class="sxs-lookup"><span data-stu-id="7d79f-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="7d79f-115">Použití sady QDK online</span><span class="sxs-lookup"><span data-stu-id="7d79f-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="7d79f-116">Použití image Dockeru pro QDK</span><span class="sxs-lookup"><span data-stu-id="7d79f-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="7d79f-117">Místní instalace sady QDK</span><span class="sxs-lookup"><span data-stu-id="7d79f-117">Install the QDK locally</span></span>

<span data-ttu-id="7d79f-118">Kód v Q# můžete vyvíjet ve většině oblíbených integrovaných vývojových prostředí. Q# se dá také integrovat s dalšími jazyky, jako je Python a .NET (C#, F#).</span><span class="sxs-lookup"><span data-stu-id="7d79f-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="7d79f-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="7d79f-119"><b>VS Code</span></span><br><span data-ttu-id="7d79f-120">(2019 nebo novější)</b></span><span class="sxs-lookup"><span data-stu-id="7d79f-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="7d79f-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d79f-121"><b>Visual Studio</span></span><br><span data-ttu-id="7d79f-122">(2019 nebo novější)</b></span><span class="sxs-lookup"><span data-stu-id="7d79f-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="7d79f-123"><b>Poznámkové bloky Jupyter</b></span><span class="sxs-lookup"><span data-stu-id="7d79f-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="7d79f-124"><b>Příkazový řádek</b></span><span class="sxs-lookup"><span data-stu-id="7d79f-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="7d79f-125"><b>Podpora operačního systému:</b></span><span class="sxs-lookup"><span data-stu-id="7d79f-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-126">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="7d79f-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="7d79f-127">Jen ve Windows</span><span class="sxs-lookup"><span data-stu-id="7d79f-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="7d79f-128">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="7d79f-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="7d79f-129">Windows, macOS, Linux</span><span class="sxs-lookup"><span data-stu-id="7d79f-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="7d79f-130"><b>Q# samostatně</b></span><span class="sxs-lookup"><span data-stu-id="7d79f-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-131"><a href="xref:microsoft.quantum.install.standalone">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-132"><a href="xref:microsoft.quantum.install.standalone">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-133"><a href="xref:microsoft.quantum.install.jupyter">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-134"><a href="xref:microsoft.quantum.install.standalone">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="7d79f-135"><b>Q# a Python</b></span><span class="sxs-lookup"><span data-stu-id="7d79f-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-136"><a href="xref:microsoft.quantum.install.python">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-137"><a href="xref:microsoft.quantum.install.python">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-138"><a href="xref:microsoft.quantum.install.python">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-139"><a href="xref:microsoft.quantum.install.python">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="7d79f-140"><b>Q# a .NET (C#, F#)</b></span><span class="sxs-lookup"><span data-stu-id="7d79f-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="7d79f-141"><a href="xref:microsoft.quantum.install.cs">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-142"><a href="xref:microsoft.quantum.install.cs">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="7d79f-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="7d79f-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="7d79f-144"><a href="xref:microsoft.quantum.install.cs">Instalace</a></span><span class="sxs-lookup"><span data-stu-id="7d79f-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="7d79f-145">Použití sady QDK online</span><span class="sxs-lookup"><span data-stu-id="7d79f-145">Use the QDK Online</span></span>

<span data-ttu-id="7d79f-146">Pomocí následujících možností můžete také vyvíjet kód v Q#, aniž byste v místním prostředí cokoli instalovali:</span><span class="sxs-lookup"><span data-stu-id="7d79f-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="7d79f-147">Prostředek</span><span class="sxs-lookup"><span data-stu-id="7d79f-147">Resource</span></span>|<span data-ttu-id="7d79f-148">Výhody</span><span class="sxs-lookup"><span data-stu-id="7d79f-148">Advantages</span></span>|<span data-ttu-id="7d79f-149">Omezení</span><span class="sxs-lookup"><span data-stu-id="7d79f-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="7d79f-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="7d79f-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="7d79f-151">Bohaté vývojové prostředí online</span><span class="sxs-lookup"><span data-stu-id="7d79f-151">A rich online development environment</span></span>  |<span data-ttu-id="7d79f-152">Vyžaduje plán a předplatné Azure.</span><span class="sxs-lookup"><span data-stu-id="7d79f-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="7d79f-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="7d79f-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="7d79f-154">Bezplatné online prostředí poznámkových bloků</span><span class="sxs-lookup"><span data-stu-id="7d79f-154">Free online notebook experience</span></span> |<span data-ttu-id="7d79f-155">Bez trvalosti</span><span class="sxs-lookup"><span data-stu-id="7d79f-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="7d79f-156">Použití sady QDK s Dockerem</span><span class="sxs-lookup"><span data-stu-id="7d79f-156">Use the QDK with Docker</span></span>

<span data-ttu-id="7d79f-157">Naši image Dockeru pro QDK můžete využít v místní instalaci Dockeru nebo v cloudu prostřednictvím libovolné knihovny, která podporuje image Dockeru, například ACI.</span><span class="sxs-lookup"><span data-stu-id="7d79f-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="7d79f-158">Image Dockeru pro IQ# si můžete stáhnout tady: https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span><span class="sxs-lookup"><span data-stu-id="7d79f-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="7d79f-159">Docker můžete také využít spolu se vzdáleným vývojovým kontejnerem nástroje Visual Studio Code k rychlému definování vývojových prostředí.</span><span class="sxs-lookup"><span data-stu-id="7d79f-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="7d79f-160">Další informace o vývojových kontejnerech nástroje VS Code najdete tady: https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span><span class="sxs-lookup"><span data-stu-id="7d79f-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d79f-161">Další kroky</span><span class="sxs-lookup"><span data-stu-id="7d79f-161">Next steps</span></span>

<span data-ttu-id="7d79f-162">Pracovní postupy pro každé z těchto nastavení jsou popsány a porovnány v tématu [Způsoby spuštění programu v Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="7d79f-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
