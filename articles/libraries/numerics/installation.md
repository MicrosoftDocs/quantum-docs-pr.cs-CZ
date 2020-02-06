---
title: Instalace a ověření knihovny numerických a ověřovacích knihoven | Microsoft Docs
description: Instalace a ověření knihovny numerických a ověřovacích knihoven
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: c41bb73ea484271689eea2ca1b59ce6639dc15a7
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036453"
---
# <a name="numerics-library-installation-and-validation"></a>Instalace a ověření knihovny numerických a ověřovacích knihoven

Sada pro vývoj po dobu provozu poskytuje podporu pro funkce numerických funkcí prostřednictvím balíčku NuGet [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .

**Visual Studio > = 2019:** Pokud používáte sadu Visual Studio 2019 nebo novější, můžete přidat balíček numerických čísel pomocí Správce balíčků NuGet.
Uděláte to tak, že vyberete spravovat balíčky NuGet... z položky nabídky projekt v aplikaci Visual Studio.

Na kartě Procházet vyhledejte název balíčku "Microsoft. Numerics".

> [!NOTE]
> Ujistěte se, že zaškrtnete políčko zahrnout předběžné verze.

Zobrazí se seznam balíčků, které jsou k dispozici ke stažení.
Najetí myší na "Microsoft. propočty. numerické" "odhalí šipku směřující dolů napravo od čísla verze.
Pro instalaci balíčku numerických součástí klikněte na šipku.

Další podrobnosti najdete v příručce k [uživatelskému rozhraní Správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Alternativně můžete použít konzolu Správce balíčků k přidání knihovny numerické aplikace do projektu prostřednictvím rozhraní příkazového řádku.

![](../../media/vs2017-nuget-console-menu.png)

V konzole správce balíčků spusťte následující příkaz:

```
Install-Package Microsoft.Quantum.Numerics
```

Další podrobnosti najdete v [Průvodci konzolou správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Příkazový řádek nebo Visual Studio Code:** Pomocí příkazového řádku na svém vlastním nebo z Visual Studio Code můžete pomocí příkazu `dotnet` přidat do projektu odkaz na balíček NuGet:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Ověření instalace

Podobně jako v ostatních částech vývojové sady pro práci s více částmi obsahuje knihovna numerických verzí ukázky, které vám pomůžou začít co nejrychleji.
K otestování instalace pomocí těchto ukázek naklonujte [hlavní úložiště ukázek](https://github.com/Microsoft/Quantum) a pak spusťte jednu z ukázek.

Spuštění ukázky [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
