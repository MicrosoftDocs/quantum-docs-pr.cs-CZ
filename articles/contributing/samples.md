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
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Přispívání ukázek do vývojové sady pro všechna ta

Pokud vás zajímá přispívání kódu do [úložiště ukázek](https://github.com/Microsoft/Quantum), Děkujeme za to, že komunita pro vývoj všech stavů je lepší.

## <a name="the-quantum-development-kit-samples-repository"></a>Úložiště ukázek pro danou sadu pro vývojová prostředí

Abychom vám pomohli připravit váš příspěvek tak, aby co nejvíce pomohl, je vhodné si rychle prohlédnout, jak je úložiště ukázek vymezeno:

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

To znamená, že ukázky v [úložišti Microsoft/](https://github.com/microsoft/Quantum) probíhají v členění podle oblasti předmětu do různých složek, jako je `algorithms/`, `arithmetic/`nebo `characterization/`.
Každá ukázka v rámci složky pro každou oblast obsahuje jednu složku, která shromažďuje vše, co si uživatel bude muset prozkoumat a použít tuto ukázku.

## <a name="how-samples-are-structured"></a>Princip strukturování ukázek

Podívejte se na soubory, které tvoří každou složku, a pojďme se podrobně na ukázku [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) .

| File              | Popis                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Projekt Q # použitý k sestavení ukázky s .NET Core SDK |
| `Game.qs`         | Operace a funkce Q # pro ukázku                 |
| `Host.cs`         | C#hostitelský program použitý ke spuštění ukázky                     |
| `host.py`         | Hostitelský program Pythonu použitý ke spuštění ukázky                 |
| `README.md`       | Dokumentace k tomu, co ukázka dělá a jak ji používat    |

Ne všechny ukázky budou mít přesně stejnou sadu souborů (např.: některé ukázky můžou být C#pouze v případě, že jiné můžou mít hostitele v Pythonu nebo některé ukázky mohou vyžadovat, aby soubory auxillary data fungovaly).

## <a name="anatomy-of-a-helpful-readme-file"></a>Anatomie užitečného souboru READme

Jedním z zvláště důležitých souborů je ale `README.md` soubor, jak si uživatelé musí začít s ukázkou.

Každý `README.md` by měl začít s některými metadaty, které pomáhají docs.microsoft.com/samples najít váš příspěvek.

> [!div class="nextstepaction"]
> [Podívejte se, jak se vykresluje ukázka chsh-Game.](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Tato metadata se poskytují jako [YAML záhlaví](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) , které určuje, jaké jazyky vaše ukázka pokrývá (obvykle se `qsharp`, `csharp`a `python`) a jaké produkty vaše ukázka pokrývá (obvykle jenom `qdk`).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> Pro zobrazení ukázky na docs.microsoft.com/samples se vyžaduje klíč `page_type: sample` v hlavičce.
> Podobně jsou klíče `product` a `language` důležité pro pomoc uživatelům při hledání a spouštění ukázky.

Pak je užitečné poskytnout krátký úvod, který říká, co dělá vaše nová Ukázka:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Uživatelé vaší ukázky budou také považovat za informace o tom, co potřebují ke spuštění (např.: uživatelé potřebují jenom vývojářskou vývojovou sadu, nebo potřebují další software, jako je Node. js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

U všech to je tak možné sdělit uživatelům, jak spustit ukázku:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Nakonec je vhodné sdělit uživatelům, co každý soubor ve vaší ukázce dělá, a kde můžou získat další informace:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Nezapomeňte místo toho použít absolutní adresy URL, protože se při vykreslování na docs.microsoft.com/samples zobrazí vaše ukázka na jiné adrese URL.
