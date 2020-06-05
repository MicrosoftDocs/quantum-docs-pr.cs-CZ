---
title: Instalace sady Microsoft Quantum Development Kit (QDK)
description: Postup instalace sady Microsoft Quantum Development Kit pro různá prostředí
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: a5230f506bce02c331d22d6a428b3bd92052bbd4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327559"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="5be10-103">Instalace sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="5be10-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="5be10-104">Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním.</span><span class="sxs-lookup"><span data-stu-id="5be10-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="5be10-105">Sada QDK obsahuje tyto komponenty:</span><span class="sxs-lookup"><span data-stu-id="5be10-105">The QDK consists of:</span></span>

- <span data-ttu-id="5be10-106">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="5be10-106">The Q# programming language</span></span>
- <span data-ttu-id="5be10-107">Sada knihoven, které abstrahují komplexní funkce v Q#</span><span class="sxs-lookup"><span data-stu-id="5be10-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="5be10-108">Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#</span><span class="sxs-lookup"><span data-stu-id="5be10-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="5be10-109">Nástroje pro usnadnění vývoje</span><span class="sxs-lookup"><span data-stu-id="5be10-109">Tools to facilitate your development</span></span>

<span data-ttu-id="5be10-110">Programy v Q# je možné spustit jako samostatné aplikace s využitím Visual Studio Code nebo sady Visual Studio nebo prostřednictvím poznámkových bloků Jupyter s jádrem IQ# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="5be10-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="5be10-111">Také je možné je spárovat s hostitelským programem v jazyce .NET (obvykle v jazyce C#) nebo Pythonu, abyste mohli volat kvantové operace z klasického programu.</span><span class="sxs-lookup"><span data-stu-id="5be10-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="5be10-112">Sada QDK je k dispozici pro víc vývojových prostředí.</span><span class="sxs-lookup"><span data-stu-id="5be10-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="5be10-113">Vyberte si upřednostňovanou instalaci z následujících možností:</span><span class="sxs-lookup"><span data-stu-id="5be10-113">Select your preferred setup from:</span></span>

<span data-ttu-id="5be10-114">[Vývoj s využitím aplikací příkazového řádku v Q#](xref:microsoft.quantum.install.standalone) – Tento přístup zvolte, pokud chcete pracovat s Q# z příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="5be10-114">[Develop with Q# command line applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command line.</span></span> <span data-ttu-id="5be10-115">Tato možnost nevyžaduje ovladač ani hostitelský program jako následující možnosti.</span><span class="sxs-lookup"><span data-stu-id="5be10-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="5be10-116">[Vývoj s využitím poznámkových bloků Jupyter v Q#](xref:microsoft.quantum.install.jupyter) – Toto prostředí vyberte, pokud chcete spouštět kód Q# v buňkách s vloženým textem nebo vytvářet interaktivní kurzy kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="5be10-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="5be10-117">[Vývoj s využitím Q# a Pythonu](xref:microsoft.quantum.install.python) – Můžete zkombinovat Python a Q# a vytvořit hostitelský program v Pythonu, který volá operace Q#.</span><span class="sxs-lookup"><span data-stu-id="5be10-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="5be10-118">[Vývoj s využitím Q# a .NET](xref:microsoft.quantum.install.cs) – Zkombinujte jazyk C#, F# nebo VB.NET a Q# a vytvořte hostitelský program v .NET, který volá operace Q#.</span><span class="sxs-lookup"><span data-stu-id="5be10-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
