---
title: Knihovna numerických procesorů Microsoft – instalace a ověření
description: Naučte se, jak do instalace sady Visual Studio 2019 nebo novější přidat knihovnu Microsoft pro počet nestejných čísel.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274702"
---
# <a name="numerics-library-installation-and-validation"></a>Instalace a ověření knihovny numerických a ověřovacích knihoven

Sada pro vývoj pro všechna ta poskytuje podporu numerických funkcí prostřednictvím [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) balíčku NuGet.

**Visual Studio >= 2019:** Pokud používáte sadu Visual Studio 2019 nebo novější, můžete přidat balíček numerických čísel pomocí Správce balíčků NuGet.
Uděláte to tak, že vyberete spravovat balíčky NuGet... z položky nabídky projekt v aplikaci Visual Studio.

Na kartě Procházet vyhledejte název balíčku "Microsoft.. Numerics".

> [!NOTE]
> Ujistěte se, že zaškrtnete políčko zahrnout předběžné verze.

Zobrazí se seznam balíčků, které jsou k dispozici ke stažení.
Najetí myší na "Microsoft. propočty. numerické" "odhalí šipku směřující dolů napravo od čísla verze.
Pro instalaci balíčku numerických součástí klikněte na šipku.

Další podrobnosti najdete v příručce k [uživatelskému rozhraní Správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternativně můžete použít konzolu Správce balíčků k přidání knihovny numerické aplikace do projektu prostřednictvím rozhraní příkazového řádku.

![Použití konzoly Správce balíčků z příkazového řádku](~/media/vs2017-nuget-console-menu.png)

V konzole správce balíčků spusťte následující příkaz:

```
Install-Package Microsoft.Quantum.Numerics
```

Další podrobnosti najdete v [Průvodci konzolou správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Příkazový řádek nebo Visual Studio Code:** Pomocí příkazového řádku na svém vlastním nebo z Visual Studio Code můžete pomocí `dotnet` příkazu přidat do projektu odkaz na balíček NuGet:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Ověření instalace

Podobně jako v ostatních částech vývojové sady pro práci s více částmi obsahuje knihovna numerických verzí ukázky, které vám pomůžou začít co nejrychleji.
K otestování instalace pomocí těchto ukázek naklonujte [hlavní úložiště ukázek](https://github.com/Microsoft/Quantum) a pak spusťte jednu z ukázek.

Spuštění [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) ukázky:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
