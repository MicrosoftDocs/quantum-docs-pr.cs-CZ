---
title: Otevírají se žádosti o přijetí změn | Microsoft Docs
description: Otevírání žádostí o přijetí změn
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: d70a0a0319d14cfdae4910b897733d77b236f2f9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183722"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="92873-103">Otevírání žádostí o přijetí změn</span><span class="sxs-lookup"><span data-stu-id="92873-103">Opening Pull Requests</span></span> #

<span data-ttu-id="92873-104">Veškerá dokumentace pro vývojová prostředí pro práci s více operačními systémy je spravovaná pomocí systému správy verzí Git prostřednictvím použití několika úložišť hostovaných na GitHubu.</span><span class="sxs-lookup"><span data-stu-id="92873-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="92873-105">Použití Gitu a GitHubu společně usnadňuje spolupráci s vývojovou sadou pro práci ve velkém rozsahu.</span><span class="sxs-lookup"><span data-stu-id="92873-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="92873-106">Konkrétně je možné klonovat nebo rozvětvit úložiště Git a vytvořit z něj zcela nezávislou kopii tohoto úložiště.</span><span class="sxs-lookup"><span data-stu-id="92873-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="92873-107">To vám umožní pracovat na svém příspěvku s nástroji a tempem, které dáváte přednost.</span><span class="sxs-lookup"><span data-stu-id="92873-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="92873-108">Až budete připraveni, můžete nám poslat žádost o zahrnutí vašeho příspěvku do našich úložišť, a to pomocí funkce _žádosti o_ přijetí změn GitHubu.</span><span class="sxs-lookup"><span data-stu-id="92873-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="92873-109">Stránka pro každou žádost o přijetí změn obsahuje podrobnosti o všech změnách, které přispívají k vašemu příspěvku, seznamu komentářů k vašemu příspěvku a sadě revizních nástrojů, které mohou jiní členové komunity využít k poskytování připomínek a rad.</span><span class="sxs-lookup"><span data-stu-id="92873-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="92873-110">Úplný kurz týkající se Gitu je nad rámec tohoto průvodce, můžeme navrhnout následující odkazy na další zdroje informací o studiu v Gitu:</span><span class="sxs-lookup"><span data-stu-id="92873-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="92873-111">[Seznámení s Git](https://www.atlassian.com/git): sada kurzů git z Atlassian.</span><span class="sxs-lookup"><span data-stu-id="92873-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="92873-112">Správa [verzí v Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): návod, jak používat Visual Studio Code jako grafické uživatelské rozhraní pro Git.</span><span class="sxs-lookup"><span data-stu-id="92873-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="92873-113">Vývojové [prostředí GitHubu](https://lab.github.com/): sada online kurzů pro používání Git, GitHubu a souvisejících technologií.</span><span class="sxs-lookup"><span data-stu-id="92873-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="92873-114">[Vizualizace Gitu](https://git-school.github.io/visualizing-git/): interaktivní nástroj pro vizualizaci, jak příkazy Gitu mění stav úložiště.</span><span class="sxs-lookup"><span data-stu-id="92873-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="92873-115">Správa [verzí pomocí Gitu (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): kurz Gitu orientovaný na vědecký výpočetní výkon.</span><span class="sxs-lookup"><span data-stu-id="92873-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="92873-116">[Seznámení s větvemi Git](https://learngitbranching.js.org/): interaktivní sada větví a přenesení puzzle, které vám pomůžou naučit nové funkce Gitu.</span><span class="sxs-lookup"><span data-stu-id="92873-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="92873-117">Co je žádost o získání dat?</span><span class="sxs-lookup"><span data-stu-id="92873-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="92873-118">V takovém případě je užitečné, abyste si vyžádali, co **je**žádost o přijetí změn.</span><span class="sxs-lookup"><span data-stu-id="92873-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="92873-119">Při práci s Git se všechny změny reprezentují jako _potvrzení_ , které popisují, jak tyto změny souvisejí se stavem úložiště před těmito změnami.</span><span class="sxs-lookup"><span data-stu-id="92873-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="92873-120">Často vykreslíme diagramy, ve kterých se potvrzení vykreslí jako kružnice se šipkami z předchozích potvrzení.</span><span class="sxs-lookup"><span data-stu-id="92873-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="92873-121">Předpokládejme, že jste na _větvi_ s názvem `feature`zahájili příspěvek.</span><span class="sxs-lookup"><span data-stu-id="92873-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="92873-122">Potom vaše rozvětvení **Microsoft/** nečinnosti může vypadat přibližně takto:</span><span class="sxs-lookup"><span data-stu-id="92873-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![](~/media/git-workflow-step0.png)

<span data-ttu-id="92873-123">Pokud provedete změny v místním úložišti, můžete si z jiného úložiště _Stáhnout_ změny, abyste mohli zachytit všechny změny, ke kterým došlo v opačném případě.</span><span class="sxs-lookup"><span data-stu-id="92873-123">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![](~/media/git-workflow-step1.png)

<span data-ttu-id="92873-124">Žádosti o přijetí změn fungují stejným způsobem, ale v opačném případě: Když otevřete žádost o přijetí změn, zeptejte se, že má nadřazené úložiště získat příspěvek do služby.</span><span class="sxs-lookup"><span data-stu-id="92873-124">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![](~/media/git-workflow-step2.png)

<span data-ttu-id="92873-125">Když v jednom z našich úložišť otevřete žádost o přijetí změn, GitHub nabídne ostatním uživatelům v komunitě možnost Zobrazit souhrn vašich změn, komentovat je a vytvořit návrhy, jak pomoci zajistit ještě lepší příspěvek.</span><span class="sxs-lookup"><span data-stu-id="92873-125">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![](~/media/pull-request-header.png)

<span data-ttu-id="92873-126">Použití tohoto procesu nám pomáhá využít funkce GitHubu ke zlepšení příspěvků a udržování vysoce kvalitních produktů pro naši komunitu programování.</span><span class="sxs-lookup"><span data-stu-id="92873-126">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="92873-127">Jak vytvořit žádost o získání dat</span><span class="sxs-lookup"><span data-stu-id="92873-127">How to Make a Pull Request</span></span> ##

<span data-ttu-id="92873-128">Existují dva hlavní způsoby, jak vytvořit žádost o získání dat.</span><span class="sxs-lookup"><span data-stu-id="92873-128">There are two main ways to make a pull request.</span></span>
<span data-ttu-id="92873-129">U malých změn, které ovlivňují jenom jeden soubor, se dá webové rozhraní GitHubu použít k úplnému Online podání žádosti o přijetí změn.</span><span class="sxs-lookup"><span data-stu-id="92873-129">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span>
<span data-ttu-id="92873-130">U složitějších příspěvků je nejčastěji snazší použít místní počítač k přípravě žádosti o přijetí změn.</span><span class="sxs-lookup"><span data-stu-id="92873-130">For more complicated contributions, it's most often easier to use your local computer to prepare for a pull request first.</span></span>

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a><span data-ttu-id="92873-131">Další kroky</span><span class="sxs-lookup"><span data-stu-id="92873-131">Next steps</span></span> ##

<span data-ttu-id="92873-132">Gratulujeme k používání Git, které vám pomůžou využít komunitu pro vývoj na více instancích.</span><span class="sxs-lookup"><span data-stu-id="92873-132">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="92873-133">Pokud chcete získat další informace o tom, jak přispívat kód, pokračujte prosím v následující příručce.</span><span class="sxs-lookup"><span data-stu-id="92873-133">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92873-134">Informace o tom, jak přispívat kód</span><span class="sxs-lookup"><span data-stu-id="92873-134">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)