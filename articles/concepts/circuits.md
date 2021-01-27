---
<span data-ttu-id="e0aed-101">title: Popis okruhu provozu: Přečtěte si, jak vizuálně znázornit jednoduché a komplexní operace s využitím diagramů okruhu.</span><span class="sxs-lookup"><span data-stu-id="e0aed-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="e0aed-102">Autor: QuantumWriter UID: Microsoft.. koncepty. okruhy MS. Author: v-benbra MS. Date: 12/11/2017 MS. téma: koncepční No-Loc:</span><span class="sxs-lookup"><span data-stu-id="e0aed-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="e0aed-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="e0aed-103">"Q#"</span></span>
- <span data-ttu-id="e0aed-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="e0aed-104">"$$v"</span></span>
- <span data-ttu-id="e0aed-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="e0aed-105">"$$"</span></span>
- <span data-ttu-id="e0aed-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="e0aed-106">"$$"</span></span>
- <span data-ttu-id="e0aed-107">"$"</span><span class="sxs-lookup"><span data-stu-id="e0aed-107">"$"</span></span>
- <span data-ttu-id="e0aed-108">"$"</span><span class="sxs-lookup"><span data-stu-id="e0aed-108">"$"</span></span>
- <span data-ttu-id="e0aed-109">"$"</span><span class="sxs-lookup"><span data-stu-id="e0aed-109">"$"</span></span>
- <span data-ttu-id="e0aed-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="e0aed-110">"$$"</span></span>
- <span data-ttu-id="e0aed-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="e0aed-111">"\cdots"</span></span>
- <span data-ttu-id="e0aed-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="e0aed-112">"bmatrix"</span></span>
- <span data-ttu-id="e0aed-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="e0aed-113">"\ddots"</span></span>
- <span data-ttu-id="e0aed-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="e0aed-114">"\equiv"</span></span>
- <span data-ttu-id="e0aed-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="e0aed-115">"\sum"</span></span>
- <span data-ttu-id="e0aed-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="e0aed-116">"\begin"</span></span>
- <span data-ttu-id="e0aed-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="e0aed-117">"\end"</span></span>
- <span data-ttu-id="e0aed-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="e0aed-118">"\sqrt"</span></span>
- <span data-ttu-id="e0aed-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="e0aed-119">"\otimes"</span></span>
- <span data-ttu-id="e0aed-120">"{"</span><span class="sxs-lookup"><span data-stu-id="e0aed-120">"{"</span></span>
- <span data-ttu-id="e0aed-121">"}"</span><span class="sxs-lookup"><span data-stu-id="e0aed-121">"}"</span></span>
- <span data-ttu-id="e0aed-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="e0aed-122">"\text"</span></span>
- <span data-ttu-id="e0aed-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="e0aed-123">"\phi"</span></span>
- <span data-ttu-id="e0aed-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="e0aed-124">"\kappa"</span></span>
- <span data-ttu-id="e0aed-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="e0aed-125">"\psi"</span></span>
- <span data-ttu-id="e0aed-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="e0aed-126">"\alpha"</span></span>
- <span data-ttu-id="e0aed-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="e0aed-127">"\beta"</span></span>
- <span data-ttu-id="e0aed-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="e0aed-128">"\gamma"</span></span>
- <span data-ttu-id="e0aed-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="e0aed-129">"\delta"</span></span>
- <span data-ttu-id="e0aed-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="e0aed-130">"\omega"</span></span>
- <span data-ttu-id="e0aed-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="e0aed-131">"\bra"</span></span>
- <span data-ttu-id="e0aed-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="e0aed-132">"\ket"</span></span>
- <span data-ttu-id="e0aed-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="e0aed-133">"\boldone"</span></span>
- <span data-ttu-id="e0aed-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="e0aed-134">"\\\\"</span></span>
- <span data-ttu-id="e0aed-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="e0aed-135">"\\"</span></span>
- <span data-ttu-id="e0aed-136">"="</span><span class="sxs-lookup"><span data-stu-id="e0aed-136">"="</span></span>
- <span data-ttu-id="e0aed-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="e0aed-137">"\frac"</span></span>
- <span data-ttu-id="e0aed-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="e0aed-138">"\text"</span></span>
- <span data-ttu-id="e0aed-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="e0aed-139">"\mapsto"</span></span>
- <span data-ttu-id="e0aed-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="e0aed-140">"\dagger"</span></span>
- <span data-ttu-id="e0aed-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="e0aed-141">"\to"</span></span>
- <span data-ttu-id="e0aed-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="e0aed-142">"\begin{cases}"</span></span>
- <span data-ttu-id="e0aed-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="e0aed-143">"\end{cases}"</span></span>
- <span data-ttu-id="e0aed-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="e0aed-144">"\operatorname"</span></span>
- <span data-ttu-id="e0aed-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="e0aed-145">"\braket"</span></span>
- <span data-ttu-id="e0aed-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="e0aed-146">"\id"</span></span>
- <span data-ttu-id="e0aed-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="e0aed-147">"\expect"</span></span>
- <span data-ttu-id="e0aed-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="e0aed-148">"\defeq"</span></span>
- <span data-ttu-id="e0aed-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="e0aed-149">"\variance"</span></span>
- <span data-ttu-id="e0aed-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="e0aed-150">"\dd"</span></span>
- <span data-ttu-id="e0aed-151">"&"</span><span class="sxs-lookup"><span data-stu-id="e0aed-151">"&"</span></span>
- <span data-ttu-id="e0aed-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="e0aed-152">"\begin{align}"</span></span>
- <span data-ttu-id="e0aed-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="e0aed-153">"\end{align}"</span></span>
- <span data-ttu-id="e0aed-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="e0aed-154">"\Lambda"</span></span>
- <span data-ttu-id="e0aed-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="e0aed-155">"\lambda"</span></span>
- <span data-ttu-id="e0aed-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="e0aed-156">"\Omega"</span></span>
- <span data-ttu-id="e0aed-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="e0aed-157">"\mathrm"</span></span>
- <span data-ttu-id="e0aed-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="e0aed-158">"\left"</span></span>
- <span data-ttu-id="e0aed-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="e0aed-159">"\right"</span></span>
- <span data-ttu-id="e0aed-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="e0aed-160">"\qquad"</span></span>
- <span data-ttu-id="e0aed-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="e0aed-161">"\times"</span></span>
- <span data-ttu-id="e0aed-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="e0aed-162">"\big"</span></span>
- <span data-ttu-id="e0aed-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="e0aed-163">"\langle"</span></span>
- <span data-ttu-id="e0aed-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="e0aed-164">"\rangle"</span></span>
- <span data-ttu-id="e0aed-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="e0aed-165">"\bigg"</span></span>
- <span data-ttu-id="e0aed-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="e0aed-166">"\Big"</span></span>
- <span data-ttu-id="e0aed-167">"|"</span><span class="sxs-lookup"><span data-stu-id="e0aed-167">"|"</span></span>
- <span data-ttu-id="e0aed-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="e0aed-168">"\mathbb"</span></span>
- <span data-ttu-id="e0aed-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="e0aed-169">"\vec"</span></span>
- <span data-ttu-id="e0aed-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="e0aed-170">"\in"</span></span>
- <span data-ttu-id="e0aed-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="e0aed-171">"\texttt"</span></span>
- <span data-ttu-id="e0aed-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="e0aed-172">"\ne"</span></span>
- <span data-ttu-id="e0aed-173">"<"</span><span class="sxs-lookup"><span data-stu-id="e0aed-173">"<"</span></span>
- <span data-ttu-id="e0aed-174">">"</span><span class="sxs-lookup"><span data-stu-id="e0aed-174">">"</span></span>
- <span data-ttu-id="e0aed-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="e0aed-175">"\leq"</span></span>
- <span data-ttu-id="e0aed-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="e0aed-176">"\geq"</span></span>
- <span data-ttu-id="e0aed-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="e0aed-177">"~~"</span></span>
- <span data-ttu-id="e0aed-178">"~"</span><span class="sxs-lookup"><span data-stu-id="e0aed-178">"~"</span></span>
- <span data-ttu-id="e0aed-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e0aed-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="e0aed-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e0aed-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="e0aed-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="e0aed-181">"\_"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="e0aed-182">Okruhy</span><span class="sxs-lookup"><span data-stu-id="e0aed-182">Quantum Circuits</span></span>
<span data-ttu-id="e0aed-183">Vezměte v úvahu okamžik, kdy bude jednotná transformace $ \text { CNOT } _ { 01 } (H \otimes 1) $ .</span><span class="sxs-lookup"><span data-stu-id="e0aed-183">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="e0aed-184">Tato sekvence brány má zásadní význam pro výpočetní výkon, protože vytváří qubit stav s maximální entangled:</span><span class="sxs-lookup"><span data-stu-id="e0aed-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="e0aed-185">$$\mathrm{CNOT } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left ( \ket { 00 }  +  \ket { 11 } \right ),$$</span><span class="sxs-lookup"><span data-stu-id="e0aed-185">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="e0aed-186">Operace s touto nebo větší složitou složitostí jsou všudypřítomný s využitím algoritmů pro provozní a přístupnosti chyb, takže by měly být skvělé, že pro svou vizualizaci se používá jednoduchá metoda, která se nazývá *diagram okruhu*.</span><span class="sxs-lookup"><span data-stu-id="e0aed-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="e0aed-187">Diagram okruhu pro přípravu tohoto maximálního entangledého stavu je:</span><span class="sxs-lookup"><span data-stu-id="e0aed-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="e0aed-188"><!--- ![](.\media\1.svg) ---></span><span class="sxs-lookup"><span data-stu-id="e0aed-188"><!--- ![](.\media\1.svg) ---></span></span>
<span data-ttu-id="e0aed-189"><!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:--></span><span class="sxs-lookup"><span data-stu-id="e0aed-189"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="e0aed-190">![Diagram okruhu pro maximální entangled stav qubit](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-190">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="e0aed-191">Konvence diagramu pro okruhy</span><span class="sxs-lookup"><span data-stu-id="e0aed-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="e0aed-192">Tento vizuál pro práci s více operačními operacemi může být mnohem snadno digestible než zapsání jeho ekvivalentní matrice, jakmile pochopíte konvence pro vyjádření okruhu.</span><span class="sxs-lookup"><span data-stu-id="e0aed-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="e0aed-193">Tyto konvence prověříme níže.</span><span class="sxs-lookup"><span data-stu-id="e0aed-193">We review these conventions below.</span></span>

<span data-ttu-id="e0aed-194">V diagramu okruhu každá plná čára znázorňuje qubit nebo více všeobecně qubit Registry.</span><span class="sxs-lookup"><span data-stu-id="e0aed-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="e0aed-195">Podle konvence je horním řádkem qubit registr $ 0 $ a zbytek je označený sekvenčně.</span><span class="sxs-lookup"><span data-stu-id="e0aed-195">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="e0aed-196">Výše uvedený příklad okruhu je znázorněný na dvou qubits (nebo ekvivalentních dvou registrech, které se skládají z jednoho qubit).</span><span class="sxs-lookup"><span data-stu-id="e0aed-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="e0aed-197">Brány fungující na jednom nebo více registrech qubit jsou označeny jako pole.</span><span class="sxs-lookup"><span data-stu-id="e0aed-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="e0aed-198">Například symbol</span><span class="sxs-lookup"><span data-stu-id="e0aed-198">For example, the symbol</span></span>

<span data-ttu-id="e0aed-199"><!--- ![](.\media\2.svg) ---></span><span class="sxs-lookup"><span data-stu-id="e0aed-199"><!--- ![](.\media\2.svg) ---></span></span>
<span data-ttu-id="e0aed-200"><!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:--></span><span class="sxs-lookup"><span data-stu-id="e0aed-200"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="e0aed-201">![Symbol pro Hadamard operace fungující v registru s jedním qubit](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-201">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="e0aed-202">je [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) operace fungující v registru s jedním qubit.</span><span class="sxs-lookup"><span data-stu-id="e0aed-202">is a [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="e0aed-203">Vyřazení z více procesorů je seřazené v chronologickém pořadí s bránou, která je nejvíce vlevo, jako brána se jako první používá pro qubits.</span><span class="sxs-lookup"><span data-stu-id="e0aed-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="e0aed-204">Jinými slovy, pokud se dráty naformátují jako držící stav, vodiče přinášejí stav u všech bran v diagramu zleva doprava.</span><span class="sxs-lookup"><span data-stu-id="e0aed-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="e0aed-205">Řekněme, že</span><span class="sxs-lookup"><span data-stu-id="e0aed-205">That is to say</span></span> 

<span data-ttu-id="e0aed-206"><!--- ![](.\media\3.svg) ---></span><span class="sxs-lookup"><span data-stu-id="e0aed-206"><!--- ![](.\media\3.svg) ---></span></span>
<span data-ttu-id="e0aed-207"><!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:--></span><span class="sxs-lookup"><span data-stu-id="e0aed-207"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="e0aed-208">![Diagram protiprocesorů používaných v zleva doprava](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-208">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="e0aed-209">je jednotná maticová matice $ certifikátů $ .</span><span class="sxs-lookup"><span data-stu-id="e0aed-209">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="e0aed-210">Násobení matice dodržuje opačnou konvenci: nejprve se použije matice nejvyšší výše.</span><span class="sxs-lookup"><span data-stu-id="e0aed-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="e0aed-211">V diagramech okruhu ve službě pro vytváření koncových procesorů se ale jako první používá brána vlevo.</span><span class="sxs-lookup"><span data-stu-id="e0aed-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="e0aed-212">Tento rozdíl může v některých případech vést k nejasnostem, takže je důležité si všimnout tohoto významného rozdílu mezi lineárním zápisem algebraických a diagramy okruhu.</span><span class="sxs-lookup"><span data-stu-id="e0aed-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="e0aed-213">Vstupy a výstupy okruhů</span><span class="sxs-lookup"><span data-stu-id="e0aed-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="e0aed-214">Všechny předchozí uvedené příklady mají přesně stejný počet vodičů (qubits), jako je počet vodičů v bráně pro plnění.</span><span class="sxs-lookup"><span data-stu-id="e0aed-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="e0aed-215">Je možné, že se zpočátku jeví jako přiměřená, že okruhy by mohly mít více nebo méně výstupů, než jsou vstupy obecně.</span><span class="sxs-lookup"><span data-stu-id="e0aed-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="e0aed-216">To však není možné, protože všechny provozní operace šetří měření, jsou jednotně a tedy vratné.</span><span class="sxs-lookup"><span data-stu-id="e0aed-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="e0aed-217">Pokud neobsahují stejný počet výstupů jako vstupy, které by nebyly vratné, a proto nejsou v rozporu.</span><span class="sxs-lookup"><span data-stu-id="e0aed-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="e0aed-218">Z tohoto důvodu musí mít jakékoli pole vykreslené v diagramu okruhu přesně stejný počet vodičů, kteří ho vstupují při jeho ukončení.</span><span class="sxs-lookup"><span data-stu-id="e0aed-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="e0aed-219">Diagramy okruhu s více qubit se podobají podobným konvencím pro qubit.</span><span class="sxs-lookup"><span data-stu-id="e0aed-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="e0aed-220">V rámci objasnění příkladu můžeme definovat qubit jednotkovou operaci $ B $ , která bude $ (H S \otimes ×), $ a vyjadřovat ekvivalent okruhu jako</span><span class="sxs-lookup"><span data-stu-id="e0aed-220">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<span data-ttu-id="e0aed-221"><!--- ![](.\media\4.svg) ---></span><span class="sxs-lookup"><span data-stu-id="e0aed-221"><!--- ![](.\media\4.svg) ---></span></span>
<span data-ttu-id="e0aed-222"><!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:--></span><span class="sxs-lookup"><span data-stu-id="e0aed-222"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="e0aed-223">![Diagram okruhu s qubit jednotkovou operací](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-223">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="e0aed-224">V $ $ závislosti na kontextu, ve kterém se okruh používá, můžeme také zobrazit B jako akce v jednom qubit registru, nikoli 2 1-qubit Registry.</span><span class="sxs-lookup"><span data-stu-id="e0aed-224">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="e0aed-225">Nejužitečnější vlastností takových diagramů s abstraktním okruhem je pravděpodobně to, že umožňují složitosti složitých algoritmů na vysoké úrovni, aniž by bylo nutné je kompilovat na základní brány.</span><span class="sxs-lookup"><span data-stu-id="e0aed-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="e0aed-226">To znamená, že můžete získat Intuition o toku dat pro velký algoritmus, aniž byste museli porozumět všem podrobnostem o tom, jak jednotlivé podrutiny v rámci algoritmu fungují.</span><span class="sxs-lookup"><span data-stu-id="e0aed-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="e0aed-227">Řízené brány</span><span class="sxs-lookup"><span data-stu-id="e0aed-227">Controlled gates</span></span>
<span data-ttu-id="e0aed-228">Druhá konstrukce, která je integrovaná do qubitch okruhů, je řídicích diagramů.</span><span class="sxs-lookup"><span data-stu-id="e0aed-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="e0aed-229">Akce u jednorázového množství, které je jednou kontrolované bránou $ \Lambda (g) $ , kde jedna hodnota qubit řídí aplikaci $ G, se dá pochopit tak, že se $ podíváme na následující příklad vstupu stavu produktu $ \Lambda (G) ( \alpha \ket { 0 }  +  \beta \ket { 1 } ) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } G \ket { \psi } $ . To znamená, že řízená brána použije $ G $ na registr, který obsahuje $ \psi $ if a jenom v případě, že ovládací prvek qubit přebírá hodnotu $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e0aed-229">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$. That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="e0aed-230">Obecně popisujeme tyto řízené operace v diagramech okruhů jako</span><span class="sxs-lookup"><span data-stu-id="e0aed-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="e0aed-231"><!--- ![](.\media\5.svg) ---></span><span class="sxs-lookup"><span data-stu-id="e0aed-231"><!--- ![](.\media\5.svg) ---></span></span>
<span data-ttu-id="e0aed-232"><!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:--></span><span class="sxs-lookup"><span data-stu-id="e0aed-232"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="e0aed-233">![Diagram okruhu samostatně kontrolované brány](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-233">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="e0aed-234">Tady černý kroužek označuje bit, na kterém je brána řízená, a vertikální kabel označuje jednotnou, která se použije, když ovládací prvek qubit převezme hodnotu $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e0aed-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="e0aed-235">Pro zvláštní případy, kdy $ G = X $ a $ g = Z $ uvádíme následující zápis, který popíše řízená verze bran (Všimněte si, že brána řízená-X je [ $ $ bránou CNOT](xref:Microsoft.Quantum.Intrinsic.CNOT)):</span><span class="sxs-lookup"><span data-stu-id="e0aed-235">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:Microsoft.Quantum.Intrinsic.CNOT)):</span></span>

<span data-ttu-id="e0aed-236"><!--- ![](.\media\6.svg) ---></span><span class="sxs-lookup"><span data-stu-id="e0aed-236"><!--- ![](.\media\6.svg) ---></span></span>
<span data-ttu-id="e0aed-237"><!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:--></span><span class="sxs-lookup"><span data-stu-id="e0aed-237"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="e0aed-238">![Diagram okruhu pro speciální případy řízených bran](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-238">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="e0aed-239">Q# poskytuje metody pro automatické generování řízené verze operace, která bude ukládat programátora z nutnosti kódování těchto operací.</span><span class="sxs-lookup"><span data-stu-id="e0aed-239">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="e0aed-240">Příklad najdete tady:</span><span class="sxs-lookup"><span data-stu-id="e0aed-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="e0aed-241">Operátor měření</span><span class="sxs-lookup"><span data-stu-id="e0aed-241">Measurement operator</span></span>
<span data-ttu-id="e0aed-242">Zbývající operace vizualizace v diagramech okruhů je měření.</span><span class="sxs-lookup"><span data-stu-id="e0aed-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="e0aed-243">Měření bere v qubit registraci, měří ho a výsledek vyprodukuje jako klasické informace.</span><span class="sxs-lookup"><span data-stu-id="e0aed-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="e0aed-244">Operace měření je označená symbolem měřiče a vždycky přebírá jako vstup qubit registr (označený plnou čárou) a výstupem klasických informací (označených dvojitou čárou).</span><span class="sxs-lookup"><span data-stu-id="e0aed-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="e0aed-245">Konkrétně takový okruh vypadá takto:</span><span class="sxs-lookup"><span data-stu-id="e0aed-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="e0aed-246"><!--- ![](.\media\7.svg) ----></span><span class="sxs-lookup"><span data-stu-id="e0aed-246"><!--- ![](.\media\7.svg) ----></span></span>
<span data-ttu-id="e0aed-247"><!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:--></span><span class="sxs-lookup"><span data-stu-id="e0aed-247"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="e0aed-248">![Symbol reprezentující operaci měření](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-248">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="e0aed-249">Q# implementuje [operátor míry](xref:Microsoft.Quantum.Intrinsic.Measure) pro tento účel.</span><span class="sxs-lookup"><span data-stu-id="e0aed-249">Q# implements a [Measure operator](xref:Microsoft.Quantum.Intrinsic.Measure) for this purpose.</span></span>
<span data-ttu-id="e0aed-250">Další informace najdete v [části o měřeních](xref:microsoft.quantum.libraries.standard.prelude#measurements) .</span><span class="sxs-lookup"><span data-stu-id="e0aed-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="e0aed-251">Podobně, předaný okruh</span><span class="sxs-lookup"><span data-stu-id="e0aed-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="e0aed-252"><!--- ![](.\media\8.svg) ---></span><span class="sxs-lookup"><span data-stu-id="e0aed-252"><!--- ![](.\media\8.svg) ---></span></span>
<span data-ttu-id="e0aed-253"><!--Nemůžou najít způsob, jak ho snadno zarovnat... pravděpodobně je nutné rozšíření:--></span><span class="sxs-lookup"><span data-stu-id="e0aed-253"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="e0aed-254">![Diagram okruhu reprezentující kontrolovanou operaci](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-254">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="e0aed-255">poskytuje klasickou bránu, kde $ G $ se aplikuje na bit klasického ovládacího prvku s hodnotou $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e0aed-255">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="e0aed-256">Diagram okruhu přenosu</span><span class="sxs-lookup"><span data-stu-id="e0aed-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="e0aed-257">Pro ilustraci těchto komponent je možná nejlepší výkon</span><span class="sxs-lookup"><span data-stu-id="e0aed-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="e0aed-258">Pomocí entanglement a měření se můžete seznámit s odpovídajícím [Kataem](xref:microsoft.quantum.overview.katas) provozu za provozu, který bude sloužit jako způsob přesunu dat v rámci počítače s procesorem na více procesorech (nebo dokonce mezi vzdálenými počítači s více procesory).</span><span class="sxs-lookup"><span data-stu-id="e0aed-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="e0aed-259">Vzhledem k tomu, že je to v podstatě schopné přesunovat stav, který je v daném qubit, je z jednoho qubit na jiný, bez ohledu na to, jaká hodnota qubit je!</span><span class="sxs-lookup"><span data-stu-id="e0aed-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="e0aed-260">To je nezbytné, aby protokol fungoval v souladu s zákony na mechanismy plnění.</span><span class="sxs-lookup"><span data-stu-id="e0aed-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="e0aed-261">Okruh pro stavovou dopravu je uveden níže. Poskytujeme také verzi okruhu s poznámkou, která ukazuje, jak číst okruh.</span><span class="sxs-lookup"><span data-stu-id="e0aed-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="e0aed-262"><!--- ![](.\media\tp2.svg) { Šířka = 50%} ---></span><span class="sxs-lookup"><span data-stu-id="e0aed-262"><!--- ![](.\media\tp2.svg){ width=50% } ---></span></span>
<span data-ttu-id="e0aed-263">![Okruh vystavování](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="e0aed-263">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
