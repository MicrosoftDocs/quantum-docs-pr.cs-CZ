---
title: Vývoj s využitím Q# a .NET
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 155367dbb1373f00e2b0bd732a5319b32462c9f9
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426506"
---
# <a name="develop-with-q-and-net"></a>Vývoj s využitím Q# a .NET

Q # je sestavený tak, aby se dobře hrál s jazyky .NET, jako je C# a F #.
V této příručce vám ukážeme, jak použít Q # s hostitelským programem napsaným v jazyce .NET.

## <a name="prerequisites"></a>Požadavky

- Nainstalujte sadu [pro vývoj pro více procesorů pro použití s projekty příkazového řádku Q #](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Vytvoření knihovny Q # a hostitele .NET

Prvním krokem je vytvoření projektů pro knihovnu Q # a pro hostitele .NET, který bude volat operace a funkce definované ve vaší knihovně Q #.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Vytvoření nové knihovny Q #
  - Přejít na **soubor**  ->  **Nový**  ->  **projekt**
  - Do vyhledávacího pole zadejte text "Q #"
  - Vybrat **knihovnu Q #**
  - Vybrat **Další**
  - Zvolit název a umístění knihovny
  - Ujistěte se, že není **zaškrtnuté** možnost "umístit projekt a řešení ve stejném adresáři".
  - Vyberte **vytvořit** .
- Vytvořit nový hostitelský program C# nebo F #
  - Přejít na **soubor** → **Nový** → **projekt**
  - Vyberte Konzolová aplikace (.NET Core) pro C# nebo F. #
  - Vybrat **Další**
  - V části *řešení*vyberte Přidat do řešení.
  - Vyberte název hostitelského programu
  - Vyberte **vytvořit** .

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code nebo příkazový řádek](#tab/tabid-cmdline)

- Vytvoření nové knihovny Q #

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Vytvoření nového projektu konzoly C# nebo F #

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Přidání knihovny Q # jako odkazu z hostitelského programu

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Volitelné Vytvoření řešení pro oba projekty

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>Volání do Q # z .NET

Jakmile budete mít projekty nastavené podle výše uvedených pokynů, můžete do aplikace v konzole .NET zavolat do Q #.
Kompilátor Q # vytvoří třídy .NET pro každou operaci Q # a funkci, která vám umožní spouštět v simulátoru své programy pro práci s více operačními systémy.

Například [Ukázka interoperability .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) zahrnuje následující příklad operace Q #:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Chcete-li volat tuto operaci z rozhraní .NET pro simulátor doby provozu, můžete použít `Run` metodu `RunAlgorithm` třídy .NET vygenerovanou kompilátorem Q #:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Další kroky

Když teď máte prostředí pro vývoj s využitím provozu pro Q # pro programy příkazového řádku Q a pro interoperabilitu s .NET, můžete napsat a spustit [svůj první program](xref:microsoft.quantum.quickstarts.qrng)pro práci s procesorem.
