---
title: Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK)
description: Jak nainstalovat sadu Microsoft Quantum Development Kit pro C#, Python a prostředí Jupyter Notebook
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 5fafb736f34d27f9233370a0a8a66c0613606048
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/13/2020
ms.locfileid: "77904770"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="14bb7-103">Instalace sady Microsoft Quantum Development Kit (QDK)</span><span class="sxs-lookup"><span data-stu-id="14bb7-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="14bb7-104">Naučte se nainstalovat sadu Microsoft Quantum Development Kit (QDK), abyste mohli začít s kvantovým programováním.</span><span class="sxs-lookup"><span data-stu-id="14bb7-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="14bb7-105">Sada QDK obsahuje tyto komponenty:</span><span class="sxs-lookup"><span data-stu-id="14bb7-105">The QDK consists of:</span></span>

- <span data-ttu-id="14bb7-106">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="14bb7-106">the Q# programming language</span></span>
- <span data-ttu-id="14bb7-107">Sada knihoven s abstraktními komplexními funkcemi v jazyku Q#</span><span class="sxs-lookup"><span data-stu-id="14bb7-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="14bb7-108">Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#</span><span class="sxs-lookup"><span data-stu-id="14bb7-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="14bb7-109">Nástroje pro usnadnění vývoje</span><span class="sxs-lookup"><span data-stu-id="14bb7-109">tools to facilitate your development</span></span>

<span data-ttu-id="14bb7-110">Programy v Q# jsou často spárovány s hostitelským programem napsaným v jazyce .NET (obvykle C#) nebo Pythonu.</span><span class="sxs-lookup"><span data-stu-id="14bb7-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="14bb7-111">Díky tomu můžeme volat kvantové operace v rámci klasického programu.</span><span class="sxs-lookup"><span data-stu-id="14bb7-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="14bb7-112">Kromě toho sada QDK poskytuje podporu Q# pro poznámkové bloky Jupyter s jádrem IQ# Jupyter.</span><span class="sxs-lookup"><span data-stu-id="14bb7-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="14bb7-113">Sada QDK je k dispozici pro víc vývojových prostředí.</span><span class="sxs-lookup"><span data-stu-id="14bb7-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="14bb7-114">Z následujících částí vyberte upřednostňovanou instalaci:</span><span class="sxs-lookup"><span data-stu-id="14bb7-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="14bb7-115">[Instalace Q# pro C#:](xref:microsoft.quantum.install.cs) Toto prostředí vyberte, pokud chcete kombinací jazyků C# a Q# vytvořit hostitelský program v C#, který volá operace v Q#.</span><span class="sxs-lookup"><span data-stu-id="14bb7-115">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="14bb7-116">[Instalace Q# pro Python:](xref:microsoft.quantum.install.python) Toto prostředí vyberte, pokud chcete kombinací jazyků Python a Q# vytvořit hostitelský program v Pythonu, který volá operace v Q#.</span><span class="sxs-lookup"><span data-stu-id="14bb7-116">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="14bb7-117">[Instalace Q # pro poznámkové bloky Jupyter:](xref:microsoft.quantum.install.jupyter) Toto prostředí vyberte, pokud chcete spouštět kód Q# v buňkách s vloženým textem nebo vytvořit interaktivní kurzy kvantových výpočtů.</span><span class="sxs-lookup"><span data-stu-id="14bb7-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="14bb7-118">Nevybírejte toto prostředí, pokud chcete kombinovat Q# s externím klasickým hostitelským programem.</span><span class="sxs-lookup"><span data-stu-id="14bb7-118">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
