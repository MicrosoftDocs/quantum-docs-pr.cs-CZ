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
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="6e516-103">Instalace a ověření knihovny numerických a ověřovacích knihoven</span><span class="sxs-lookup"><span data-stu-id="6e516-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="6e516-104">Sada pro vývoj pro všechna ta poskytuje podporu numerických funkcí prostřednictvím [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) balíčku NuGet.</span><span class="sxs-lookup"><span data-stu-id="6e516-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="6e516-105">**Visual Studio >= 2019:** Pokud používáte sadu Visual Studio 2019 nebo novější, můžete přidat balíček numerických čísel pomocí Správce balíčků NuGet.</span><span class="sxs-lookup"><span data-stu-id="6e516-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="6e516-106">Uděláte to tak, že vyberete spravovat balíčky NuGet... z položky nabídky projekt v aplikaci Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6e516-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="6e516-107">Na kartě Procházet vyhledejte název balíčku "Microsoft.. Numerics".</span><span class="sxs-lookup"><span data-stu-id="6e516-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="6e516-108">Ujistěte se, že zaškrtnete políčko zahrnout předběžné verze.</span><span class="sxs-lookup"><span data-stu-id="6e516-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="6e516-109">Zobrazí se seznam balíčků, které jsou k dispozici ke stažení.</span><span class="sxs-lookup"><span data-stu-id="6e516-109">This will list the packages available for download.</span></span>
<span data-ttu-id="6e516-110">Najetí myší na "Microsoft. propočty. numerické" "odhalí šipku směřující dolů napravo od čísla verze.</span><span class="sxs-lookup"><span data-stu-id="6e516-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="6e516-111">Pro instalaci balíčku numerických součástí klikněte na šipku.</span><span class="sxs-lookup"><span data-stu-id="6e516-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="6e516-112">Další podrobnosti najdete v příručce k [uživatelskému rozhraní Správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="6e516-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="6e516-113">Alternativně můžete použít konzolu Správce balíčků k přidání knihovny numerické aplikace do projektu prostřednictvím rozhraní příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="6e516-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![Použití konzoly Správce balíčků z příkazového řádku](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="6e516-115">V konzole správce balíčků spusťte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="6e516-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="6e516-116">Další podrobnosti najdete v [Průvodci konzolou správce balíčků](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="6e516-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="6e516-117">**Příkazový řádek nebo Visual Studio Code:** Pomocí příkazového řádku na svém vlastním nebo z Visual Studio Code můžete pomocí `dotnet` příkazu přidat do projektu odkaz na balíček NuGet:</span><span class="sxs-lookup"><span data-stu-id="6e516-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="6e516-118">Ověření instalace</span><span class="sxs-lookup"><span data-stu-id="6e516-118">Verifying your installation</span></span>

<span data-ttu-id="6e516-119">Podobně jako v ostatních částech vývojové sady pro práci s více částmi obsahuje knihovna numerických verzí ukázky, které vám pomůžou začít co nejrychleji.</span><span class="sxs-lookup"><span data-stu-id="6e516-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="6e516-120">K otestování instalace pomocí těchto ukázek naklonujte [hlavní úložiště ukázek](https://github.com/Microsoft/Quantum) a pak spusťte jednu z ukázek.</span><span class="sxs-lookup"><span data-stu-id="6e516-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="6e516-121">Spuštění [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) ukázky:</span><span class="sxs-lookup"><span data-stu-id="6e516-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
