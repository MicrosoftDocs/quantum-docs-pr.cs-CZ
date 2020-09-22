---
title: Seznámení s knihovnou kvantové chemie
description: Seznamte se s knihovnou Microsoft Quantum pro chemii a jejím využitím při simulaci elektronických struktur na kvantových počítačích.
author: QuantumWriter
ms.author: ageller
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15439a34933bd561dc011acf48e669abeb031e33
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835787"
---
# <a name="introduction-to-the-quantum-chemistry-library"></a><span data-ttu-id="27d80-103">Seznámení s knihovnou kvantové chemie</span><span class="sxs-lookup"><span data-stu-id="27d80-103">Introduction to the Quantum Chemistry Library</span></span>

<span data-ttu-id="27d80-104">Simulace fyzických systémů hrála v oblasti kvantových výpočtů dlouhou dobu hlavní roli.</span><span class="sxs-lookup"><span data-stu-id="27d80-104">Simulation of physical systems has long played a central role in quantum computing.</span></span>  <span data-ttu-id="27d80-105">Důvodem je široce rozšířené přesvědčení, že kvantová dynamika je pro simulace na kvantových počítačích nevhodná, protože složitost simulace systému roste exponenciálně s velikostí zkoumaného kvantového systému.</span><span class="sxs-lookup"><span data-stu-id="27d80-105">This is because quantum dynamics are widely believed to be intractable to simulate on quantum computers, meaning that the complexity of simulating the system scales exponentially with the size of the quantum system in question.</span></span>  <span data-ttu-id="27d80-106">Simulování problémů v chemii a nauce o materiálech zůstává pravděpodobně nejzajímavější oblastí použití kvantových výpočtů a umožnilo by nám testovat mechanismy chemických reakcí, které až dosud byly mimo naše schopnosti měření nebo simulace.</span><span class="sxs-lookup"><span data-stu-id="27d80-106">Simulating problems in chemistry and material science remains perhaps the most evocative application of quantum computing and would allow us to probe chemical reaction mechanisms that hitherto were beyond our ability to measure or simulate.</span></span>  <span data-ttu-id="27d80-107">Pomohlo by nám také simulovat korelované elektronické materiály, jako jsou vysokoteplotní supravodiče.</span><span class="sxs-lookup"><span data-stu-id="27d80-107">It would also allow us to simulate correlated electronic materials such as high-temperature superconductors.</span></span> <span data-ttu-id="27d80-108">Seznam použití v této oblasti je nekonečný.</span><span class="sxs-lookup"><span data-stu-id="27d80-108">The list of applications in this space is vast.</span></span>

<span data-ttu-id="27d80-109">Účelem této dokumentace je poskytnout stručný úvod do problémů simulace elektronických struktur na kvantových počítačích, abychom čtenářům usnadnili pochopení role, jakou na tomto poli hraje řada aspektů knihovny hamiltoniánských simulací.</span><span class="sxs-lookup"><span data-stu-id="27d80-109">The purpose of this documentation is to provide a concise introduction to simulating electronic structure problems on quantum computers in order to help the reader understand the role that many aspects of the Hamiltonian simulation library play within the space.</span></span>  <span data-ttu-id="27d80-110">Začneme stručným úvodem do kvantové mechaniky a pak přejdeme ke způsobům, jak jsou v ní modelovány elektronické systémy.</span><span class="sxs-lookup"><span data-stu-id="27d80-110">We begin with a brief introduction to quantum mechanics and then proceed to discuss how electronic systems are modeled in it.</span></span>  <span data-ttu-id="27d80-111">Potom probereme možnosti, jak jde kvantovou dynamiku emulovat pomocí kvantového počítače.</span><span class="sxs-lookup"><span data-stu-id="27d80-111">We will then discuss how such quantum dynamics can be emulated using a quantum computer.</span></span>  <span data-ttu-id="27d80-112">Po dokončení probereme dvě metody používané ke kompilaci kvantové dynamiky do posloupností elementárních hradel: Trotter-Suzukiho dekompozice a qubitizace.</span><span class="sxs-lookup"><span data-stu-id="27d80-112">Once this is complete we will discuss two methods used to compile the quantum dynamics to sequences of elementary gates: Trotter-Suzuki decompositions and qubitization.</span></span>
