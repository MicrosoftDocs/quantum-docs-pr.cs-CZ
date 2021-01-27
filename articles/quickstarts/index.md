---
title: Nastavení sady Microsoft Quantum Development Kit (QDK)
description: Zjistěte, jak nastavit sadu Microsoft Quantum Development Kit pro různá prostředí.
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859030"
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

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><b>VS Code<br>(2019 nebo novější)</b></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><b>Visual Studio<br>(2019 nebo novější)</b></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><b>Poznámkové bloky Jupyter</b></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><b>Příkazový řádek</b></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><b>Podpora operačního systému:</b></td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Jen ve Windows</td>
        <td align="center">Windows, macOS, Linux</td>
        <td align="center">Windows, macOS, Linux</td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><b>Q# samostatně</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalace</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalace</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.jupyter">Instalace</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.standalone">Instalace</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><b>Q# a Python</b></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalace</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalace</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalace</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.python">Instalace</a></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><b>Q# a .NET (C#, F#)</b></td> 
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalace</a></td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalace</a></td>
        <td align="center">&#10006;</td>
        <td align="center"><a href="xref:microsoft.quantum.install.cs">Instalace</a></td>
   </tr>
</table>

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
