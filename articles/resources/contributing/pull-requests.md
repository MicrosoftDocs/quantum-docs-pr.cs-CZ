---
title: Otevírání žádostí o přijetí změn
description: Přečtěte si, jak odeslat žádost o přijetí změn GitHubu, až budete připraveni přispívat k kódu nebo dokumentaci k Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: 82af3b5123588cc06882f746ffcb0402ad3f0f2e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274545"
---
# <a name="opening-pull-requests"></a>Otevírání žádostí o přijetí změn #

Veškerá dokumentace pro vývojová prostředí pro práci s více operačními systémy je spravovaná pomocí systému správy verzí Git prostřednictvím použití několika úložišť hostovaných na GitHubu.
Použití Gitu a GitHubu společně usnadňuje spolupráci s vývojovou sadou pro práci ve velkém rozsahu.
Konkrétně je možné klonovat nebo rozvětvit úložiště Git a vytvořit z něj zcela nezávislou kopii tohoto úložiště.
To vám umožní pracovat na svém příspěvku s nástroji a tempem, které dáváte přednost.

Až budete připraveni, můžete nám poslat žádost o zahrnutí vašeho příspěvku do našich úložišť, a to pomocí funkce _žádosti o_ přijetí změn GitHubu.
Stránka pro každou žádost o přijetí změn obsahuje podrobnosti o všech změnách, které přispívají k vašemu příspěvku, seznamu komentářů k vašemu příspěvku a sadě revizních nástrojů, které mohou jiní členové komunity využít k poskytování připomínek a rad.

> [!NOTE]
> Úplný kurz týkající se Gitu je nad rámec tohoto průvodce, můžeme navrhnout následující odkazy na další zdroje informací o studiu v Gitu:
>
> - [Seznámení s Git](https://www.atlassian.com/git): sada kurzů git z Atlassian.
> - Správa [verzí v Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): návod, jak používat Visual Studio Code jako grafické uživatelské rozhraní pro Git.
> - Vývojové [prostředí GitHubu](https://lab.github.com/): sada online kurzů pro používání Git, GitHubu a souvisejících technologií.
> - [Vizualizace Gitu](https://git-school.github.io/visualizing-git/): interaktivní nástroj pro vizualizaci, jak příkazy Gitu mění stav úložiště.
> - Správa [verzí pomocí Gitu (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): kurz Gitu orientovaný na vědecký výpočetní výkon.
> - [Seznámení s větvemi Git](https://learngitbranching.js.org/): interaktivní sada větví a přenesení puzzle, které vám pomůžou naučit nové funkce Gitu.

## <a name="what-is-a-pull-request"></a>Co je žádost o získání dat? ##

V takovém případě je užitečné, abyste si vyžádali, co **je**žádost o přijetí změn.
Při práci s Git se všechny změny reprezentují jako _potvrzení_ , které popisují, jak tyto změny souvisejí se stavem úložiště před těmito změnami.
Často vykreslíme diagramy, ve kterých se potvrzení vykreslí jako kružnice se šipkami z předchozích potvrzení.

Předpokládejme, že jste ve _větvi_ s názvem zahájili příspěvek `feature` .
Potom vaše rozvětvení **Microsoft/** nečinnosti může vypadat přibližně takto:

![Pracovní větev na GitHubu](~/media/git-workflow-step0.png)

Pokud provedete změny v místním úložišti, můžete si z jiného úložiště _Stáhnout_ změny, abyste mohli zachytit všechny změny, ke kterým došlo v opačném případě.

![Přijímání a slučování změn z nadřazeného úložiště](~/media/git-workflow-step1.png)

Žádosti o přijetí změn fungují stejným způsobem, ale v opačném případě: Když otevřete žádost o přijetí změn, zeptejte se, že má nadřazené úložiště získat příspěvek do služby.

![Vyžádání žádosti o přijetí změn zpátky do původního úložiště](~/media/git-workflow-step2.png)

Když v jednom z našich úložišť otevřete žádost o přijetí změn, GitHub nabídne ostatním uživatelům v komunitě možnost Zobrazit souhrn vašich změn, komentovat je a vytvořit návrhy, jak pomoci zajistit ještě lepší příspěvek.

![Snímek obrazovky žádosti o získání dat v GitHubu](~/media/pull-request-header.png)

Použití tohoto procesu nám pomáhá využít funkce GitHubu ke zlepšení příspěvků a udržování vysoce kvalitních produktů pro naši komunitu programování.

## <a name="how-to-make-a-pull-request"></a>Jak vytvořit žádost o získání dat ##

Existují dva hlavní způsoby, jak vytvořit žádost o získání dat.  
U malých změn, které ovlivňují jenom jeden soubor, se dá webové rozhraní GitHubu použít k úplnému Online podání žádosti o přijetí změn. Jednoduše přejděte k souboru, který chcete upravit, a použijte ikonu Upravit.  
U složitějších příspěvků je nejčastěji snazší naklonování úložiště do místního počítače, aby se nejdříve připravila žádost o získání dat.

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

## <a name="next-steps"></a>Další kroky ##

Gratulujeme k používání Git, které vám pomůžou využít komunitu pro vývoj na více instancích.
Pokud chcete získat další informace o tom, jak přispívat kód, pokračujte prosím v následující příručce.

> [!div class="nextstepaction"]
> [Informace o tom, jak přispívat kód](xref:microsoft.quantum.contributing.code)