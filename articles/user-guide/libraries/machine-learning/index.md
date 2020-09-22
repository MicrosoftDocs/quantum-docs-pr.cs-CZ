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
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="9ee5d-103">Seznámení s knihovnou pro kvantové strojové učení</span><span class="sxs-lookup"><span data-stu-id="9ee5d-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="9ee5d-104">Knihovna pro kvantové strojové učení je rozhraní API napsané v jazyce Q#, které vám dává možnost spouštět hybridní experimenty kvantového/klasického strojového učení.</span><span class="sxs-lookup"><span data-stu-id="9ee5d-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="9ee5d-105">Tato knihovna umožňuje:</span><span class="sxs-lookup"><span data-stu-id="9ee5d-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="9ee5d-106">Načítat vlastní data pro klasifikaci s využitím kvantových simulátorů</span><span class="sxs-lookup"><span data-stu-id="9ee5d-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="9ee5d-107">Využívat ukázky a kurzy k seznámení s problematikou kvantového strojového učení</span><span class="sxs-lookup"><span data-stu-id="9ee5d-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="9ee5d-108">V porovnání se současnými klasickými architekturami strojového učení můžete očekávat nízký výkon (nezapomínejte, že všechno běží nad simulací kvantového zařízení, která sama o sobě má na výpočetní výkon velké nároky).</span><span class="sxs-lookup"><span data-stu-id="9ee5d-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="9ee5d-109">Účelem této dokumentace je:</span><span class="sxs-lookup"><span data-stu-id="9ee5d-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="9ee5d-110">Stručné seznámení s nástroji strojového učení (napsanými v jazyce Q\#) pro hybridní kvantové/klasické učení.</span><span class="sxs-lookup"><span data-stu-id="9ee5d-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="9ee5d-111">Seznámení s koncepty strojového učení a konkrétně jejich realizací v kvantových klasifikátorech se zaměřením na obvody (označují se také jako kvantové sekvenční klasifikátory).</span><span class="sxs-lookup"><span data-stu-id="9ee5d-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="9ee5d-112">Zajištění sady kurzů zaměřených na základy využívání nástrojů, které tato knihovna poskytuje.</span><span class="sxs-lookup"><span data-stu-id="9ee5d-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="9ee5d-113">Diskuze o metodách trénování a ověřování pro klasifikátory tohoto typu a jejich převodu na konkrétní operace Q\# poskytované touto knihovnou.</span><span class="sxs-lookup"><span data-stu-id="9ee5d-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="9ee5d-114">Model implementovaný v této knihovně vychází ze schématu kvantového/klasického trénování popsaného v článku [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633) (Kvantové klasifikátory se zaměřením na obvody).</span><span class="sxs-lookup"><span data-stu-id="9ee5d-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
