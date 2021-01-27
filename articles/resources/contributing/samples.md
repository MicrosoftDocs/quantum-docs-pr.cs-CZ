---
title: Přispívání ukázek do Microsoft QDK
description: Naučte se, jak přispívat vzorový kód do Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0c940a4cf228c694a899988f469158b1bb6e2425
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847586"
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

To znamená, že ukázky v [úložišti Microsoft/](https://github.com/microsoft/Quantum) probíhají v členění podle oblasti předmětu do různých složek, například `algorithms/` , `arithmetic/` nebo `characterization/` .
Každá ukázka v rámci složky pro každou oblast obsahuje jednu složku, která shromažďuje vše, co si uživatel bude muset prozkoumat a použít tuto ukázku.

## <a name="how-samples-are-structured"></a>Princip strukturování ukázek

Podívejte se na soubory, které tvoří každou složku, a pojďme se podrobně do [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) ukázky.

| Soubor              | Popis                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q# projekt použitý k sestavení ukázky s .NET Core SDK |
| `Game.qs`         | Q# operace a funkce pro ukázku                 |
| `Host.cs`         | Hostitelský program C# použitý ke spuštění ukázky                     |
| `host.py`         | Hostitelský program Pythonu použitý ke spuštění ukázky                 |
| `README.md`       | Dokumentace k tomu, co ukázka dělá a jak ji používat    |

Ne všechny vzorky budou mít přesně stejnou sadu souborů (například: některé ukázky mohou být pouze C#, ostatní nemusí mít hostitele v Pythonu nebo některé ukázky mohou vyžadovat, aby auxillary datové soubory fungovaly).

## <a name="anatomy-of-a-helpful-readme-file"></a>Anatomie užitečného souboru READme

Jedním z zvláště důležitých souborů je, že se jedná o `README.md` soubor, jak si uživatelé musí začít s ukázkou.

Každý `README.md` by měl začít s některými metadaty, které pomáhají docs.Microsoft.com/Samples najít váš příspěvek.

> [!div class="nextstepaction"]
> [Podívejte se, jak se vykresluje ukázka chsh-Game.](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Tato metadata jsou k dispozici jako [YAML záhlaví](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) , které určuje, jaké jazyky vaše ukázka pokrývá (obvykle se jedná o `qsharp` , `csharp` a `python` ) a jaké produkty vaše ukázka pokrývá (obvykle `qdk` ).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample`Klíč v hlavičce je vyžadován, aby se ukázka zobrazovala na docs.Microsoft.com/Samples.
> Podobně `product` `language` jsou klíče a důležité pro pomoc uživatelům při hledání a spuštění ukázky.

Pak je užitečné poskytnout krátký úvod, který říká, co dělá vaše nová Ukázka:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Uživatelé vaší ukázky budou také považovat za znalosti toho, co potřebují ke spuštění (např.: uživatelé potřebují jenom vývojářskou sadu pro vývoj, nebo potřebují další software, například node.js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

U všech to je tak možné sdělit uživatelům, jak spustit ukázku:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Nakonec je vhodné sdělit uživatelům, co každý soubor ve vaší ukázce dělá, a kde můžou získat další informace:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Nezapomeňte místo toho použít absolutní adresy URL, protože se při vykreslování na docs.microsoft.com/samples zobrazí vaše ukázka na jiné adrese URL.
