---
title: Popis okruhu provozu: Přečtěte si, jak vizuálně znázornit jednoduché a komplexní operace s využitím diagramů okruhu.
Autor: QuantumWriter UID: Microsoft.. koncepty. okruhy MS. Author: v-benbra MS. Date: 12/11/2017 MS. téma: koncepční No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="quantum-circuits"></a>Okruhy
Vezměte v úvahu okamžik, kdy bude jednotná transformace $ \text { CNOT } _ { 01 } (H \otimes 1) $ .
Tato sekvence brány má zásadní význam pro výpočetní výkon, protože vytváří qubit stav s maximální entangled:

$$\mathrm{CNOT } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left ( \ket { 00 }  +  \ket { 11 } \right ),$$

Operace s touto nebo větší složitou složitostí jsou všudypřítomný s využitím algoritmů pro provozní a přístupnosti chyb, takže by měly být skvělé, že pro svou vizualizaci se používá jednoduchá metoda, která se nazývá *diagram okruhu*.
Diagram okruhu pro přípravu tohoto maximálního entangledého stavu je:

<!--- ![](.\media\1.svg) --->
<!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:-->
![Diagram okruhu pro maximální entangled stav qubit](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>Konvence diagramu pro okruhy
Tento vizuál pro práci s více operačními operacemi může být mnohem snadno digestible než zapsání jeho ekvivalentní matrice, jakmile pochopíte konvence pro vyjádření okruhu.
Tyto konvence prověříme níže.

V diagramu okruhu každá plná čára znázorňuje qubit nebo více všeobecně qubit Registry.
Podle konvence je horním řádkem qubit registr $ 0 $ a zbytek je označený sekvenčně. Výše uvedený příklad okruhu je znázorněný na dvou qubits (nebo ekvivalentních dvou registrech, které se skládají z jednoho qubit).
Brány fungující na jednom nebo více registrech qubit jsou označeny jako pole.
Například symbol

<!--- ![](.\media\2.svg) --->
<!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:-->
![Symbol pro Hadamard operace fungující v registru s jedním qubit](~/media/2.svg)

je [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) operace fungující v registru s jedním qubit.

Vyřazení z více procesorů je seřazené v chronologickém pořadí s bránou, která je nejvíce vlevo, jako brána se jako první používá pro qubits.
Jinými slovy, pokud se dráty naformátují jako držící stav, vodiče přinášejí stav u všech bran v diagramu zleva doprava.
Řekněme, že 

<!--- ![](.\media\3.svg) --->
<!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:-->
![Diagram protiprocesorů používaných v zleva doprava](~/media/3.svg)

je jednotná maticová matice $ certifikátů $ .
Násobení matice dodržuje opačnou konvenci: nejprve se použije matice nejvyšší výše. V diagramech okruhu ve službě pro vytváření koncových procesorů se ale jako první používá brána vlevo.
Tento rozdíl může v některých případech vést k nejasnostem, takže je důležité si všimnout tohoto významného rozdílu mezi lineárním zápisem algebraických a diagramy okruhu.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Vstupy a výstupy okruhů
Všechny předchozí uvedené příklady mají přesně stejný počet vodičů (qubits), jako je počet vodičů v bráně pro plnění.
Je možné, že se zpočátku jeví jako přiměřená, že okruhy by mohly mít více nebo méně výstupů, než jsou vstupy obecně.
To však není možné, protože všechny provozní operace šetří měření, jsou jednotně a tedy vratné.
Pokud neobsahují stejný počet výstupů jako vstupy, které by nebyly vratné, a proto nejsou v rozporu.
Z tohoto důvodu musí mít jakékoli pole vykreslené v diagramu okruhu přesně stejný počet vodičů, kteří ho vstupují při jeho ukončení.

Diagramy okruhu s více qubit se podobají podobným konvencím pro qubit.
V rámci objasnění příkladu můžeme definovat qubit jednotkovou operaci $ B $ , která bude $ (H S \otimes ×), $ a vyjadřovat ekvivalent okruhu jako

<!--- ![](.\media\4.svg) --->
<!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:-->
![Diagram okruhu s qubit jednotkovou operací](~/media/4.svg)

V $ $ závislosti na kontextu, ve kterém se okruh používá, můžeme také zobrazit B jako akce v jednom qubit registru, nikoli 2 1-qubit Registry. Nejužitečnější vlastností takových diagramů s abstraktním okruhem je pravděpodobně to, že umožňují složitosti složitých algoritmů na vysoké úrovni, aniž by bylo nutné je kompilovat na základní brány.
To znamená, že můžete získat Intuition o toku dat pro velký algoritmus, aniž byste museli porozumět všem podrobnostem o tom, jak jednotlivé podrutiny v rámci algoritmu fungují.

## <a name="controlled-gates"></a>Řízené brány
Druhá konstrukce, která je integrovaná do qubitch okruhů, je řídicích diagramů.
Akce u jednorázového množství, které je jednou kontrolované bránou $ \Lambda (g) $ , kde jedna hodnota qubit řídí aplikaci $ G, se dá pochopit tak, že se $ podíváme na následující příklad vstupu stavu produktu $ \Lambda (G) ( \alpha \ket { 0 }  +  \beta \ket { 1 } ) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } G \ket { \psi } $ . To znamená, že řízená brána použije $ G $ na registr, který obsahuje $ \psi $ if a jenom v případě, že ovládací prvek qubit přebírá hodnotu $ 1 $ .
Obecně popisujeme tyto řízené operace v diagramech okruhů jako

