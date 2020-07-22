---
<span data-ttu-id="e9ede-101">title: Popis pokročilých konceptů matrice: Přečtěte si o exponenciálních eigenvectors, eigenvalues a matricích, základních nástrojích, které se používají k popisu a simulaci algoritmů.</span><span class="sxs-lookup"><span data-stu-id="e9ede-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="e9ede-102">Autor: QuantumWriter UID: Microsoft.. koncepty. Matrix-rozšířené MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. téma: article No-Loc:</span><span class="sxs-lookup"><span data-stu-id="e9ede-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="e9ede-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-103">"$$"</span></span>
- <span data-ttu-id="e9ede-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-104">"$$"</span></span>
- <span data-ttu-id="e9ede-105">"$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-105">"$"</span></span>
- <span data-ttu-id="e9ede-106">"$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-106">"$"</span></span>
- <span data-ttu-id="e9ede-107">"$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-107">"$"</span></span>
- <span data-ttu-id="e9ede-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-108">"$$"</span></span>
- <span data-ttu-id="e9ede-109">"$$$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-109">"$$$"</span></span>
- <span data-ttu-id="e9ede-110">"$$$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-110">"$$$"</span></span>
- <span data-ttu-id="e9ede-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="e9ede-111">"$$$"</span></span>
- <span data-ttu-id="e9ede-112">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="e9ede-112">"\cdots"</span></span>
- <span data-ttu-id="e9ede-113">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="e9ede-113">"bmatrix"</span></span>
- <span data-ttu-id="e9ede-114">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="e9ede-114">"\ddots"</span></span>
- <span data-ttu-id="e9ede-115">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="e9ede-115">"\equiv"</span></span>
- <span data-ttu-id="e9ede-116">"\sum"</span><span class="sxs-lookup"><span data-stu-id="e9ede-116">"\sum"</span></span>
- <span data-ttu-id="e9ede-117">"\begin"</span><span class="sxs-lookup"><span data-stu-id="e9ede-117">"\begin"</span></span>
- <span data-ttu-id="e9ede-118">"\end"</span><span class="sxs-lookup"><span data-stu-id="e9ede-118">"\end"</span></span>
- <span data-ttu-id="e9ede-119">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="e9ede-119">"\sqrt"</span></span>
- <span data-ttu-id="e9ede-120">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="e9ede-120">"\otimes"</span></span>
- <span data-ttu-id="e9ede-121">"{"</span><span class="sxs-lookup"><span data-stu-id="e9ede-121">"{"</span></span>
- <span data-ttu-id="e9ede-122">"}"</span><span class="sxs-lookup"><span data-stu-id="e9ede-122">"}"</span></span>
- <span data-ttu-id="e9ede-123">"\text"</span><span class="sxs-lookup"><span data-stu-id="e9ede-123">"\text"</span></span>
- <span data-ttu-id="e9ede-124">"\phi"</span><span class="sxs-lookup"><span data-stu-id="e9ede-124">"\phi"</span></span>
- <span data-ttu-id="e9ede-125">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="e9ede-125">"\kappa"</span></span>
- <span data-ttu-id="e9ede-126">"\psi"</span><span class="sxs-lookup"><span data-stu-id="e9ede-126">"\psi"</span></span>
- <span data-ttu-id="e9ede-127">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="e9ede-127">"\alpha"</span></span>
- <span data-ttu-id="e9ede-128">"\beta"</span><span class="sxs-lookup"><span data-stu-id="e9ede-128">"\beta"</span></span>
- <span data-ttu-id="e9ede-129">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="e9ede-129">"\gamma"</span></span>
- <span data-ttu-id="e9ede-130">"\delta"</span><span class="sxs-lookup"><span data-stu-id="e9ede-130">"\delta"</span></span>
- <span data-ttu-id="e9ede-131">"\omega"</span><span class="sxs-lookup"><span data-stu-id="e9ede-131">"\omega"</span></span>
- <span data-ttu-id="e9ede-132">"\bra"</span><span class="sxs-lookup"><span data-stu-id="e9ede-132">"\bra"</span></span>
- <span data-ttu-id="e9ede-133">"\ket"</span><span class="sxs-lookup"><span data-stu-id="e9ede-133">"\ket"</span></span>
- <span data-ttu-id="e9ede-134">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="e9ede-134">"\boldone"</span></span>
- <span data-ttu-id="e9ede-135">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="e9ede-135">"\\\\"</span></span>
- <span data-ttu-id="e9ede-136">"\\"</span><span class="sxs-lookup"><span data-stu-id="e9ede-136">"\\"</span></span>
- <span data-ttu-id="e9ede-137">"="</span><span class="sxs-lookup"><span data-stu-id="e9ede-137">"="</span></span>
- <span data-ttu-id="e9ede-138">"\frac"</span><span class="sxs-lookup"><span data-stu-id="e9ede-138">"\frac"</span></span>
- <span data-ttu-id="e9ede-139">"\text"</span><span class="sxs-lookup"><span data-stu-id="e9ede-139">"\text"</span></span>
- <span data-ttu-id="e9ede-140">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="e9ede-140">"\mapsto"</span></span>
- <span data-ttu-id="e9ede-141">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="e9ede-141">"\dagger"</span></span>
- <span data-ttu-id="e9ede-142">"\to"</span><span class="sxs-lookup"><span data-stu-id="e9ede-142">"\to"</span></span>
- <span data-ttu-id="e9ede-143">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="e9ede-143">"\begin{cases}"</span></span>
- <span data-ttu-id="e9ede-144">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="e9ede-144">"\end{cases}"</span></span>
- <span data-ttu-id="e9ede-145">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="e9ede-145">"\operatorname"</span></span>
- <span data-ttu-id="e9ede-146">"\braket"</span><span class="sxs-lookup"><span data-stu-id="e9ede-146">"\braket"</span></span>
- <span data-ttu-id="e9ede-147">"\id"</span><span class="sxs-lookup"><span data-stu-id="e9ede-147">"\id"</span></span>
- <span data-ttu-id="e9ede-148">"\expect"</span><span class="sxs-lookup"><span data-stu-id="e9ede-148">"\expect"</span></span>
- <span data-ttu-id="e9ede-149">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="e9ede-149">"\defeq"</span></span>
- <span data-ttu-id="e9ede-150">"\variance"</span><span class="sxs-lookup"><span data-stu-id="e9ede-150">"\variance"</span></span>
- <span data-ttu-id="e9ede-151">"\dd"</span><span class="sxs-lookup"><span data-stu-id="e9ede-151">"\dd"</span></span>
- <span data-ttu-id="e9ede-152">"&"</span><span class="sxs-lookup"><span data-stu-id="e9ede-152">"&"</span></span>
- <span data-ttu-id="e9ede-153">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="e9ede-153">"\begin{align}"</span></span>
- <span data-ttu-id="e9ede-154">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="e9ede-154">"\end{align}"</span></span>
- <span data-ttu-id="e9ede-155">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="e9ede-155">"\Lambda"</span></span>
- <span data-ttu-id="e9ede-156">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="e9ede-156">"\lambda"</span></span>
- <span data-ttu-id="e9ede-157">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="e9ede-157">"\Omega"</span></span>
- <span data-ttu-id="e9ede-158">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="e9ede-158">"\mathrm"</span></span>
- <span data-ttu-id="e9ede-159">"\left"</span><span class="sxs-lookup"><span data-stu-id="e9ede-159">"\left"</span></span>
- <span data-ttu-id="e9ede-160">"\right"</span><span class="sxs-lookup"><span data-stu-id="e9ede-160">"\right"</span></span>
- <span data-ttu-id="e9ede-161">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="e9ede-161">"\qquad"</span></span>
- <span data-ttu-id="e9ede-162">"\times"</span><span class="sxs-lookup"><span data-stu-id="e9ede-162">"\times"</span></span>
- <span data-ttu-id="e9ede-163">"\big"</span><span class="sxs-lookup"><span data-stu-id="e9ede-163">"\big"</span></span>
- <span data-ttu-id="e9ede-164">"\langle"</span><span class="sxs-lookup"><span data-stu-id="e9ede-164">"\langle"</span></span>
- <span data-ttu-id="e9ede-165">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="e9ede-165">"\rangle"</span></span>
- <span data-ttu-id="e9ede-166">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="e9ede-166">"\bigg"</span></span>
- <span data-ttu-id="e9ede-167">"\Big"</span><span class="sxs-lookup"><span data-stu-id="e9ede-167">"\Big"</span></span>
- <span data-ttu-id="e9ede-168">"|"</span><span class="sxs-lookup"><span data-stu-id="e9ede-168">"|"</span></span>
- <span data-ttu-id="e9ede-169">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="e9ede-169">"\mathbb"</span></span>
- <span data-ttu-id="e9ede-170">"\vec"</span><span class="sxs-lookup"><span data-stu-id="e9ede-170">"\vec"</span></span>
- <span data-ttu-id="e9ede-171">"\in"</span><span class="sxs-lookup"><span data-stu-id="e9ede-171">"\in"</span></span>
- <span data-ttu-id="e9ede-172">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="e9ede-172">"\texttt"</span></span>
- <span data-ttu-id="e9ede-173">"\ne"</span><span class="sxs-lookup"><span data-stu-id="e9ede-173">"\ne"</span></span>
- <span data-ttu-id="e9ede-174">"<"</span><span class="sxs-lookup"><span data-stu-id="e9ede-174">"<"</span></span>
- <span data-ttu-id="e9ede-175">">"</span><span class="sxs-lookup"><span data-stu-id="e9ede-175">">"</span></span>
- <span data-ttu-id="e9ede-176">"\leq"</span><span class="sxs-lookup"><span data-stu-id="e9ede-176">"\leq"</span></span>
- <span data-ttu-id="e9ede-177">"\geq"</span><span class="sxs-lookup"><span data-stu-id="e9ede-177">"\geq"</span></span>
- <span data-ttu-id="e9ede-178">"~~"</span><span class="sxs-lookup"><span data-stu-id="e9ede-178">"~~"</span></span>
- <span data-ttu-id="e9ede-179">"~"</span><span class="sxs-lookup"><span data-stu-id="e9ede-179">"~"</span></span>
- <span data-ttu-id="e9ede-180">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e9ede-180">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="e9ede-181">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="e9ede-181">"\end{bmatrix}"</span></span>
- <span data-ttu-id="e9ede-182">"\_"</span><span class="sxs-lookup"><span data-stu-id="e9ede-182">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="e9ede-183">Pokročilé koncepty matrice</span><span class="sxs-lookup"><span data-stu-id="e9ede-183">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="e9ede-184">Teď rozšíříme své manipulace s matricemi na [*eigenvalues, eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) a [*exponenciální*](https://en.wikipedia.org/wiki/Matrix_exponential) , které tvoří základní sadu nástrojů, které potřebujeme k popisu a implementaci algoritmů.</span><span class="sxs-lookup"><span data-stu-id="e9ede-184">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="e9ede-185">Eigenvalues a eigenvectors</span><span class="sxs-lookup"><span data-stu-id="e9ede-185">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="e9ede-186">Nechť $ M je $ čtvercová matice a $ v $ je vektor, který není vektorem všechny nuly (tj. vektor se všemi položkami rovnými $ 0 $ ).</span><span class="sxs-lookup"><span data-stu-id="e9ede-186">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="e9ede-187">Řekněme, $ $ že v je [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) M, pokud je v $ $ $ = $ nějakém čísle $ jazyka c MV CV $ .</span><span class="sxs-lookup"><span data-stu-id="e9ede-187">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="e9ede-188">Řekněme, $ $ že c je [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) odpovídající eigenvector $ v $ .</span><span class="sxs-lookup"><span data-stu-id="e9ede-188">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="e9ede-189">Obecně $ může matice M $ transformovat vektor na jakýkoliv jiný vektor, ale eigenvector je zvláštní, protože je ponechán beze změny s výjimkou vynásobený číslem.</span><span class="sxs-lookup"><span data-stu-id="e9ede-189">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="e9ede-190">Všimněte si, že pokud $ $ je v eigenvector s eigenvalue $ c $ , $ AV $ je také eigenvector (pro jakoukoliv nenulovou $ a $ ) se stejným eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="e9ede-190">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="e9ede-191">Například pro matici identity je každý vektor $ v $ eigenvector s eigenvalue $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="e9ede-191">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="e9ede-192">Jako další příklad zvažte [*diagonální matici*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ , která obsahuje pouze nenulové položky na diagonále:</span><span class="sxs-lookup"><span data-stu-id="e9ede-192">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="e9ede-193">d_1 & 0 0 0 & d_2 0 0 0 \\\\ & & \\\\ & & D_3 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="e9ede-193">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="e9ede-194">Vektory</span><span class="sxs-lookup"><span data-stu-id="e9ede-194">The vectors</span></span>

$$<span data-ttu-id="e9ede-195">\begin{bmatrix}1 \\\\ 0 \\\\ \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} a \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="e9ede-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="e9ede-196">eigenvectors z této matrice s eigenvalues $ D_1 $ , $ d_2 $ a $ D_3 $ , v uvedeném pořadí.</span><span class="sxs-lookup"><span data-stu-id="e9ede-196">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="e9ede-197">Pokud $ D_1 $ , $ d_2 $ a $ D_3 $ mají odlišná čísla, pak jsou tyto vektory (a jejich násobky) jediným eigenvectors matice $ d $ . Obecně platí, že pro diagonální matrici je snadné číst z eigenvalues a eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="e9ede-197">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="e9ede-198">Eigenvalues jsou všechna čísla, která se zobrazují na diagonále a jejich příslušné eigenvectors jsou vektory jednotek s jednou položkou rovnající se $ 1 $ a zbývající položky rovnající se $ 0 $ .</span><span class="sxs-lookup"><span data-stu-id="e9ede-198">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="e9ede-199">Všimněte si výše uvedeného příkladu, že eigenvectors $ D $ tvoří základ pro trojrozměrné $ $ vektory.</span><span class="sxs-lookup"><span data-stu-id="e9ede-199">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="e9ede-200">Základem je sada vektorů, což znamená, že každý vektor lze zapsat jako lineární kombinaci.</span><span class="sxs-lookup"><span data-stu-id="e9ede-200">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="e9ede-201">Explicitní, $ v_1 $ , $ v_2 $ a $ v_3 $ tvoří základ, pokud je libovolný vektor $ v $ zápisu jako $ v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ pro některá čísla $ A_1 $ , $ A_2 $ a $ a_3 $ .</span><span class="sxs-lookup"><span data-stu-id="e9ede-201">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="e9ede-202">Odvolání, že matice Hermitian (označovaná také jako samostatně rovnocenná) je složitá čtvercová matice, která se rovná své vlastní složitosti sdružené transponovat, zatímco Jednotková matice je složitá čtvercová matice, jejíž inverzní funkce se rovná jejímu sousedovi nebo složitě sdružené hodnotě.</span><span class="sxs-lookup"><span data-stu-id="e9ede-202">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="e9ede-203">V případě Hermitian a maticových matric, které jsou v podstatě jenom pro tyto matrice, je k dispozici obecný výsledek, který je známý jako [*spektrální věta*](https://en.wikipedia.org/wiki/Spectral_theorem), který vyhodnotí následující: pro každou Hermitian nebo jednotkovou matrici $ m $ existuje $ $ pro každou $ = \dagger $ úhlopříčnou matrici $ $ s jednotkou v jednotkách u ^ D u. Kromě toho diagonální položky $ D $ budou eigenvalues $ M $ .</span><span class="sxs-lookup"><span data-stu-id="e9ede-203">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="e9ede-204">Už víte, jak vypočítat eigenvalues a eigenvectors úhlopříčné matrice $ D $ . Pomocí tohoto věta víme, že pokud $ v $ je eigenvector z $ D $ s eigenvalue $ c $ , tj. $ DV = CV $ , pak $ U ^ \dagger v $ bude eigenvector z $ M $ s eigenvalue $ c $ .</span><span class="sxs-lookup"><span data-stu-id="e9ede-204">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="e9ede-205">Důvodem je to, že</span><span class="sxs-lookup"><span data-stu-id="e9ede-205">This is because</span></span>

