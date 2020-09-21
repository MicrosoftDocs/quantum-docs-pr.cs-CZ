---
title: Schéma chemického Broombridge
description: Přehled schématu Broombridgech nech procesorů, který se používá k modelování reálných problémů v chemickém prostředí s Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
no-loc:
- Q#
- $$v
ms.openlocfilehash: e580fd8267cc7ba30533d557eceb486f8c205be6
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835770"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Schéma chemického Broombridge # 

Výkonný výpočetní software pro zpracování, jako je [NWChem](http://www.nwchem-sw.org/) , umožňuje modelovat nejrůznější problémy v oblasti reálného světa. Aby bylo možné získat přístup k NWChem molekulových modelů pomocí knihovny Microsoft pro složení doby, použijete schéma založené na [YAML](https://en.wikipedia.org/wiki/YAML)s názvem **Broombridge**. Název se zvolil v odkazu na [orientační bod](https://en.wikipedia.org/wiki/Broom_Bridge) , který je v některých kruzích přidaný jako místo narození Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) je open source projekt licencovaný v rámci OPRAVŇUJÍCÍ licence zákaz ECL (vzdělávací komunity) 2,0. [Schéma Broombridgech](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)termínů pro stanovení nepočátečních termínů je open source schéma, které zahrnuje [definici](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) následující [RFC 2119](https://tools.ietf.org/html/rfc2119) a [skript validátoru](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licencovaný v rámci licence MIT. 

YAML Broombridge je strukturovaný, uživatelsky čitelný a upravitelný způsob, jak vyjádřit problémy s elektronickými strukturami. Konkrétně je možné znázornit následující data:
- Fermionic Hamiltonians lze reprezentovat pomocí jednoho a dvou částí.
- Stavy uzemnění a zajímání se dají znázornit pomocí sekvencí vytváření.
- Je možné zadat horní a dolní meze úrovně energie.

Data je možné vygenerovat z NWChem pomocí různých metod, jako je například použití úplné instalace NWChem ke spouštění sady chemické balíčky (například ty, které jsou uvedeny v [knihovně NWChem](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) , které výstup Broombridge jako součást běhu), nebo Docker image NWChem, která se dá použít také ke generování Broombridge z chemické balíčky. Aby bylo možné rychle začít s výpočetními chemiemi bez nutnosti instalovat software ze chemického prostředí, můžete použít vizuální rozhraní k NWChem, které poskytuje [EMSL šipky](https://arrows.emsl.pnnl.gov/api/qsharp_chem).

Na vysoké úrovni se souhře mezi NWChem a Microsoft Quantum Development Kit dá vizuálně vybarvit takto: ![ chemie Stack ](~/media/broombridge.png) (modré šedivé pole) představuje schéma Broombridge, různá šedá vystínovaná pole představují další interní reprezentace dat, která se rozhodla znázornit a zpracovávat algoritmy pro výpočetní výpočetní služby na základě reálných problémů s chemie.

Složka [integrál/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) v úložišti pro vývojová prostředí pro práci s ukázkami obsahuje několik chemických reprezentací definovaných pomocí schématu Broombridge.
