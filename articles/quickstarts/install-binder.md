---
title: Vývoj s využitím Q# a Binderu
description: Naučte se vytvářet aplikace v Q# pomocí Binderu.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: quickstart
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f7e9b1ae67d6275ec7ba39ea411842dc537536c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856714"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="b3f3e-103">Vývoj s využitím Q# a Binderu</span><span class="sxs-lookup"><span data-stu-id="b3f3e-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="b3f3e-104">Pomocí Binderu můžete spouštět a sdílet poznámkové bloky Jupyter online.</span><span class="sxs-lookup"><span data-stu-id="b3f3e-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="b3f3e-105">Použití Binderu s ukázkami sady Microsoft QDK</span><span class="sxs-lookup"><span data-stu-id="b3f3e-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="b3f3e-106">Automatické nakonfigurování Binderu pro použití ukázek sady Microsoft QDK:</span><span class="sxs-lookup"><span data-stu-id="b3f3e-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="b3f3e-107">Otevřete prohlížeč a přejděte na adresu https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="b3f3e-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="b3f3e-108">Na úvodní stránce **ukázek sady Quantum Development Kit** klikněte na **poznámkový blok Q#** a naučte se používat IQ# k psaní vlastních poznámkových bloků kvantových aplikací.</span><span class="sxs-lookup"><span data-stu-id="b3f3e-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![Úvodní stránka sady QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="b3f3e-110">Použití Binderu s vlastními poznámkovými bloky a úložištěm</span><span class="sxs-lookup"><span data-stu-id="b3f3e-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="b3f3e-111">Pokud už máte poznámkové bloky v úložišti GitHub, můžete Binder nakonfigurovat, aby pracoval s vaším úložištěm:</span><span class="sxs-lookup"><span data-stu-id="b3f3e-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="b3f3e-112">Zajistěte, aby byl v kořenové složce úložiště soubor s názvem *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="b3f3e-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="b3f3e-113">Tento soubor musí obsahovat alespoň následující řádky:</span><span class="sxs-lookup"><span data-stu-id="b3f3e-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="b3f3e-114">V [Poznámkách k verzi](xref:microsoft.quantum.relnotes) můžete ověřit nejaktuálnější verzi IQ#.</span><span class="sxs-lookup"><span data-stu-id="b3f3e-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="b3f3e-115">Další informace o vytváření souboru Dockerfile najdete v [referenčních informacích k souboru Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="b3f3e-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="b3f3e-116">Otevřete prohlížeč s adresou [mybinder.org](https://mybinder.org).</span><span class="sxs-lookup"><span data-stu-id="b3f3e-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="b3f3e-117">Zadejte název svého úložiště jako **adresu URL GitHubu** (například *jméno/MyRepo*) a klikněte na **launch** (Spustit).</span><span class="sxs-lookup"><span data-stu-id="b3f3e-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![Formulář MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="b3f3e-119">Další kroky</span><span class="sxs-lookup"><span data-stu-id="b3f3e-119">Next steps</span></span>

<span data-ttu-id="b3f3e-120">Když jste teď vytvořili prostředí Binderu, můžete psát a spouštět [své první kvantové programy](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="b3f3e-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
