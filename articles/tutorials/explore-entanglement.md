---
title: 'Prozkoumejte entanglement s Q#'
description: 'Přečtěte si, jak napsat program pro vypisování do Q# . Vývoj aplikace demonstrující Bellovy stavy pomocí nástroje Quantum Development Kit (QDK)'
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 7a1a49e18ac9330ca6e3cc89b3e58c96eccb91db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691673"
---
# <a name="tutorial-explore-entanglement-with-q"></a><span data-ttu-id="15e77-104">Kurz: Zkoumání provázání s využitím Q\#</span><span class="sxs-lookup"><span data-stu-id="15e77-104">Tutorial: Explore entanglement with Q\#</span></span>

<span data-ttu-id="15e77-105">V tomto kurzu vám ukážeme, jak napsat Q# program, který pracuje s měřením qubits a ukazuje účinky nadpozice a entanglement.</span><span class="sxs-lookup"><span data-stu-id="15e77-105">In this tutorial, we show you how to write a Q# program that manipulates and measures qubits and demonstrates the effects of superposition and entanglement.</span></span>

<span data-ttu-id="15e77-106">Vytvoříme aplikaci nazvanou Bell, která demonstruje kvantové provázání.</span><span class="sxs-lookup"><span data-stu-id="15e77-106">You will write an application called Bell to demonstrate quantum entanglement.</span></span>
<span data-ttu-id="15e77-107">Název Bell odkazuje na Bellovy stavy, což jsou specifické kvantové stavy 2 qubitů používané k demonstraci nejjednodušších příkladů superpozice a provázání.</span><span class="sxs-lookup"><span data-stu-id="15e77-107">The name Bell is in reference to Bell states, which are specific quantum states of two qubits that are used to represent the simplest examples of superposition and quantum entanglement.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="15e77-108">Požadavky</span><span class="sxs-lookup"><span data-stu-id="15e77-108">Pre-requisites</span></span>

<span data-ttu-id="15e77-109">Chcete-li se pustit do kódování, nejprve proveďte tyto kroky:</span><span class="sxs-lookup"><span data-stu-id="15e77-109">If you are ready to start coding, follow these steps before proceeding:</span></span> 

* <span data-ttu-id="15e77-110">[Nainstalujte](xref:microsoft.quantum.install) sadu pro vývoj pro práci s více jazyky pomocí vašeho preferovaného jazykového a vývojového prostředí.</span><span class="sxs-lookup"><span data-stu-id="15e77-110">[Install](xref:microsoft.quantum.install) the Quantum Development Kit using your  preferred language and development environment.</span></span>
* <span data-ttu-id="15e77-111">Pokud už máte sadu QDK nainstalovanou, zkontrolujte, že je [aktualizovaná na nejnovější verzi](xref:microsoft.quantum.update)</span><span class="sxs-lookup"><span data-stu-id="15e77-111">If you already have the QDK installed, make sure you have [updated](xref:microsoft.quantum.update) to the latest version</span></span>

<span data-ttu-id="15e77-112">Můžete také postupovat spolu s mluveným komentářem bez instalace QDK, Projděte si přehledy Q# programovacího jazyka a první koncepty výpočetních prostředků.</span><span class="sxs-lookup"><span data-stu-id="15e77-112">You can also follow along with the narrative without installing the QDK, reviewing  the overviews of the Q# programming language and the first concepts of quantum computing.</span></span>

## <a name="in-this-tutorial-youll-learn-how-to"></a><span data-ttu-id="15e77-113">V tomto kurzu se naučíte:</span><span class="sxs-lookup"><span data-stu-id="15e77-113">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="15e77-114">Vytváření a kombinování operací v Q\#</span><span class="sxs-lookup"><span data-stu-id="15e77-114">Create and combine operations in Q\#</span></span>
> * <span data-ttu-id="15e77-115">Vytvořte operace pro vložení qubits do umístění, entangle a měření.</span><span class="sxs-lookup"><span data-stu-id="15e77-115">Create operations to put qubits in superposition, entangle and measure them.</span></span>
> * <span data-ttu-id="15e77-116">Demonstrujte neentanglementa za sebou za Q# běhu programu v simulátoru.</span><span class="sxs-lookup"><span data-stu-id="15e77-116">Demonstrate quantum entanglement with a Q# program run in a simulator.</span></span> 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a><span data-ttu-id="15e77-117">Demonstrace chování qubit pomocí QDK</span><span class="sxs-lookup"><span data-stu-id="15e77-117">Demonstrating qubit behavior with the QDK</span></span>

