---
title: Použití dalších Q# knihoven
description: Naučte se, jak přidat další Q# knihovny do vašich aplikací pro vlastníce.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: c558e25bf0d906ba6480cd7c41d3ece4ea97c2d1
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863089"
---
# <a name="using-additional-no-locq-libraries"></a>Použití dalších Q# knihoven

Sada pro vývoj všech procesorů poskytuje další funkce specifické pro doménu prostřednictvím _balíčků NuGet_ , které je možné přidat do vašich Q# projektů.

| Q# Knihovna  | Balíček NuGet | Poznámky |
|---------|---------|--------|
| [Q# Standardní knihovna](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. nestandardní**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Zahrnuto ve výchozím nastavení |
| [Kvantová chemická knihovna](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Kvantová numerická knihovna](xref:microsoft.quantum.numerics.intro) | [**Microsoft.... NUMERIC**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Knihovna pro kvantové strojové učení](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

Jakmile nainstalujete sadu pro vývoj všech automobilů pro použití s preferovaným prostředím a jazykem hostitele, můžete snadno přidávat knihovny do jednotlivých Q# projektů bez nutnosti další instalace.

> [!NOTE]
> Některé Q# knihovny můžou fungovat dobře s dalšími nástroji, které fungují společně Q# s vašimi programy, nebo které se integrují s vašimi hostitelskými aplikacemi.
> Například [pokyny k instalaci knihovny chemického](xref:microsoft.quantum.chemistry.concepts.installation) zpracování popisují, jak použít balíček [ **Microsoft. NWChem. chemie** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) společně s platformou výpočetních dat a jak nainstalovat `qdk-chem` nástroje příkazového řádku pro práci s daty ze chemie.

## <a name="no-locq-applications-or-net-interopability"></a>[Q# aplikace nebo interoperabilita rozhraní .NET](#tab/tabid-csproj)

**Příkazový řádek nebo Visual Studio Code:** Pomocí příkazového řádku vlastní nebo v rámci Visual Studio Code můžete pomocí `dotnet` příkazu přidat do projektu odkaz na balíček NuGet.
Pokud například chcete přidat balíček [**Microsoft. probíhat. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) , spusťte následující příkaz:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Pokud používáte sadu Visual Studio 2019 nebo novější, můžete přidat další Q# balíčky pomocí Správce balíčků NuGet.
Načtení balíčku: 
1. Otevřete projekt v aplikaci Visual Studio a v nabídce **projekt** vyberte **Spravovat balíčky NuGet...**

2. Klikněte na tlačítko **Procházet**, vyberte možnost **Zahrnout předprodejní** a vyhledejte název balíčku "Microsoft..... Numerics". Zobrazí se seznam balíčků, které jsou k dispozici ke stažení.

3. Najeďte myší na **Microsoft. propočty. čísel** a kliknutím na šipku dolů napravo od čísla verze nainstalujte balíček numerických verzí.

Další podrobnosti najdete v příručce k [uživatelskému rozhraní Správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternativně můžete použít konzolu Správce balíčků k přidání knihovny numerické aplikace do projektu prostřednictvím rozhraní příkazového řádku.

![Použití konzoly Správce balíčků z příkazového řádku](~/media/vs2017-nuget-console-menu.png)

V konzole správce balíčků spusťte následující příkaz:

```
Install-Package Microsoft.Quantum.Numerics
```

Další podrobnosti najdete v [Průvodci konzolou správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="ino-locq-notebooks"></a>[I Q# poznámkové bloky](#tab/tabid-notebook)

Další balíčky můžete zpřístupnit pro použití v Q# poznámkovém bloku pomocí [ `%package` příkazu Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).
Pokud například chcete přidat balíček [**Microsoft. probíhat. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) pro použití v Q# poznámkovém bloku, spusťte následující příkaz v buňce s poznámkovým blokem:

```
%package Microsoft.Quantum.Numerics
```

Po tomto příkazu je balíček dostupný pro všechny buňky v poznámkovém bloku.
Pokud chcete balíček zpřístupnit z Q# kódu v aktuálním pracovním prostoru, po přidání balíčku znovu načtěte tento pracovní prostor:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Interoperabilita Pythonu](#tab/tabid-python)


Další balíčky můžete zpřístupnit pro použití v hostitelském programu Pythonu pomocí [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) metody.
Pokud například chcete přidat balíček [**Microsoft. probíhat. Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) pro použití v Q# poznámkovém bloku, spusťte následující kód Pythonu:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Po provedení tohoto příkazu bude balíček dostupný pro jakýkoli Q# kód kompilovaný pomocí `qsharp.compile` .
Pokud chcete balíček zpřístupnit z Q# kódu v aktuálním pracovním prostoru, po přidání balíčku znovu načtěte tento pracovní prostor:

```python
qsharp.reload()
```

***
