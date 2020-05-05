---
title: Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK)
description: Jak nainstalovat sadu Microsoft Quantum Development Kit pro C#, Python a prostředí Jupyter Notebook
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680193"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="81361-103">Instalace sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="81361-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="81361-104">Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním.</span><span class="sxs-lookup"><span data-stu-id="81361-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="81361-105">Sada QDK obsahuje tyto komponenty:</span><span class="sxs-lookup"><span data-stu-id="81361-105">The QDK consists of:</span></span>

- <span data-ttu-id="81361-106">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="81361-106">the Q# programming language</span></span>
- <span data-ttu-id="81361-107">Sada knihoven s abstraktními komplexními funkcemi v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="81361-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="81361-108">Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#</span><span class="sxs-lookup"><span data-stu-id="81361-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="81361-109">Nástroje pro usnadnění vývoje</span><span class="sxs-lookup"><span data-stu-id="81361-109">tools to facilitate your development</span></span>

<span data-ttu-id="81361-110">Programy v Q# jsou často spárovány s hostitelským programem napsaným v jazyce .NET (obvykle C#) nebo Pythonu.</span><span class="sxs-lookup"><span data-stu-id="81361-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="81361-111">Díky tomu můžeme volat kvantové operace v rámci klasického programu.</span><span class="sxs-lookup"><span data-stu-id="81361-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="81361-112">Kromě toho sada QDK poskytuje podporu Q# pro poznámkové bloky Jupyter s jádrem IQ# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="81361-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="81361-113">Sada QDK je k dispozici pro víc vývojových prostředí.</span><span class="sxs-lookup"><span data-stu-id="81361-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="81361-114">Z následujících částí vyberte upřednostňovanou instalaci:</span><span class="sxs-lookup"><span data-stu-id="81361-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="81361-115">[Aplikace příkazového řádku v Q#:](xref:microsoft.quantum.install.standalone) Tento přístup zvolte, když chcete pracovat s jazykem Q# z příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="81361-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="81361-116">Tato možnost nevyžaduje ovladač ani hostitelský program jako následující možnosti.</span><span class="sxs-lookup"><span data-stu-id="81361-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="81361-117">[Instalace Q # pro poznámkové bloky Jupyter:](xref:microsoft.quantum.install.jupyter) Toto prostředí vyberte, pokud chcete spouštět kód Q# v buňkách s vloženým textem nebo vytvořit interaktivní kurzy kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="81361-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="81361-118">[Vývoj s využitím Q# a Pythonu:](xref:microsoft.quantum.install.python) Toto prostředí vyberte, pokud chcete kombinací jazyků Python a Q# vytvořit hostitelský program v Pythonu, který volá operace v Q#.</span><span class="sxs-lookup"><span data-stu-id="81361-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="81361-119">[Vývoj s využitím Q# a C# nebo F#:](xref:microsoft.quantum.install.cs) Toto prostředí vyberte, pokud chcete kombinací jazyků C# nebo F# a Q# vytvořit hostitelský program v .NET, který volá operace v Q#.</span><span class="sxs-lookup"><span data-stu-id="81361-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