<span data-ttu-id="15e77-118">Zatímco klasické bity obsahují jednu binární hodnotu (tj. 0 nebo 1), [qubit](xref:microsoft.quantum.glossary#qubit) se může nacházet v **superpozici** stavů 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="15e77-118">Where classical bits hold a single binary value such as a 0 or 1, the state of a [qubit](xref:microsoft.quantum.glossary#qubit) can be in a **superposition** of 0 and 1.</span></span>  <span data-ttu-id="15e77-119">Koncepční, stav qubit lze představit jako směr v abstraktním prostoru (označuje se také jako vektor).</span><span class="sxs-lookup"><span data-stu-id="15e77-119">Conceptually, the state of a qubit can be thought of as a direction in an abstract space (also known as a vector).</span></span>  <span data-ttu-id="15e77-120">Stav qubit může být v libovolném z možných směrů.</span><span class="sxs-lookup"><span data-stu-id="15e77-120">A qubit state can be in any of the possible directions.</span></span> <span data-ttu-id="15e77-121">Dva **klasické stavy** odpovídají dvěma směrům. Představují 100% šanci na změření 0 a 100% šanci na změření 1.</span><span class="sxs-lookup"><span data-stu-id="15e77-121">The two **classical states** are the two directions; representing 100% chance of measuring 0 and 100% chance of measuring 1.</span></span>

<span data-ttu-id="15e77-122">Akce měření poskytuje binární výsledek a mění stav qubitu.</span><span class="sxs-lookup"><span data-stu-id="15e77-122">The act of measurement produces a binary result and changes a qubit state.</span></span>
<span data-ttu-id="15e77-123">Měření vytvoří binární hodnotu, buď 0, nebo 1.</span><span class="sxs-lookup"><span data-stu-id="15e77-123">Measurement  produces a binary value, either 0 or 1.</span></span>  <span data-ttu-id="15e77-124">V důsledku měření přejde qubit ze superpozice (libovolného směru) do jednoho z klasických stavů.</span><span class="sxs-lookup"><span data-stu-id="15e77-124">The qubit goes from being in superposition (any direction) to one of the classical states.</span></span>  <span data-ttu-id="15e77-125">Všechna následná opakovaná měření bez provedení dalších operací už budou poskytovat shodný binární výsledek.</span><span class="sxs-lookup"><span data-stu-id="15e77-125">Thereafter, repeating the same measurement without any intervening operations produces the same binary result.</span></span>  

<span data-ttu-id="15e77-126">Několik qubitů může být také [**provázáno**](xref:microsoft.quantum.glossary#entanglement).</span><span class="sxs-lookup"><span data-stu-id="15e77-126">Multiple qubits can be [**entangled**](xref:microsoft.quantum.glossary#entanglement).</span></span>  <span data-ttu-id="15e77-127">Když změříme jeden provázaný qubit, změní se tím naše znalost stavu ostatních qubitů.</span><span class="sxs-lookup"><span data-stu-id="15e77-127">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

<span data-ttu-id="15e77-128">Nyní jsme připraveni předvést, jak Q# Toto chování vyjadřuje.</span><span class="sxs-lookup"><span data-stu-id="15e77-128">Now, we're ready to demonstrate how Q# expresses this behavior.</span></span>  <span data-ttu-id="15e77-129">Začneme s nejjednodušším možným programem a sestavíme ho tak, abychom demonstrovali kvantovou superpozici a provázání.</span><span class="sxs-lookup"><span data-stu-id="15e77-129">You start with the simplest program possible and build it up to demonstrate quantum superposition and quantum entanglement.</span></span>

## <a name="creating-a-no-locq-project"></a><span data-ttu-id="15e77-130">Vytvoření Q# projektu</span><span class="sxs-lookup"><span data-stu-id="15e77-130">Creating a Q# project</span></span>

<span data-ttu-id="15e77-131">První věc, kterou je potřeba udělat, je vytvoření nového Q# projektu.</span><span class="sxs-lookup"><span data-stu-id="15e77-131">The first thing we have to do is to create a new Q# project.</span></span> <span data-ttu-id="15e77-132">V tomto kurzu použijeme prostředí založené na [ Q# aplikacích s vs Code](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="15e77-132">In this tutorial we are going to use the environment based on [Q# applications with VS Code](xref:microsoft.quantum.install.standalone).</span></span>

<span data-ttu-id="15e77-133">Chcete-li vytvořit nový projekt, v VS Code:</span><span class="sxs-lookup"><span data-stu-id="15e77-133">To create a new project, in VS Code:</span></span> 

1. <span data-ttu-id="15e77-134">Klikněte na **Zobrazení** -> **Paleta příkazů** a vyberte **Q#: Vytvořit nový projekt** .</span><span class="sxs-lookup"><span data-stu-id="15e77-134">Click **View** -> **Command Palette** and select **Q#: Create New Project** .</span></span>
2. <span data-ttu-id="15e77-135">Klikněte na **Samostatná konzolová aplikace** .</span><span class="sxs-lookup"><span data-stu-id="15e77-135">Click **Standalone console application** .</span></span>
3. <span data-ttu-id="15e77-136">Přejděte do umístění, kam chcete projekt uložit, a klikněte na **Vytvořit projekt** .</span><span class="sxs-lookup"><span data-stu-id="15e77-136">Navigate to the location to save the project and click **Create Project** .</span></span>
4. <span data-ttu-id="15e77-137">Po úspěšném vytvoření projektu klikněte na **Otevřít nový projekt...** v pravém dolním rohu.</span><span class="sxs-lookup"><span data-stu-id="15e77-137">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="15e77-138">V tomto případě jsme volali projekt `Bell` .</span><span class="sxs-lookup"><span data-stu-id="15e77-138">In this case we called the project `Bell`.</span></span> <span data-ttu-id="15e77-139">Tím se vytvoří dva soubory: `Bell.csproj` , soubor projektu a `Program.qs` Šablona aplikace, kterou použijeme Q# k zápisu naší aplikace.</span><span class="sxs-lookup"><span data-stu-id="15e77-139">This generates two files: `Bell.csproj`, the project file and `Program.qs`, a template of a Q# application that we will use to write our application.</span></span> <span data-ttu-id="15e77-140">Obsah `Program.qs` by měl být:</span><span class="sxs-lookup"><span data-stu-id="15e77-140">The content of `Program.qs` should be:</span></span>

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a><span data-ttu-id="15e77-141">Zapsat aplikaci Q \#</span><span class="sxs-lookup"><span data-stu-id="15e77-141">Write the Q\# application</span></span>
 
<span data-ttu-id="15e77-142">Naším cílem je připravit dva qubitsy v určitém stavu, který ukazuje, jak pracovat na qubits s Q# cílem změnit svůj stav a Ukázat účinky nadpozice a entanglement.</span><span class="sxs-lookup"><span data-stu-id="15e77-142">Our goal is to prepare two qubits in a specific quantum state, demonstrating how to operate on qubits with Q# to change their state and demonstrate the effects of superposition and entanglement.</span></span> <span data-ttu-id="15e77-143">Za účelem zavedení qubitch států, operací a měření vám budeme sestavovat tuto část.</span><span class="sxs-lookup"><span data-stu-id="15e77-143">We will build this up piece by piece to introduce qubit states, operations, and measurement.</span></span>

### <a name="initialize-qubit-using-measurement"></a><span data-ttu-id="15e77-144">Inicializovat qubit pomocí měření</span><span class="sxs-lookup"><span data-stu-id="15e77-144">Initialize qubit using measurement</span></span>

<span data-ttu-id="15e77-145">V prvním fragmentu kódu níže ukazujeme, jak pracovat s qubits v Q# .</span><span class="sxs-lookup"><span data-stu-id="15e77-145">In the first code snippet below, we show you how to work with qubits in Q#.</span></span>  <span data-ttu-id="15e77-146">Zavádíme dvě operace [`M`](xref:Microsoft.Quantum.Intrinsic.m) a [`X`](xref:Microsoft.Quantum.Intrinsic.X) transformují stav qubit.</span><span class="sxs-lookup"><span data-stu-id="15e77-146">We’ll introduce two operations, [`M`](xref:Microsoft.Quantum.Intrinsic.m) and [`X`](xref:Microsoft.Quantum.Intrinsic.X) that transform the state of a qubit.</span></span> <span data-ttu-id="15e77-147">V tomto fragmentu kódu je použita operace `SetQubitState`, která přijímá jako parametr qubit a další parametr `desired` označující stav, do kterého chceme qubit převést.</span><span class="sxs-lookup"><span data-stu-id="15e77-147">In this code snippet, an operation `SetQubitState` is defined that takes as a parameter a qubit and another parameter, `desired`, representing the state that we would like the qubit to be in.</span></span>  <span data-ttu-id="15e77-148">Operace `SetQubitState` provádí měření qubitu pomocí operace `M`.</span><span class="sxs-lookup"><span data-stu-id="15e77-148">The operation `SetQubitState` performs a measurement on the qubit using the operation `M`.</span></span>  <span data-ttu-id="15e77-149">V Q# je měření qubit vždy vrací buď `Zero` nebo `One` .</span><span class="sxs-lookup"><span data-stu-id="15e77-149">In Q#, a qubit measurement always returns either `Zero` or `One`.</span></span>  <span data-ttu-id="15e77-150">Pokud měření vrátí hodnotu, která není rovna požadované hodnotě, "převrátí `SetQubitState` " qubit; to znamená, že spustí `X` operaci, která změní stav qubit na nový stav, ve kterém pravděpodobnost vracení měření vrací `Zero` a `One` jsou obráceny.</span><span class="sxs-lookup"><span data-stu-id="15e77-150">If the measurement returns a value not equal to the desired value, `SetQubitState` “flips” the qubit; that is, it runs an `X` operation, which changes the qubit state to a new state in which the probabilities of a measurement returning `Zero` and `One` are reversed.</span></span> <span data-ttu-id="15e77-151">Tímto způsobem `SetQubitState` vždy umístí cílový qubit do požadovaného stavu.</span><span class="sxs-lookup"><span data-stu-id="15e77-151">This way, `SetQubitState` always puts the target qubit in the desired state.</span></span>

<span data-ttu-id="15e77-152">Nahraďte obsah `Program.qs` následujícím kódem:</span><span class="sxs-lookup"><span data-stu-id="15e77-152">Replace the contents of `Program.qs` with the following code:</span></span>


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

<span data-ttu-id="15e77-153">Teď můžeme zavolat tuto operaci, aby nastavila qubit do klasického stavu a vrátila buď hodnotu `Zero` ve 100 % případů, nebo hodnotu `One` ve 100 % případů.</span><span class="sxs-lookup"><span data-stu-id="15e77-153">This operation may now be called to set a qubit to a classical state, either returning `Zero` 100% of the time or returning `One` 100% of the time.</span></span>
<span data-ttu-id="15e77-154">`Zero` a `One` jsou konstanty, které představují pouze dva možné výsledky měření stavu qubitu.</span><span class="sxs-lookup"><span data-stu-id="15e77-154">`Zero` and `One` are constants that represent the only two possible results of a measurement of a qubit.</span></span>

<span data-ttu-id="15e77-155">Operace `SetQubitState` měří qubit.</span><span class="sxs-lookup"><span data-stu-id="15e77-155">The operation `SetQubitState` measures the qubit.</span></span> <span data-ttu-id="15e77-156">Pokud je qubit ve stavu, který chceme, `SetQubitState` ponechá ho samostatně. v opačném případě se `X` stav qubit změní na požadovaný stav.</span><span class="sxs-lookup"><span data-stu-id="15e77-156">If the qubit is in the state we want, `SetQubitState` leaves it alone; otherwise, by running the `X` operation, we change the qubit state to the desired state.</span></span>

#### <a name="about-no-locq-operations"></a><span data-ttu-id="15e77-157">O Q# operacích</span><span class="sxs-lookup"><span data-stu-id="15e77-157">About Q# operations</span></span>

<span data-ttu-id="15e77-158">Q#Operace je podprogram nečinnosti.</span><span class="sxs-lookup"><span data-stu-id="15e77-158">A Q# operation is a quantum subroutine.</span></span> <span data-ttu-id="15e77-159">To znamená, že se jedná o volanou rutinu, která obsahuje volání jiných operací.</span><span class="sxs-lookup"><span data-stu-id="15e77-159">That is, it is a callable routine that contains calls to other quantum operations.</span></span>

<span data-ttu-id="15e77-160">Argumenty operace jsou zadány jako řazené kolekce členů v závorkách.</span><span class="sxs-lookup"><span data-stu-id="15e77-160">The arguments to an operation are specified as a tuple, within parentheses.</span></span>

<span data-ttu-id="15e77-161">Návratový typ operace je určen za dvojtečkou.</span><span class="sxs-lookup"><span data-stu-id="15e77-161">The return type of the operation is specified after a colon.</span></span> <span data-ttu-id="15e77-162">V takovém případě `SetQubitState` operace nemá žádný návratový typ, takže je označena jako návratová `Unit` .</span><span class="sxs-lookup"><span data-stu-id="15e77-162">In this case, the `SetQubitState` operation has no return type, so it is marked as returning `Unit`.</span></span> <span data-ttu-id="15e77-163">Toto je Q# ekvivalent `unit` v F #, který je zhruba podobný `void` v jazyce C# a prázdná řazená kolekce členů v Pythonu ( `()` reprezentovaná parametrem typu `Tuple[()]` ).</span><span class="sxs-lookup"><span data-stu-id="15e77-163">This is the Q# equivalent of `unit` in F#, which is roughly analogous to `void` in C#, and an empty tuple in Python (`()`, represented by the type hint `Tuple[()]`).</span></span>

<span data-ttu-id="15e77-164">V první operaci jste použili dvě provozní operace Q# :</span><span class="sxs-lookup"><span data-stu-id="15e77-164">You have used two quantum operations in your first Q# operation:</span></span>

* <span data-ttu-id="15e77-165">[`M`](xref:Microsoft.Quantum.Intrinsic.m)Operace, která měří stav qubit</span><span class="sxs-lookup"><span data-stu-id="15e77-165">The [`M`](xref:Microsoft.Quantum.Intrinsic.m) operation, which measures the state of the qubit</span></span>
* <span data-ttu-id="15e77-166">[`X`](xref:Microsoft.Quantum.Intrinsic.X)Operace, která Překlopí stav qubit</span><span class="sxs-lookup"><span data-stu-id="15e77-166">The [`X`](xref:Microsoft.Quantum.Intrinsic.X) operation, which flips the state of a qubit</span></span>

<span data-ttu-id="15e77-167">Kvantová operace mění stav qubitu.</span><span class="sxs-lookup"><span data-stu-id="15e77-167">A quantum operation transforms the state of a qubit.</span></span> <span data-ttu-id="15e77-168">Někdy se mluví o kvantových hradlech místo kvantových operacích, je totiž možná i analogie s klasickými logickými hradly.</span><span class="sxs-lookup"><span data-stu-id="15e77-168">Sometime people talk about quantum gates instead of operations, in analogy to classical logic gates.</span></span> <span data-ttu-id="15e77-169">Tento koncept pochází z raných dob kvantových výpočtů, kdy byly algoritmy jen teoretické konstrukce a vizualizovaly se ve formě schémat odpovídacích obvodovým schématům klasických počítačů.</span><span class="sxs-lookup"><span data-stu-id="15e77-169">This is rooted in the early days of quantum computing when algorithms were merely a theoretical construct and visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>

### <a name="counting-measurement-outcomes"></a><span data-ttu-id="15e77-170">Počítání výsledků měření</span><span class="sxs-lookup"><span data-stu-id="15e77-170">Counting measurement outcomes</span></span>

<span data-ttu-id="15e77-171">Pro předvedení efektu operace `SetQubitState` je pak přidána operace `TestBellState`.</span><span class="sxs-lookup"><span data-stu-id="15e77-171">To demonstrate the effect of the `SetQubitState` operation, a `TestBellState` operation is then added.</span></span> <span data-ttu-id="15e77-172">Tato operace jako vstup přebírá `Zero` nebo `One`, několikrát s tímto vstupem zavolá operaci `SetQubitState` a spočítá, kolikrát byla z měření qubitu vrácena hodnota `Zero` a kolikrát `One`.</span><span class="sxs-lookup"><span data-stu-id="15e77-172">This operation takes as input a `Zero` or `One`, and calls the `SetQubitState` operation some number of times with that input, and counts the number of times that `Zero` was returned from the measurement of the qubit and the number of times that `One` was returned.</span></span> <span data-ttu-id="15e77-173">Samozřejmě v této první simulaci operace `TestBellState` očekáváme, že všechna měření qubitu nastaveného pomocí vstupního parametru `Zero` vrátí hodnotu `Zero` a všechna měření qubitu nastaveného pomocí parametru `One` vrátí `One`.</span><span class="sxs-lookup"><span data-stu-id="15e77-173">Of course, in this first simulation of the `TestBellState` operation, we expect that the output will show that all measurements of the qubit set with `Zero` as the parameter input will return `Zero`, and all measurements of a qubit set with `One` as the parameter input will return `One`.</span></span> <span data-ttu-id="15e77-174">Dále přidáte kód k `TestBellState` předvedení entanglement a.</span><span class="sxs-lookup"><span data-stu-id="15e77-174">Further on, we’ll add code to `TestBellState` to demonstrate superposition and entanglement.</span></span>

<span data-ttu-id="15e77-175">Přidejte do souboru `Program.qs` následující operaci, do oboru názvů za konec operace `SetQubitState`:</span><span class="sxs-lookup"><span data-stu-id="15e77-175">Add the following operation to the `Program.qs` file, inside the namespace, after the end of the `SetQubitState` operation:</span></span>

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
<span data-ttu-id="15e77-176">Všimněte si, že před `return` tiskem vysvětlující zprávy v konzole jsme přidali řádek s funkcí ( `Message` ) [Microsoft. prohlášeno. vnitřní. zpráva].</span><span class="sxs-lookup"><span data-stu-id="15e77-176">Note that we added a line before the `return` to print an explanatory message in the console with the function (`Message`)[microsoft.quantum.intrinsic.message]</span></span>

<span data-ttu-id="15e77-177">Tato operace (`TestBellState`) se zopakuje v `count` iteracích, v každé nastaví zadanou hodnotu qubitu `initial` a pak změří výsledek (`M`).</span><span class="sxs-lookup"><span data-stu-id="15e77-177">This operation (`TestBellState`) will loop for `count` iterations, set a specified `initial` value on a qubit and then measure (`M`) the result.</span></span> <span data-ttu-id="15e77-178">Shromáždí statistiku o počtu naměřených nul a jedniček a vrátí je volajícímu.</span><span class="sxs-lookup"><span data-stu-id="15e77-178">It will gather statistics on how many zeros and ones we've measured and return them to the caller.</span></span> <span data-ttu-id="15e77-179">Provede ale ještě jednu důležitou operaci.</span><span class="sxs-lookup"><span data-stu-id="15e77-179">It performs one other necessary operation.</span></span> <span data-ttu-id="15e77-180">Před návratem resetuje qubit do známého stavu (`Zero`), aby ostatní mohli tento qubit použít ve známém stavu.</span><span class="sxs-lookup"><span data-stu-id="15e77-180">It resets the qubit to a known state (`Zero`) before returning it allowing others to allocate this qubit in a known state.</span></span> <span data-ttu-id="15e77-181">To je provedeno příkazem `using`.</span><span class="sxs-lookup"><span data-stu-id="15e77-181">This is required by the `using` statement.</span></span>

#### <a name="about-variables-in-q"></a><span data-ttu-id="15e77-182">O proměnných v Q\#</span><span class="sxs-lookup"><span data-stu-id="15e77-182">About variables in Q\#</span></span>

<span data-ttu-id="15e77-183">Ve výchozím nastavení proměnné v Q# jsou neměnné; jejich hodnota nesmí být po svázání změněna.</span><span class="sxs-lookup"><span data-stu-id="15e77-183">By default, variables in Q# are immutable; their value may not be changed after they are bound.</span></span> <span data-ttu-id="15e77-184">Klíčové slovo `let` slouží k označení vazby neměnné proměnné.</span><span class="sxs-lookup"><span data-stu-id="15e77-184">The `let` keyword is used to indicate the binding of an immutable variable.</span></span> <span data-ttu-id="15e77-185">Argumenty operace jsou vždycky neměnné.</span><span class="sxs-lookup"><span data-stu-id="15e77-185">Operation arguments are always immutable.</span></span>

<span data-ttu-id="15e77-186">Pokud potřebujete proměnnou, jejíž hodnotu je možné změnit, například `numOnes` v našem příkladu, můžete proměnnou deklarovat pomocí klíčového slova `mutable`.</span><span class="sxs-lookup"><span data-stu-id="15e77-186">If you need a variable whose value can change, such as `numOnes` in the example, you can declare the variable with the `mutable` keyword.</span></span> <span data-ttu-id="15e77-187">Hodnotu proměnlivé proměnné lze změnit pomocí příkazu `set`.</span><span class="sxs-lookup"><span data-stu-id="15e77-187">A mutable variable's value may be changed using a `set` statement.</span></span>

<span data-ttu-id="15e77-188">V obou případech je typ proměnné odvozen kompilátorem.</span><span class="sxs-lookup"><span data-stu-id="15e77-188">In both cases, the type of a variable is inferred by the compiler.</span></span> <span data-ttu-id="15e77-189">Q# pro proměnné nevyžadují žádné anotace typu.</span><span class="sxs-lookup"><span data-stu-id="15e77-189">Q# doesn't require any type annotations for variables.</span></span>

#### <a name="about-using-statements-in-q"></a><span data-ttu-id="15e77-190">O `using` příkazech v Q\#</span><span class="sxs-lookup"><span data-stu-id="15e77-190">About `using` statements in Q\#</span></span>

<span data-ttu-id="15e77-191">`using`Příkaz je také speciální pro Q# .</span><span class="sxs-lookup"><span data-stu-id="15e77-191">The `using` statement is also special to Q#.</span></span> <span data-ttu-id="15e77-192">Slouží k přidělení qubitů pro použití v bloku kódu.</span><span class="sxs-lookup"><span data-stu-id="15e77-192">It is used to allocate qubits for use in a block of code.</span></span> <span data-ttu-id="15e77-193">V systému se Q# všechny qubits dynamicky přidělují a uvolňují, ale nejedná se o pevné prostředky, které jsou pro celou dobu života komplexního algoritmu.</span><span class="sxs-lookup"><span data-stu-id="15e77-193">In Q#, all qubits are dynamically allocated and released, rather than being fixed resources that are there for the entire lifetime of a complex algorithm.</span></span> <span data-ttu-id="15e77-194">Příkaz `using` přidělí sadu qubitů na začátku a uvolní je na konci bloku.</span><span class="sxs-lookup"><span data-stu-id="15e77-194">A `using` statement allocates a set of qubits at the start, and releases those qubits at the end of the block.</span></span>

## <a name="run-the-code-from-the-command-prompt"></a><span data-ttu-id="15e77-195">Spuštění kódu z příkazového řádku</span><span class="sxs-lookup"><span data-stu-id="15e77-195">Run the code from the command prompt</span></span>

<span data-ttu-id="15e77-196">Aby bylo možné spustit kód, musíme instruovat kompilátor, *který* se při zadání příkazu spustí, aby běžel `dotnet run` .</span><span class="sxs-lookup"><span data-stu-id="15e77-196">In order to run the code we need to tell the compiler *which* callable to run when we provide the `dotnet run` command.</span></span> <span data-ttu-id="15e77-197">To se provádí v případě jednoduché změny v Q# souboru přidáním řádku s `@EntryPoint()` přímo předcházejícím voláním: `TestBellState` operace v tomto případě.</span><span class="sxs-lookup"><span data-stu-id="15e77-197">This is done with a simple change in the Q# file by adding a line with `@EntryPoint()` directly preceding the callable: the `TestBellState` operation in this case.</span></span> <span data-ttu-id="15e77-198">Úplný kód by měl být:</span><span class="sxs-lookup"><span data-stu-id="15e77-198">The full code should be:</span></span>

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

<span data-ttu-id="15e77-199">Aby bylo možné spustit program, musíme zadat `count` `initial` argumenty a z příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="15e77-199">To run the program we need to specify `count` and `initial` arguments from the command prompt.</span></span> <span data-ttu-id="15e77-200">Vybereme například `count = 1000` a `initial = One` .</span><span class="sxs-lookup"><span data-stu-id="15e77-200">Let's choose for example `count = 1000` and `initial = One`.</span></span> <span data-ttu-id="15e77-201">Zadejte následující příkaz:</span><span class="sxs-lookup"><span data-stu-id="15e77-201">Enter the following command:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

<span data-ttu-id="15e77-202">A měli byste sledovat následující výstup:</span><span class="sxs-lookup"><span data-stu-id="15e77-202">And you should observe the following output:</span></span>

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="15e77-203">Pokud se o to pokusíte `initial = Zero` , měli byste sledovat:</span><span class="sxs-lookup"><span data-stu-id="15e77-203">If you try with `initial = Zero` you should observe:</span></span>

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a><span data-ttu-id="15e77-204">Příprava superpozice</span><span class="sxs-lookup"><span data-stu-id="15e77-204">Prepare superposition</span></span>

<span data-ttu-id="15e77-205">Teď se podíváme na to, jak vyjadřuje způsob, jak Q# umístit qubits na pozici.</span><span class="sxs-lookup"><span data-stu-id="15e77-205">Now let’s look at how Q# expresses ways to put qubits in superposition.</span></span>  <span data-ttu-id="15e77-206">Připomeňme si, že stav qubitu může být superpozicí hodnot 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="15e77-206">Recall that the state of a qubit can be in a superposition of 0 and 1.</span></span>  <span data-ttu-id="15e77-207">Dosáhneme toho operací `Hadamard`.</span><span class="sxs-lookup"><span data-stu-id="15e77-207">We’ll use the `Hadamard` operation to accomplish this.</span></span> <span data-ttu-id="15e77-208">Pokud je qubit v některém z klasických stavů (kdy měření vrátí vždy `Zero` nebo vždy `One`), pak operace `Hadamard` nebo `H` převede qubit do stavu, ve kterém měření vrátí v 50 % případů `Zero` a v 50 % případů `One`.</span><span class="sxs-lookup"><span data-stu-id="15e77-208">If the qubit is in either of the classical states (where a measurement returns `Zero` always or `One` always), then the `Hadamard` or `H` operation will put the qubit in a state where a measurement of the qubit will return `Zero` 50% of the time and return `One` 50% of the time.</span></span>  <span data-ttu-id="15e77-209">Můžete si to představit tak, že qubit je uprostřed mezi `Zero` a `One`.</span><span class="sxs-lookup"><span data-stu-id="15e77-209">Conceputually, the qubit can be thought of as halfway between the `Zero` and `One`.</span></span>  <span data-ttu-id="15e77-210">Když teď budeme simulovat operaci `TestBellState`, uvidíme, že jednotlivá měření vrátí přibližně stejný počet hodnot `Zero` a `One`.</span><span class="sxs-lookup"><span data-stu-id="15e77-210">Now, when we simulate the `TestBellState` operation, we will see the results will return roughly an equal number of `Zero` and `One` after measurement.</span></span>  

### <a name="x-flips-qubit-state"></a><span data-ttu-id="15e77-211">`X` Překlopí stav qubit.</span><span class="sxs-lookup"><span data-stu-id="15e77-211">`X` flips qubit state</span></span>

<span data-ttu-id="15e77-212">Nejdřív se podíváme na překlopení qubit (Pokud je qubit ve `Zero` stavu, Překlopí se na `One` a naopak).</span><span class="sxs-lookup"><span data-stu-id="15e77-212">First we'll just try to flip the qubit (if the qubit is in `Zero` state it will flip to `One` and vice versa).</span></span> <span data-ttu-id="15e77-213">Toho se dosáhne použitím operace `X` před změřením v operaci `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="15e77-213">This is accomplished by performing an `X` operation before we measure it in `TestBellState`:</span></span>

```qsharp
X(qubit);
let res = M(qubit);
```

<span data-ttu-id="15e77-214">Nyní jsou výsledky vráceny:</span><span class="sxs-lookup"><span data-stu-id="15e77-214">Now the results are reversed:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

<span data-ttu-id="15e77-215">Teď se podíváme na vlastnosti pro qubits.</span><span class="sxs-lookup"><span data-stu-id="15e77-215">Now let's explore the quantum properties of the qubits.</span></span>

### <a name="h-prepares-superposition"></a><span data-ttu-id="15e77-216">`H` připraví nadpozici</span><span class="sxs-lookup"><span data-stu-id="15e77-216">`H` prepares superposition</span></span>

<span data-ttu-id="15e77-217">Stačí k tomu nahradit operaci `X` v předchozím běhu operací `H` (Hadamard).</span><span class="sxs-lookup"><span data-stu-id="15e77-217">All we need to do is replace the `X` operation in the previous run with an `H` or Hadamard operation.</span></span> <span data-ttu-id="15e77-218">Místo úplného překlopení qubitu z 0 na 1 ho můžeme překlopit jen napůl.</span><span class="sxs-lookup"><span data-stu-id="15e77-218">Instead of flipping the qubit all the way from 0 to 1, we will only flip it halfway.</span></span> <span data-ttu-id="15e77-219">Změněné řádky v `TestBellState` teď vypadají takto:</span><span class="sxs-lookup"><span data-stu-id="15e77-219">The replaced lines in `TestBellState` now look like:</span></span>

```qsharp
H(qubit);
let res = M(qubit);
```

<span data-ttu-id="15e77-220">Teď už výsledky budou zajímavější:</span><span class="sxs-lookup"><span data-stu-id="15e77-220">Now the results get more interesting:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

<span data-ttu-id="15e77-221">Každým měřením požádáme o klasickou hodnotu, ale qubit je uprostřed mezi 0 a 1, takže (statisticky) dostaneme v polovině případů 0 a v polovině případů 1.</span><span class="sxs-lookup"><span data-stu-id="15e77-221">Every time we measure, we ask for a classical value, but the qubit is halfway between 0 and 1, so we get (statistically) 0 half the time and 1 half the time.</span></span>
<span data-ttu-id="15e77-222">To se označuje jako **superpozice** a je to naše první seznámení s kvantovými stavy.</span><span class="sxs-lookup"><span data-stu-id="15e77-222">This is known as **superposition** and gives us our first real view into a quantum state.</span></span>

## <a name="prepare-entanglement"></a><span data-ttu-id="15e77-223">Příprava provázání</span><span class="sxs-lookup"><span data-stu-id="15e77-223">Prepare entanglement</span></span>

<span data-ttu-id="15e77-224">Teď se podíváme na Q# to, jak vyjádřit možnosti entangle qubits.</span><span class="sxs-lookup"><span data-stu-id="15e77-224">Now let’s look at how Q# expresses ways to entangle qubits.</span></span>
<span data-ttu-id="15e77-225">Nejdřív uvedeme první qubit do počátečního stavu a pak ho pomocí operace `H` převedeme do superpozice.</span><span class="sxs-lookup"><span data-stu-id="15e77-225">First, we set the first qubit to the initial state and then use the `H` operation to put it into superposition.</span></span>  <span data-ttu-id="15e77-226">Pak před měřením prvního qubit používáme novou operaci ( `CNOT` ), která se zaznamená pro kontrolu *ne* .</span><span class="sxs-lookup"><span data-stu-id="15e77-226">Then, before we measure the first qubit, we use a new operation (`CNOT`), which stands for *Controlled-NOT* .</span></span>  <span data-ttu-id="15e77-227">Výsledkem spuštění této operace na dvou qubits je překlopení druhé qubit, pokud je první qubit `One` .</span><span class="sxs-lookup"><span data-stu-id="15e77-227">The result of running this operation on two qubits is to flip the second qubit if the first qubit is `One`.</span></span>  <span data-ttu-id="15e77-228">Nyní máme dva provázané qubity.</span><span class="sxs-lookup"><span data-stu-id="15e77-228">Now, the two qubits are entangled.</span></span>  <span data-ttu-id="15e77-229">Statistika prvního qubitu se nezměnila (stále šance 50-50, že měřením získáme `Zero` nebo `One`), ale když teď změříme stav druhého qubitu, bude __vždy__ stejný jako stav naměřený u toho prvního.</span><span class="sxs-lookup"><span data-stu-id="15e77-229">Our statistics for the first qubit haven't changed (50-50 chance of a `Zero` or a `One` after measurement), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit.</span></span> <span data-ttu-id="15e77-230">Operace `CNOT` provázala oba qubity, takže cokoli se stane jednomu, stane se i druhému.</span><span class="sxs-lookup"><span data-stu-id="15e77-230">Our `CNOT` has entangled the two qubits, so that whatever happens to one of them, happens to the other.</span></span> <span data-ttu-id="15e77-231">Když pořadí měření otočíme (změříme nejprve druhý a pak první qubit), dostaneme úplně stejný výsledek.</span><span class="sxs-lookup"><span data-stu-id="15e77-231">If you reversed the measurements (did the second qubit before the first), the same thing would happen.</span></span> <span data-ttu-id="15e77-232">První měření bude náhodné, ale druhé bude přesně kopírovat výsledek toho prvního.</span><span class="sxs-lookup"><span data-stu-id="15e77-232">The first measurement would be random and the second would be in lock step with whatever was discovered for the first.</span></span>

<span data-ttu-id="15e77-233">První věc, kterou je potřeba udělat, je přidělit dvě qubits místo jedné v `TestBellState` :</span><span class="sxs-lookup"><span data-stu-id="15e77-233">The first thing we'll need to do is allocate two qubits instead of one in `TestBellState`:</span></span>

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

<span data-ttu-id="15e77-234">To nám umožní přidat novou operaci (`CNOT`) před změřením (`M`) v operaci `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="15e77-234">This will allow us to add a new operation (`CNOT`) before we measure  (`M`) in `TestBellState`:</span></span>

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

<span data-ttu-id="15e77-235">Přidali jsme další operaci `SetQubitState` inicializující první qubit, abychom se ujistili, že je vždy v počátečním stavu `Zero`.</span><span class="sxs-lookup"><span data-stu-id="15e77-235">We've added another `SetQubitState` operation to initialize the first qubit to make sure that it's always in the `Zero` state when we start.</span></span>

<span data-ttu-id="15e77-236">Stejně tak musíme resetovat druhý qubit, než ho na konci uvolníme.</span><span class="sxs-lookup"><span data-stu-id="15e77-236">We also need to reset the second qubit before releasing it.</span></span>

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

<span data-ttu-id="15e77-237">Úplná rutina teď vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="15e77-237">The full routine now looks like this:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

<span data-ttu-id="15e77-238">Když ji spustíme, získáme přesně stejný výsledek 50-50, jako předtím.</span><span class="sxs-lookup"><span data-stu-id="15e77-238">If we run this, we'll get exactly the same 50-50 result we got before.</span></span> <span data-ttu-id="15e77-239">Co nás ale zajímá je způsob, jakým druhý qubit reaguje na první měřenou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="15e77-239">However, what we're interested in is how the second qubit reacts to the first being measured.</span></span> <span data-ttu-id="15e77-240">Tuto statistiku přidáme s novou verzí operace `TestBellState`:</span><span class="sxs-lookup"><span data-stu-id="15e77-240">We'll add this statistic with a new version of the `TestBellState` operation:</span></span>

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

<span data-ttu-id="15e77-241">Nová návratová hodnota (`agree`) počítá případy, kdy se měření prvního qubitu shodovalo s měřením druhého qubitu.</span><span class="sxs-lookup"><span data-stu-id="15e77-241">The new return value (`agree`) keeps track of every time the measurement from the first qubit matches the measurement of the second qubit.</span></span>

<span data-ttu-id="15e77-242">Spuštění kódu, který získáme:</span><span class="sxs-lookup"><span data-stu-id="15e77-242">Running the code we obtain:</span></span>

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

<span data-ttu-id="15e77-243">Jak jsme uvedli v přehledu, statistika prvního qubitu se nezměnila (stále šance 50:50, že získáme 0 nebo 1), ale teď když změříme stav druhého qubitu, bude __vždy__ stejný, jako změřený stav toho prvního, protože jsou provázané!</span><span class="sxs-lookup"><span data-stu-id="15e77-243">As stated in the overview, our statistics for the first qubit haven't changed (50-50 chance of a 0 or a 1), but now when we measure the second qubit, it is __always__ the same as what we measured for the first qubit, because they are entangled!</span></span>

## <a name="next-steps"></a><span data-ttu-id="15e77-244">Další kroky</span><span class="sxs-lookup"><span data-stu-id="15e77-244">Next steps</span></span>

<span data-ttu-id="15e77-245">V kurzu [Grover Search](xref:microsoft.quantum.quickstarts.search) se dozvíte, jak sestavovat a spouštět hledání Grover, jeden z nejoblíbenějších výpočetních algoritmů a nabízí dobrý příklad Q# programu, který se dá použít k řešení reálných problémů s výpočetním využitím.</span><span class="sxs-lookup"><span data-stu-id="15e77-245">The tutorial [Grover’s search](xref:microsoft.quantum.quickstarts.search) shows you how to build and run Grover search, one of the most popular quantum computing algorithms and offers a nice example of a Q# program that can be used to solve real problems with quantum computing.</span></span>  

<span data-ttu-id="15e77-246">[Začínáme s vývojovou sadou pro](xref:microsoft.quantum.welcome) všechna ta: doporučuje více způsobů, jak se naučit Q# a naprogramovat práci.</span><span class="sxs-lookup"><span data-stu-id="15e77-246">[Get Started with the Quantum Development Kit](xref:microsoft.quantum.welcome) recommends more ways to learn Q# and quantum programming.</span></span>
