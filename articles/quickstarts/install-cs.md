---
title: Vývoj s využitím Q# a .NET
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 714c15d9589095f0fe395fcd6941672167879dca
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885499"
---
# <a name="develop-with-q-and-net"></a>Vývoj s využitím Q# a .NET

Jazyk Q# je navržen tak, aby dobře spolupracoval s jazyky používanými v prostředí .NET, jako je C# nebo F#.
V tomto tématu vám ukážeme, jak použít Q# s hostitelským programem napsaným v jazyce .NET.

Nejprve vytvoříme aplikaci v jazyce Q# a hostitele .NET, a potom ukážeme, jak volat Q# z hostitele.

## <a name="prerequisites"></a>Požadavky

- Nainstalujte sadu Quantum Development Kit [pro práci s projekty Q# na příkazovém řádku](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Vytvoření knihovny Q# a hostitele .NET

Prvním krokem je vytvoření projektů pro vaši knihovnu Q# a pro hostitele .NET, který bude volat operace a funkce definované ve vaší knihovně Q#.

Postupujte podle pokynů na kartě odpovídající vašemu vývojovému prostředí.
Pokud používáte jiný editor než Visual Studio nebo VS Code, jednoduše postupujte podle kroků pro příkazový řádek.

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code nebo Příkazový řádek](#tab/tabid-cmdline)

- Vytvoření nové knihovny Q#

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Vytvořte nový projekt konzoly C# nebo F#.

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Přidejte knihovnu Q# jako referenci z hostitelského programu.

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [Volitelné] Vytvořte řešení pro oba projekty.

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Vytvoření nové knihovny Q#
  - Přejděte do části **Soubor** -> **Nový** -> **Projekt**.
  - Do vyhledávacího pole zadejte „Q#“.
  - Vyberte **Q# Library**.
  - Vyberte **Další**.
  - Vyberte název a umístění knihovny.
  - **Nezaškrtávejte** možnost „umístit projekt a řešení ve stejném adresáři“.
  - Vyberte **Vytvořit**.
- Vytvoření nového hostitelského programu C# nebo F#
  - Přejděte na **Soubor** → **Nový** → **Projekt**
  - Vyberte „Konzolová aplikace (.NET Core)“ pro C# nebo F#.
  - Vyberte **Další**.
  - V části *řešení*vyberte „přidat do řešení“.
  - Zvolte název hostitelského programu.
  - Vyberte **Vytvořit**.

***

## <a name="calling-into-q-from-net"></a>Volání Q# z .NET

Jakmile budete mít projekty nastavené podle výše uvedených pokynů, můžete z konzolové aplikace zavolat program Q#.
Kompilátor Q# vytvoří třídy .NET pro každou operaci a funkci Q#, které umožní spouštění kvantových programů v simulátoru.

Například [ukázka interoperability .NET](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) obsahuje následující příklad operace Q#:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

K volání této operace z prostředí .NET na kvantovém simulátoru můžete použít metodu `Run` z třídy .NET `RunAlgorithm`, generované kompilátorem Q#:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>Další kroky

Když teď máte sadu Quantum Development Kit konfigurovanou pro programy Q# na příkazovém řádku i pro spolupráci s prostředím .NET, můžete začít psát [svůj první kvantový program](xref:microsoft.quantum.quickstarts.qrng).
