---
title: Seznámení s balíčkem kvantového strojového učení | Microsoft Docs
description: Seznámení s balíčkem kvantového strojového učení
author: QuantumWriter
ms.author: alexeib
ms.date: 12/5/2019
ms.topic: conceptual
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e36948a216a06d76b99cd451bbfac6f5defd7c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858790"
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
