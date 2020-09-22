---
title: Seznámení s balíčkem kvantového strojového učení | Microsoft Docs
description: Seznámení s balíčkem kvantového strojového učení
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 321901a7976e4633a672495827c27c5f1645ad30
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835685"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a>Seznámení s knihovnou pro kvantové strojové učení

Knihovna pro kvantové strojové učení je rozhraní API napsané v jazyce Q#, které vám dává možnost spouštět hybridní experimenty kvantového/klasického strojového učení. Tato knihovna umožňuje:

- Načítat vlastní data pro klasifikaci s využitím kvantových simulátorů

- Využívat ukázky a kurzy k seznámení s problematikou kvantového strojového učení

V porovnání se současnými klasickými architekturami strojového učení můžete očekávat nízký výkon (nezapomínejte, že všechno běží nad simulací kvantového zařízení, která sama o sobě má na výpočetní výkon velké nároky).

Účelem této dokumentace je:

- Stručné seznámení s nástroji strojového učení (napsanými v jazyce Q\#) pro hybridní kvantové/klasické učení.
- Seznámení s koncepty strojového učení a konkrétně jejich realizací v kvantových klasifikátorech se zaměřením na obvody (označují se také jako kvantové sekvenční klasifikátory).
- Zajištění sady kurzů zaměřených na základy využívání nástrojů, které tato knihovna poskytuje.
- Diskuze o metodách trénování a ověřování pro klasifikátory tohoto typu a jejich převodu na konkrétní operace Q\# poskytované touto knihovnou.

Model implementovaný v této knihovně vychází ze schématu kvantového/klasického trénování popsaného v článku [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633) (Kvantové klasifikátory se zaměřením na obvody).