<!--- ![](.\media\5.svg) --->
<!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:-->
![Diagram okruhu samostatně kontrolované brány](~/media/5.svg)

Tady černý kroužek označuje bit, na kterém je brána řízená, a vertikální kabel označuje jednotnou, která se použije, když ovládací prvek qubit převezme hodnotu $ 1 $ .
Pro zvláštní případy, kdy $ G = X $ a $ g = Z $ uvádíme následující zápis, který popíše řízená verze bran (Všimněte si, že brána řízená-X je [ $ $ bránou CNOT](xref:Microsoft.Quantum.Intrinsic.CNOT)):

<!--- ![](.\media\6.svg) --->
<!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:-->
![Diagram okruhu pro speciální případy řízených bran](~/media/6.svg)

Q# poskytuje metody pro automatické generování řízené verze operace, která bude ukládat programátora z nutnosti kódování těchto operací. Příklad najdete tady:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Operátor měření
Zbývající operace vizualizace v diagramech okruhů je měření.
Měření bere v qubit registraci, měří ho a výsledek vyprodukuje jako klasické informace.
Operace měření je označená symbolem měřiče a vždycky přebírá jako vstup qubit registr (označený plnou čárou) a výstupem klasických informací (označených dvojitou čárou).
Konkrétně takový okruh vypadá takto:

<!--- ![](.\media\7.svg) ---->
<!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:-->
![Symbol reprezentující operaci měření](~/media/7.svg)

Q# implementuje [operátor míry](xref:Microsoft.Quantum.Intrinsic.Measure) pro tento účel.
Další informace najdete v [části o měřeních](xref:microsoft.quantum.libraries.standard.prelude#measurements) .

Podobně, předaný okruh

<!--- ![](.\media\8.svg) --->
<!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:-->
![Diagram okruhu reprezentující kontrolovanou operaci](~/media/8.svg)

poskytuje klasickou bránu, kde $ G $ se aplikuje na bit klasického ovládacího prvku s hodnotou $ 1 $ .

## <a name="teleportation-circuit-diagram"></a>Diagram okruhu přenosu
Pro ilustraci těchto komponent je možná nejlepší výkon
Pomocí entanglement a měření se můžete seznámit s odpovídajícím [Kataem](xref:microsoft.quantum.overview.katas) provozu za provozu, který bude sloužit jako způsob přesunu dat v rámci počítače s procesorem na více procesorech (nebo dokonce mezi vzdálenými počítači s více procesory).
Vzhledem k tomu, že je to v podstatě schopné přesunovat stav, který je v daném qubit, je z jednoho qubit na jiný, bez ohledu na to, jaká hodnota qubit je!
To je nezbytné, aby protokol fungoval v souladu s zákony na mechanismy plnění.
Okruh pro stavovou dopravu je uveden níže. Poskytujeme také verzi okruhu s poznámkou, která ukazuje, jak číst okruh.

<!--- ![](.\media\tp2.svg) { Šířka = 50%} --->
![Okruh vystavování](~/media/tp2.svg)
