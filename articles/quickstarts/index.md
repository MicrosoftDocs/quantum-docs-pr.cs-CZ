---
title: Instalace sady Microsoft Quantum Development Kit (QDK)
description: Postup instalace sady Microsoft Quantum Development Kit pro různá prostředí
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 378970dc911ea5a794590f8336ffc6d3f9673285
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867569"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="0c1be-103">Instalace sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="0c1be-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="0c1be-104">Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním.</span><span class="sxs-lookup"><span data-stu-id="0c1be-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="0c1be-105">Sada QDK obsahuje tyto komponenty:</span><span class="sxs-lookup"><span data-stu-id="0c1be-105">The QDK consists of:</span></span>

- <span data-ttu-id="0c1be-106">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="0c1be-106">The Q# programming language</span></span>
- <span data-ttu-id="0c1be-107">Sada knihoven, které abstrahují komplexní funkce v Q#</span><span class="sxs-lookup"><span data-stu-id="0c1be-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="0c1be-108">Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#</span><span class="sxs-lookup"><span data-stu-id="0c1be-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="0c1be-109">Nástroje pro usnadnění vývoje</span><span class="sxs-lookup"><span data-stu-id="0c1be-109">Tools to facilitate your development</span></span>

<span data-ttu-id="0c1be-110">Programy v Q# je možné spustit jako samostatné aplikace s využitím Visual Studio Code nebo sady Visual Studio nebo prostřednictvím aplikací Jupyter Notebook s jádrem IQ# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="0c1be-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="0c1be-111">Také je možné je spárovat s hostitelským programem v jazyce .NET (obvykle v jazyce C#) nebo Pythonu, abyste mohli volat kvantové operace z klasického programu.</span><span class="sxs-lookup"><span data-stu-id="0c1be-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="0c1be-112">Pracovní postupy pro každé z těchto nastavení jsou popsány a porovnány v tématu [Způsoby spuštění programu v Q#](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="0c1be-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="0c1be-113">Pokud chcete pokračovat v instalaci sady QDK a vytváření projektů v jazyce v Q#, vyberte upřednostňovanou instalaci:</span><span class="sxs-lookup"><span data-stu-id="0c1be-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="0c1be-114">[Vývoj s využitím aplikací příkazového řádku v Q#](xref:microsoft.quantum.install.standalone) – Tento přístup zvolte, pokud chcete pracovat s Q# z příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="0c1be-114">[Develop with Q# command line applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command line.</span></span> <span data-ttu-id="0c1be-115">Tato možnost nevyžaduje ovladač ani hostitelský program jako následující možnosti.</span><span class="sxs-lookup"><span data-stu-id="0c1be-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="0c1be-116">[Vývoj s využitím poznámkových bloků Jupyter v Q#Q#](xref:microsoft.quantum.install.jupyter) – Toto prostředí vyberte, pokud chcete spouštět kód Q# v buňkách s vloženým textem nebo vytvářet interaktivní kurzy kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="0c1be-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="0c1be-117">[Vývoj s využitím Q# a Pythonu](xref:microsoft.quantum.install.python) – Můžete zkombinovat Python a Q# a vytvořit hostitelský program v Pythonu, který volá operace Q#.</span><span class="sxs-lookup"><span data-stu-id="0c1be-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="0c1be-118">[Vývoj s využitím Q# a .NET](xref:microsoft.quantum.install.cs) – Zkombinujte jazyk C#, F# nebo VB.NET a Q# a vytvořte hostitelský program v .NET, který volá operace Q#.</span><span class="sxs-lookup"><span data-stu-id="0c1be-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