$$<span data-ttu-id="e9ede-206">M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = U ^ \dagger D v = c u ^ \dagger v.$$</span><span class="sxs-lookup"><span data-stu-id="e9ede-206">M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="e9ede-207">Exponenciální matice</span><span class="sxs-lookup"><span data-stu-id="e9ede-207">Matrix Exponentials</span></span>
<span data-ttu-id="e9ede-208">Exponenciální funkce lze definovat také pomocí [*exponenciálního*](https://en.wikipedia.org/wiki/Matrix_exponential) analogie matice.</span><span class="sxs-lookup"><span data-stu-id="e9ede-208">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="e9ede-209">Matice exponenciálního exponentu matice $ a $ může být vyjádřena jako</span><span class="sxs-lookup"><span data-stu-id="e9ede-209">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="e9ede-210">e ^ A = \boldone + a + \frac { a ^ 2 } { 2! } + \frac { A ^ 3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="e9ede-210">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="e9ede-211">To je důležité kvůli tomu, že při vývoji v mechanickém čase je popsána jednotná matice formuláře $ e ^ { IB } $ pro Hermitian Matrix $ B $ .  Z tohoto důvodu je provádění exponenciálních exponenciálních výpočetních operací základní částí výpočetní funkce a jako takové Q # nabízí vnitřní rutiny pro popis těchto operací.</span><span class="sxs-lookup"><span data-stu-id="e9ede-211">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="e9ede-212">Existuje mnoho způsobů, jak na klasický počítač vypočítat exponenciální exponenciálu matrice, a obecně numericky přibližně fraught s Peril.</span><span class="sxs-lookup"><span data-stu-id="e9ede-212">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="e9ede-213">Viz [*Cleve Moler a Charles Van půjčka. "Devatenáct podezřelých způsoby výpočtu exponenciálního podílu matice." SIAM revize 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) pro další informace o problémech, které se týkají.</span><span class="sxs-lookup"><span data-stu-id="e9ede-213">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="e9ede-214">Nejjednodušší způsob, jak porozumět tomu, jak vypočítat exponenciální část matice, je prostřednictvím eigenvalues a eigenvectors této matrice.</span><span class="sxs-lookup"><span data-stu-id="e9ede-214">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="e9ede-215">Konkrétně věta spektrální popis uvádí, že pro každou Hermitian nebo jednotnou matrici $ $ existuje jednotná matice $ u $ a šikmá matice $ D $ tak, že $ = u ^ \dagger D u $ .  Vzhledem k tomu, že vlastnosti unitarity máme $ ^ 2 = u ^ \dagger d ^ 2 u $ a podobně pro všechny síly $ p $ $ a ^ p = u ^ \dagger D ^ p u $ .  Pokud tuto část nasadíme do definice operátora exponenciálního operátoru, získáte:</span><span class="sxs-lookup"><span data-stu-id="e9ede-215">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="e9ede-216">e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 0 0 & \cdots & \\\\ & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN } ) \end{bmatrix} U.$$</span><span class="sxs-lookup"><span data-stu-id="e9ede-216">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="e9ede-217">Jinými slovy, pokud Transformujte na eigenbasis matice $ a $ potom výpočet exponenciální hodnoty matice je ekvivalentní s výpočetem obyčejného exponenciálního exponenciálního eigenvaluesu matice.</span><span class="sxs-lookup"><span data-stu-id="e9ede-217">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="e9ede-218">Tolik operací v případě, že výpočetní výkon zahrnuje provádění exponenciálních exponenciálních výpočetních funkcí, je tento způsob transformace do eigenbasis matice, aby se zjednodušila i četnost exponenciálního zobrazení operátorů.</span><span class="sxs-lookup"><span data-stu-id="e9ede-218">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="e9ede-219">Další užitečnou vlastností je, že $ b $ je v obou i Hermitian, tj. b $ = b ^ { -1 } = b ^ a \dagger $ $ B ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="e9ede-219">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="e9ede-220">Když použijete toto pravidlo na výše uvedené rozšíření matice exponenciálního součtu a $ \boldone $ $ spojíte a a B $ , může to být vidět pro libovolnou skutečnou hodnotu $ x $ identity.</span><span class="sxs-lookup"><span data-stu-id="e9ede-220">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

$$<span data-ttu-id="e9ede-221">e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$</span><span class="sxs-lookup"><span data-stu-id="e9ede-221">e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="e9ede-222">ryby.</span><span class="sxs-lookup"><span data-stu-id="e9ede-222">holds.</span></span> <span data-ttu-id="e9ede-223">Tento zdvih je zvláště užitečný, protože umožňuje odůvodnění exponenciálních exponenciálních akcí, a to i v případě, že je rozměr $ b $ exponenciálně velký, pro zvláštní případ, $ Pokud $ je b jednotkou a Hermitian.</span><span class="sxs-lookup"><span data-stu-id="e9ede-223">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
