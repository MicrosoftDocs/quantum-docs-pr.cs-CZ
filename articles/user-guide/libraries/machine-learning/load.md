---
title: Načítání klasických dat
description: Naučte se, jak načíst vlastní datovou sadu pro výuku modelu klasifikátoru pomocí Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: cd6fdb6bb33a65ee02ac8c43f40df9abeff9c841
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833698"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="5cd2c-103">Načtení a klasifikace vlastních datových sad</span><span class="sxs-lookup"><span data-stu-id="5cd2c-103">Load and classify your own datasets</span></span>

<span data-ttu-id="5cd2c-104">V tomto krátkém kurzu se naučíte, jak načíst vlastní datovou sadu pro výuku modelu klasifikátoru pomocí nástroje pro vývoj QDK.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="5cd2c-105">Důrazně doporučujeme použití standardizovaného formátu serializace, jako jsou [soubory JSON](https://en.wikipedia.org/wiki/JSON) , pro ukládání vašich dat.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="5cd2c-106">Takové formáty nabízejí vysokou kompatibilitu s různými architekturami, jako je Python a ekosystém .NET.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="5cd2c-107">Konkrétně doporučujeme použít naši šablonu pro načtení dat, abyste mohli zkopírovat kód přímo z ukázek.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="5cd2c-108">Šablona pro načítání datových sad</span><span class="sxs-lookup"><span data-stu-id="5cd2c-108">Template for loading your datasets</span></span>

<span data-ttu-id="5cd2c-109">Předpokládejme, že máme datovou sadu pro školení $ (x, y) $ o velikosti $N = $2, kde každá instance $x _i $ $x $ má tři funkce: $x _ {typem I1} $, $x _ {I2} $ a $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="5cd2c-110">Datová sada ověření má stejnou strukturu.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="5cd2c-111">Tyto datsets mohou být reprezentovány `data.json` souborem podobným následujícímu:</span><span class="sxs-lookup"><span data-stu-id="5cd2c-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a><span data-ttu-id="5cd2c-112">Příklad použití šablony</span><span class="sxs-lookup"><span data-stu-id="5cd2c-112">Example using the template</span></span>

<span data-ttu-id="5cd2c-113">Předpokládejme, že máme malou datovou sadu se výškami a závažími různých koček a psů.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="5cd2c-114">Tato datová sada je velmi malá pro výuku modelu, ale bude stačit pro zobrazení procesu načtení datové sady.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="5cd2c-115">Výška (m)</span><span class="sxs-lookup"><span data-stu-id="5cd2c-115">Height (m)</span></span> | <span data-ttu-id="5cd2c-116">Váha (kg)</span><span class="sxs-lookup"><span data-stu-id="5cd2c-116">Weight (kg)</span></span> | <span data-ttu-id="5cd2c-117">Plyšák</span><span class="sxs-lookup"><span data-stu-id="5cd2c-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="5cd2c-118">0.54</span><span class="sxs-lookup"><span data-stu-id="5cd2c-118">0.54</span></span>      | <span data-ttu-id="5cd2c-119">30</span><span class="sxs-lookup"><span data-stu-id="5cd2c-119">30</span></span>         | <span data-ttu-id="5cd2c-120">Psy</span><span class="sxs-lookup"><span data-stu-id="5cd2c-120">Dog</span></span>    |
| <span data-ttu-id="5cd2c-121">0,30</span><span class="sxs-lookup"><span data-stu-id="5cd2c-121">0.30</span></span>      | <span data-ttu-id="5cd2c-122">8</span><span class="sxs-lookup"><span data-stu-id="5cd2c-122">8</span></span>          | <span data-ttu-id="5cd2c-123">Cat</span><span class="sxs-lookup"><span data-stu-id="5cd2c-123">Cat</span></span>    |
| <span data-ttu-id="5cd2c-124">0,91</span><span class="sxs-lookup"><span data-stu-id="5cd2c-124">0.91</span></span>      | <span data-ttu-id="5cd2c-125">44</span><span class="sxs-lookup"><span data-stu-id="5cd2c-125">44</span></span>         | <span data-ttu-id="5cd2c-126">Psy</span><span class="sxs-lookup"><span data-stu-id="5cd2c-126">Dog</span></span>    |
| <span data-ttu-id="5cd2c-127">0,86</span><span class="sxs-lookup"><span data-stu-id="5cd2c-127">0.86</span></span>      | <span data-ttu-id="5cd2c-128">31</span><span class="sxs-lookup"><span data-stu-id="5cd2c-128">31</span></span>          | <span data-ttu-id="5cd2c-129">Psy</span><span class="sxs-lookup"><span data-stu-id="5cd2c-129">Dog</span></span>    |
| <span data-ttu-id="5cd2c-130">0,32</span><span class="sxs-lookup"><span data-stu-id="5cd2c-130">0.32</span></span>      | <span data-ttu-id="5cd2c-131">5</span><span class="sxs-lookup"><span data-stu-id="5cd2c-131">5</span></span>         | <span data-ttu-id="5cd2c-132">Cat</span><span class="sxs-lookup"><span data-stu-id="5cd2c-132">Cat</span></span>    |
| <span data-ttu-id="5cd2c-133">0,25</span><span class="sxs-lookup"><span data-stu-id="5cd2c-133">0.25</span></span>      | <span data-ttu-id="5cd2c-134">4</span><span class="sxs-lookup"><span data-stu-id="5cd2c-134">4</span></span>          | <span data-ttu-id="5cd2c-135">Cat</span><span class="sxs-lookup"><span data-stu-id="5cd2c-135">Cat</span></span>    |

<span data-ttu-id="5cd2c-136">Postup je následující:</span><span class="sxs-lookup"><span data-stu-id="5cd2c-136">The process is:</span></span>

- <span data-ttu-id="5cd2c-137">Nejdřív je potřeba oddělit datovou sadu do školení a ověření.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="5cd2c-138">V takovém případě můžeme pouze první tři ukázky pro školení a zbytek vzorků pro ověření.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="5cd2c-139">Obecně je vhodné vzorkovat datovou sadu s náhodným školením a ověřením, abyste se vyhnuli nechtěným posunům v školicích datech.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="5cd2c-140">Za druhé potřebujeme přiřadit číselný popisek ke každé třídě.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="5cd2c-141">Všimněte si, že za chvíli QML Library pouze problémy binární klasifikace.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="5cd2c-142">Proto přiřadíme k třídě popisek 0 `Dog` a číslo 1 ke třídě `Cat` .</span><span class="sxs-lookup"><span data-stu-id="5cd2c-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="5cd2c-143">Nakonec šablonu vyplníme pomocí dat z naší datové sady.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="5cd2c-144">Všimněte si, že pro velké datové sady byste měli vytvořit malý skript, který automaticky vygeneruje šablonu z konkrétní datové sady.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="5cd2c-145">Tento skript bude záviset na původním formátu datové sady.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="5cd2c-146">Pro naši datovou sadu `data.json` soubor je:</span><span class="sxs-lookup"><span data-stu-id="5cd2c-146">For our dataset the `data.json` file is:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a><span data-ttu-id="5cd2c-147">Načtení dat</span><span class="sxs-lookup"><span data-stu-id="5cd2c-147">Loading the data</span></span>

<span data-ttu-id="5cd2c-148">Jakmile budete mít data serializovaná jako soubor JSON, můžete je načíst pomocí knihoven JSON, které jsou k dispozici s vámi zvoleným jazykem hostitele.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="5cd2c-149">Python</span><span class="sxs-lookup"><span data-stu-id="5cd2c-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="5cd2c-150">Python poskytuje [integrovaný `json` balíček](https://docs.python.org/3.7/library/json.html) pro práci s daty serializovanými ve formátu JSON:</span><span class="sxs-lookup"><span data-stu-id="5cd2c-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="5cd2c-151">C#</span><span class="sxs-lookup"><span data-stu-id="5cd2c-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="5cd2c-152">Platforma .NET Core poskytuje [ `System.Text.Json` balíček](https://www.nuget.org/packages/System.Text.Json) pro práci s daty serializovanými ve formátu JSON:</span><span class="sxs-lookup"><span data-stu-id="5cd2c-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="5cd2c-153">Další kroky</span><span class="sxs-lookup"><span data-stu-id="5cd2c-153">Next steps</span></span>

<span data-ttu-id="5cd2c-154">Nyní jste připraveni začít používat vlastní experimenty s vlastními datovými sadami.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="5cd2c-155">Vyzkoušejte různé třídění a datovou sadu a přispívat ke sdílení vašich výsledků komunitou.</span><span class="sxs-lookup"><span data-stu-id="5cd2c-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
