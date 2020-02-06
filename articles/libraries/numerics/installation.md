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
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="c9bdb-103">Instalace a ověření knihovny numerických a ověřovacích knihoven</span><span class="sxs-lookup"><span data-stu-id="c9bdb-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="c9bdb-104">Sada pro vývoj po dobu provozu poskytuje podporu pro funkce numerických funkcí prostřednictvím balíčku NuGet [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .</span><span class="sxs-lookup"><span data-stu-id="c9bdb-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="c9bdb-105">**Visual Studio > = 2019:** Pokud používáte sadu Visual Studio 2019 nebo novější, můžete přidat balíček numerických čísel pomocí Správce balíčků NuGet.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="c9bdb-106">Uděláte to tak, že vyberete spravovat balíčky NuGet... z položky nabídky projekt v aplikaci Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="c9bdb-107">Na kartě Procházet vyhledejte název balíčku "Microsoft. Numerics".</span><span class="sxs-lookup"><span data-stu-id="c9bdb-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="c9bdb-108">Ujistěte se, že zaškrtnete políčko zahrnout předběžné verze.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="c9bdb-109">Zobrazí se seznam balíčků, které jsou k dispozici ke stažení.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-109">This will list the packages available for download.</span></span>
<span data-ttu-id="c9bdb-110">Najetí myší na "Microsoft. propočty. numerické" "odhalí šipku směřující dolů napravo od čísla verze.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="c9bdb-111">Pro instalaci balíčku numerických součástí klikněte na šipku.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="c9bdb-112">Další podrobnosti najdete v příručce k [uživatelskému rozhraní Správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="c9bdb-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="c9bdb-113">Alternativně můžete použít konzolu Správce balíčků k přidání knihovny numerické aplikace do projektu prostřednictvím rozhraní příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](../../media/vs2017-nuget-console-menu.png)

<span data-ttu-id="c9bdb-114">V konzole správce balíčků spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="c9bdb-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="c9bdb-115">Další podrobnosti najdete v [Průvodci konzolou správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="c9bdb-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="c9bdb-116">**Příkazový řádek nebo Visual Studio Code:** Pomocí příkazového řádku na svém vlastním nebo z Visual Studio Code můžete pomocí příkazu `dotnet` přidat do projektu odkaz na balíček NuGet:</span><span class="sxs-lookup"><span data-stu-id="c9bdb-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="c9bdb-117">Ověření instalace</span><span class="sxs-lookup"><span data-stu-id="c9bdb-117">Verifying your installation</span></span>

<span data-ttu-id="c9bdb-118">Podobně jako v ostatních částech vývojové sady pro práci s více částmi obsahuje knihovna numerických verzí ukázky, které vám pomůžou začít co nejrychleji.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="c9bdb-119">K otestování instalace pomocí těchto ukázek naklonujte [hlavní úložiště ukázek](https://github.com/Microsoft/Quantum) a pak spusťte jednu z ukázek.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="c9bdb-120">Spuštění ukázky [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :</span><span class="sxs-lookup"><span data-stu-id="c9bdb-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
