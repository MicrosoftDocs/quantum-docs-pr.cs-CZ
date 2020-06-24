---
title: Načítání klasických dat
description: Naučte se, jak načíst vlastní datovou sadu pro výuku modelu klasifikátoru pomocí Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: efa4a65a489446cbef48507d0b02a932da74c71c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274705"
---
# <a name="load-and-classify-your-own-datasets"></a>Načtení a klasifikace vlastních datových sad

V tomto krátkém kurzu se naučíte, jak načíst vlastní datovou sadu pro výuku modelu klasifikátoru pomocí nástroje pro vývoj QDK.

Důrazně doporučujeme použití standardizovaného formátu serializace, jako jsou [soubory JSON](https://en.wikipedia.org/wiki/JSON) , pro ukládání vašich dat.
Takové formáty nabízejí vysokou kompatibilitu s různými architekturami, jako je Python a ekosystém .NET.
Konkrétně doporučujeme použít naši šablonu pro načtení dat, abyste mohli zkopírovat kód přímo z ukázek.

## <a name="template-for-loading-your-datasets"></a>Šablona pro načítání datových sad

Předpokládejme, že máme datovou sadu pro školení $ (x, y) $ o velikosti $N = $2, kde každá instance $x _i $ $x $ má tři funkce: $x _ {typem I1} $, $x _ {I2} $ a $x _ {i3} $.
Datová sada ověření má stejnou strukturu.
Tyto datsets mohou být reprezentovány `data.json` souborem podobným následujícímu:

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

### <a name="example-using-the-template"></a>Příklad použití šablony

Předpokládejme, že máme malou datovou sadu se výškami a závažími různých koček a psů. Tato datová sada je velmi malá pro výuku modelu, ale bude stačit pro zobrazení procesu načtení datové sady.

| Výška (m) | Váha (kg) | Plyšák |
|-----------|------------|--------|
| 0,54      | 30         | Psy    |
| 0,30      | 8          | Cat    |
| 0,91      | 44         | Psy    |
| 0,86      | 31          | Psy    |
| 0,32      | 5         | Cat    |
| 0,25      | 4          | Cat    |

Postup je následující:

- Nejdřív je potřeba oddělit datovou sadu do školení a ověření. V takovém případě můžeme pouze první tři ukázky pro školení a zbytek vzorků pro ověření. Obecně je vhodné vzorkovat datovou sadu s náhodným školením a ověřením, abyste se vyhnuli nechtěným posunům v školicích datech.
- Za druhé potřebujeme přiřadit číselný popisek ke každé třídě. Všimněte si, že za chvíli QML Library pouze problémy binární klasifikace. Proto přiřadíme k třídě popisek 0 `Dog` a číslo 1 ke třídě `Cat` .
- Nakonec šablonu vyplníme pomocí dat z naší datové sady. Všimněte si, že pro velké datové sady byste měli vytvořit malý skript, který automaticky vygeneruje šablonu z konkrétní datové sady. Tento skript bude záviset na původním formátu datové sady.

Pro naši datovou sadu `data.json` soubor je:

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

## <a name="loading-the-data"></a>Načtení dat

Jakmile budete mít data serializovaná jako soubor JSON, můžete je načíst pomocí knihoven JSON, které jsou k dispozici s vámi zvoleným jazykem hostitele.

### <a name="python"></a>[Python](#tab/tabid-python)

Python poskytuje [integrovaný `json` balíček](https://docs.python.org/3.7/library/json.html) pro práci s daty serializovanými ve formátu JSON:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

Platforma .NET Core poskytuje [ `System.Text.Json` balíček](https://www.nuget.org/packages/System.Text.Json) pro práci s daty serializovanými ve formátu JSON:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Další kroky

Nyní jste připraveni začít používat vlastní experimenty s vlastními datovými sadami. Vyzkoušejte různé třídění a datovou sadu a přispívat ke sdílení vašich výsledků komunitou.
