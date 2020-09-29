---
title: Vývoj s využitím Q# a Binderu
description: Naučte se vytvářet aplikace v Q# pomocí Binderu.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836523"
---
# <a name="develop-with-no-locq-and-binder"></a>Vývoj s využitím Q# a Binderu

Pomocí Binderu můžete spouštět a sdílet poznámkové bloky Jupyter online.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Použití Binderu s ukázkami sady Microsoft QDK

Automatické nakonfigurování Binderu pro použití ukázek sady Microsoft QDK:

1. Otevřete prohlížeč a přejděte na adresu https://aka.ms/try-qsharp.
1. Na úvodní stránce **ukázek sady Quantum Development Kit** klikněte na **poznámkový blok Q#** a naučte se používat IQ# k psaní vlastních poznámkových bloků kvantových aplikací.

![Úvodní stránka sady QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>Použití Binderu s vlastními poznámkovými bloky a úložištěm

Pokud už máte poznámkové bloky v úložišti GitHub, můžete Binder nakonfigurovat, aby pracoval s vaším úložištěm:

1. Zajistěte, aby byl v kořenové složce úložiště soubor s názvem *Dockerfile*. Tento soubor musí obsahovat alespoň následující řádky:

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > V [Poznámkách k verzi](xref:microsoft.quantum.relnotes) můžete ověřit nejaktuálnější verzi IQ#.

    Další informace o vytváření souboru Dockerfile najdete v [referenčních informacích k souboru Dockerfile](https://docs.docker.com/engine/reference/builder/).

2. Otevřete prohlížeč s adresou [mybinder.org](https://mybinder.org).
3. Zadejte název svého úložiště jako **adresu URL GitHubu** (například *jméno/MyRepo*) a klikněte na **launch** (Spustit).

![Formulář MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a>Další kroky

Když jste teď vytvořili prostředí Binderu, můžete psát a spouštět [své první kvantové programy](xref:microsoft.quantum.quickstarts.qrng).