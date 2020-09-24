---
title: Nastavení sady Microsoft Quantum Development Kit (QDK)
description: Zjistěte, jak nastavit sadu Microsoft Quantum Development Kit pro různá prostředí.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834478"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a>Nastavení sady Microsoft Quantum Development Kit (QDK)

Naučte se nastavit sadu Microsoft Quantum Development Kit (QDK) pro vaše prostředí, abyste mohli začít s kvantovým programováním. Sada QDK obsahuje tyto komponenty:

- Programovací jazyk Q#
- Sada knihoven, které abstrahují komplexní funkce v Q#
- Rozhraní API pro jazyky Python a .NET (C#, F# a VB.NET) pro spouštění kvantových programů napsaných v Q#
- Nástroje pro usnadnění vývoje

Programy v Q# je možné spustit jako samostatné aplikace s využitím nástroje Visual Studio Code nebo sady Visual Studio, prostřednictvím aplikací Jupyter Notebook s jádrem IQ# Jupyter nebo spárované s hostitelským programem napsaným v Pythonu nebo v jazyce .NET (C#, F#). Programy v Q# můžete také spouštět online s využitím [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/) nebo [Dockeru](#use-the-qdk-with-docker). 

## <a name="options-for-setting-up-the-qdk"></a>Možnosti pro nastavení QDK

Sadu QDK můžete využít třemi způsoby:

- [Místní instalace sady QDK](#install-the-qdk-locally)
- [Použití sady QDK online](#use-the-qdk-online)
- [Použití image Dockeru pro QDK](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a>Místní instalace sady QDK

Kód v Q# můžete vyvíjet ve většině oblíbených integrovaných vývojových prostředí. Q# se dá také integrovat s dalšími jazyky, jako je Python a .NET (C#, F#).

|&nbsp; | **VS Code<br>(2019 nebo novější)**| **Visual Studio<br>(2019 nebo novější)** | **Poznámkové bloky Jupyter** | **Příkazový řádek**|
|:-----|:-----:|:-----:|:-----:|:-----:|
|**OS** |Windows, macOS, Linux |Jen ve Windows |Windows, macOS, Linux |Windows, macOS, Linux |
|<br>**Q# samostatně** |<br>[Instalace](xref:microsoft.quantum.install.standalone) |<br> [Instalace](xref:microsoft.quantum.install.standalone)  |<br> [Instalace](xref:microsoft.quantum.install.jupyter) |<br>[Instalace](xref:microsoft.quantum.install.standalone)|
|**Q# a Python** |[Instalace](xref:microsoft.quantum.install.python) |[Instalace](xref:microsoft.quantum.install.python) |[Instalace](xref:microsoft.quantum.install.jupyter) |[Instalace](xref:microsoft.quantum.install.python) |
|**Q# a .NET (C#, F#)**|[Instalace](xref:microsoft.quantum.install.cs) |[Instalace](xref:microsoft.quantum.install.cs)|&#10006; |[Instalace](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a>Použití sady QDK online

Pomocí následujících možností můžete také vyvíjet kód v Q#, aniž byste v místním prostředí cokoli instalovali:

|Prostředek|Výhody|Omezení|
|---|---|---|
|[**Visual Studio Codespaces**](xref:microsoft.quantum.install.standalone)|Bohaté vývojové prostředí online  |Vyžaduje plán a předplatné Azure. |
|[**Binder**](xref:microsoft.quantum.install.binder) | Bezplatné online prostředí poznámkových bloků |Bez trvalosti |

## <a name="use-the-qdk-with-docker"></a>Použití sady QDK s Dockerem

Naši image Dockeru pro QDK můžete využít v místní instalaci Dockeru nebo v cloudu prostřednictvím libovolné knihovny, která podporuje image Dockeru, například ACI.

Image Dockeru pro IQ# si můžete stáhnout tady: https://github.com/microsoft/iqsharp/#using-iq-as-a-container. 

Docker můžete také využít spolu se vzdáleným vývojovým kontejnerem nástroje Visual Studio Code k rychlému definování vývojových prostředí. Další informace o vývojových kontejnerech nástroje VS Code najdete tady: https://github.com/microsoft/Quantum/tree/master/.devcontainer.

## <a name="next-steps"></a>Další kroky

Pracovní postupy pro každé z těchto nastavení jsou popsány a porovnány v tématu [Způsoby spuštění programu v Q#](xref:microsoft.quantum.guide.host-programs).
