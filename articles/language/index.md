---
title: Programovací jazyk Q#
description: Seznámení s jazykem Q# pro vývoj kvantových programů
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: b62e6866fc3609d95c26a5eab2a6eac325dfe330
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907371"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="43366-103">Programovací jazyk Q#</span><span class="sxs-lookup"><span data-stu-id="43366-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="43366-104">Úvod</span><span class="sxs-lookup"><span data-stu-id="43366-104">Introduction</span></span>

<span data-ttu-id="43366-105">Přirozeným modelem pro kvantové výpočty je přistupovat ke kvantovému počítači jako ke koprocesoru podobnému těm, které se používají s grafickými procesory, programovatelnými hradlovými poli (FPGA) a dalšími pomocnými procesory.</span><span class="sxs-lookup"><span data-stu-id="43366-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="43366-106">Primární řídicí logika spouští klasický kód v klasickém „hostitelském“ počítači.</span><span class="sxs-lookup"><span data-stu-id="43366-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="43366-107">Když je to vhodné a potřebné, hostitelský program může vyvolat subrutinu, která běží na pomocném procesoru.</span><span class="sxs-lookup"><span data-stu-id="43366-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="43366-108">Po dokončení provádění subrutiny získá hostitelský program přístup k jejím výsledkům.</span><span class="sxs-lookup"><span data-stu-id="43366-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="43366-109">Q# je programovací jazyk specifický pro konkrétní doménu, který se používá k vyjadřování kvantových algoritmů.</span><span class="sxs-lookup"><span data-stu-id="43366-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="43366-110">Slouží k psaní subrutin, které se spouštějí na pomocném kvantovém procesoru a jsou řízeny klasickým hostitelským programem a počítačem.</span><span class="sxs-lookup"><span data-stu-id="43366-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="43366-111">Dokud nebudou kvantové procesory běžně k dispozici, budou se subrutiny v jazyku Q# spouštět v simulátoru.</span><span class="sxs-lookup"><span data-stu-id="43366-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="43366-112">Jazyk Q# poskytuje malou množinu primitivních typů a také dva způsoby (pole a řazené kolekce členů) vytváření nových strukturovaných typů.</span><span class="sxs-lookup"><span data-stu-id="43366-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="43366-113">Podporuje základní procedurální model pro psaní programů se smyčkami a příkazy if/then.</span><span class="sxs-lookup"><span data-stu-id="43366-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="43366-114">Konstrukty nejvyšší úrovně v jazyku Q# jsou uživatelsky definované typy, operace a funkce.</span><span class="sxs-lookup"><span data-stu-id="43366-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="43366-115">V následujících částech jsou podrobně vysvětlena tato témata:</span><span class="sxs-lookup"><span data-stu-id="43366-115">The following sections detail:</span></span>
- [<span data-ttu-id="43366-116">Model typů</span><span class="sxs-lookup"><span data-stu-id="43366-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="43366-117">Výrazy</span><span class="sxs-lookup"><span data-stu-id="43366-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="43366-118">Příkazy</span><span class="sxs-lookup"><span data-stu-id="43366-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="43366-119">Struktura souborů</span><span class="sxs-lookup"><span data-stu-id="43366-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="43366-120">Zásady</span><span class="sxs-lookup"><span data-stu-id="43366-120">Conventions</span></span>

<span data-ttu-id="43366-121">Snažíme se zajistit, aby se ve všech situacích konzistentně používaly běžná interpunkční znaménka.</span><span class="sxs-lookup"><span data-stu-id="43366-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="43366-122">Očekáváme, že díky tomu bude snazší naučit se jazyk Q# a číst ho, protože tato znaménka znamenají vždy totéž a stejná koncepce je vždy reprezentována stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="43366-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="43366-123">Konkrétně:</span><span class="sxs-lookup"><span data-stu-id="43366-123">Specifically:</span></span>

- <span data-ttu-id="43366-124">Středník (`;`) slouží k ukončení příkazu nebo jednořádkové direktivy.</span><span class="sxs-lookup"><span data-stu-id="43366-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="43366-125">Nepoužívá se k žádným jiným účelům.</span><span class="sxs-lookup"><span data-stu-id="43366-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="43366-126">Čárka (`,`) slouží k oddělení prvků posloupnosti.</span><span class="sxs-lookup"><span data-stu-id="43366-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="43366-127">Používá se pro literály řazené kolekce členů, literály pole, seznamy argumentů, definice řazených kolekcí členů a seznamy typů.</span><span class="sxs-lookup"><span data-stu-id="43366-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="43366-128">**Na rozdíl od dřívějších verzí již znak `;` není podporován jako oddělovač literálů pole.**</span><span class="sxs-lookup"><span data-stu-id="43366-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="43366-129">Dvojtečka (`:`) slouží k uvedení anotace typu.</span><span class="sxs-lookup"><span data-stu-id="43366-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="43366-130">Používá se primárně v signaturách, které lze volat.</span><span class="sxs-lookup"><span data-stu-id="43366-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="43366-131">Vzhledem k tomu, že dvojtečka vždy uvádí signaturu typu, ternární podmíněný operátor zavedený ve verzi 0.3 používá svislou čáru (`|`) pro oddělení hodnot true a false; jazyk Q# proto používá namísto dvojtečky oddělovač `cond ? tval | fval` jako v jazyku C.</span><span class="sxs-lookup"><span data-stu-id="43366-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
