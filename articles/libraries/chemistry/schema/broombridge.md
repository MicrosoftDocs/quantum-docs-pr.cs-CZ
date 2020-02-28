---
title: Broombridge – schéma pro složení nech procesorů
description: Přehled schématu Broombridgech nech procesorů, který se používá k modelování reálných problémů v chemickém prostředí s Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907813"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Schéma chemického Broombridge # 

Výkonný výpočetní programový software, jako je [NWChem](http://www.nwchem-sw.org/) , umožňuje modelovat nejrůznější problémy v oblasti reálného světa. Aby bylo možné získat přístup k NWChem molekulových modelů pomocí knihovny Microsoft pro složení doby, používáme schéma založené na [YAML](https://en.wikipedia.org/wiki/YAML), které voláme **Broombridge**. Název se zvolil v odkazu na [orientační bod](https://en.wikipedia.org/wiki/Broom_Bridge) , který je v některých kruzích přidaný jako místo narození Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) je open source projekt licencovaný v rámci OPRAVŇUJÍCÍ licence zákaz ECL (vzdělávací komunity) 2,0. Broombridge je open source schéma, které je zadané [tady](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) a které se nachází v [definici](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) popsané v [dokumentu RFC 2119](https://tools.ietf.org/html/rfc2119) a [skriptu validátoru](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licencovaného v rámci licence MIT. 

YAML Broombridge je strukturovaný, uživatelsky čitelný a upravitelný způsob, jak vyjádřit problémy s elektronickými strukturami. Konkrétně je možné znázornit následující data: 
- Fermionic Hamiltonians lze reprezentovat pomocí jednoho a dvou částí. 
- Stavy uzemnění a zajímání se dají znázornit pomocí sekvencí vytváření.
- Je možné zadat horní a dolní meze úrovně energie.

Formát dat je možné vygenerovat z NWChem s možností snadného navýšení: k dispozici je celá řada metod, která je v rozsahu od úplné instalace NWChem, aby spouštěla sady chemické balíčky, jako jsou ty, které jsou [tady](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) uvedené, a výstupní Broombridge jako součást běhu, přes Docker image NWChem, která se dá také použít ke generování Broombridge z chemické balíčky. Nakonec vizuální metodu, která umožňuje rychle začít s výpočetními chemiemi, aniž by bylo nutné instalovat žádný software z chemického prostředí [EMSL šipkami](https://arrows.emsl.pnnl.gov/api/qsharp_chem) na NWChem. 

Na vysoké úrovni se souhře mezi NWChem a Microsoft Quantum Development Kit dá vizuálně seskupit takto: ![ou sazbu,](~/media/broombridge.png) modré šedivé pole představuje schéma Broombridge, různá šedá vystínovaná pole představují další interní reprezentace dat, která se rozhodla znázornit a zpracovávat algoritmy pro výpočetní výpočetní služby na základě problémů ze skutečných složení. 

[Zde](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)jsou uvedeny různé chemické reprezentace definované pomocí schématu Broombridge.
