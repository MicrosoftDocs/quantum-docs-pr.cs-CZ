---
<span data-ttu-id="251c1-101">title: vektory a matice v popisu pro výpočetní výkon – Popis: Naučte se základy práce s vektory a maticemi.</span><span class="sxs-lookup"><span data-stu-id="251c1-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="251c1-102">Autor: QuantumWriter UID: Microsoft.. koncepty. Vectors MS. Author: v-benbra MS. Date: 12/11/2017 MS. téma: No-Loc:</span><span class="sxs-lookup"><span data-stu-id="251c1-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="251c1-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="251c1-103">"Q#"</span></span>
- <span data-ttu-id="251c1-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="251c1-104">"$$v"</span></span>
- <span data-ttu-id="251c1-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="251c1-105">"$$"</span></span>
- <span data-ttu-id="251c1-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="251c1-106">"$$"</span></span>
- <span data-ttu-id="251c1-107">"$"</span><span class="sxs-lookup"><span data-stu-id="251c1-107">"$"</span></span>
- <span data-ttu-id="251c1-108">"$"</span><span class="sxs-lookup"><span data-stu-id="251c1-108">"$"</span></span>
- <span data-ttu-id="251c1-109">"$"</span><span class="sxs-lookup"><span data-stu-id="251c1-109">"$"</span></span>
- <span data-ttu-id="251c1-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="251c1-110">"$$"</span></span>
- <span data-ttu-id="251c1-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="251c1-111">"\cdots"</span></span>
- <span data-ttu-id="251c1-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="251c1-112">"bmatrix"</span></span>
- <span data-ttu-id="251c1-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="251c1-113">"\ddots"</span></span>
- <span data-ttu-id="251c1-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="251c1-114">"\equiv"</span></span>
- <span data-ttu-id="251c1-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="251c1-115">"\sum"</span></span>
- <span data-ttu-id="251c1-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="251c1-116">"\begin"</span></span>
- <span data-ttu-id="251c1-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="251c1-117">"\end"</span></span>
- <span data-ttu-id="251c1-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="251c1-118">"\sqrt"</span></span>
- <span data-ttu-id="251c1-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="251c1-119">"\otimes"</span></span>
- <span data-ttu-id="251c1-120">"{"</span><span class="sxs-lookup"><span data-stu-id="251c1-120">"{"</span></span>
- <span data-ttu-id="251c1-121">"}"</span><span class="sxs-lookup"><span data-stu-id="251c1-121">"}"</span></span>
- <span data-ttu-id="251c1-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="251c1-122">"\text"</span></span>
- <span data-ttu-id="251c1-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="251c1-123">"\phi"</span></span>
- <span data-ttu-id="251c1-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="251c1-124">"\kappa"</span></span>
- <span data-ttu-id="251c1-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="251c1-125">"\psi"</span></span>
- <span data-ttu-id="251c1-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="251c1-126">"\alpha"</span></span>
- <span data-ttu-id="251c1-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="251c1-127">"\beta"</span></span>
- <span data-ttu-id="251c1-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="251c1-128">"\gamma"</span></span>
- <span data-ttu-id="251c1-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="251c1-129">"\delta"</span></span>
- <span data-ttu-id="251c1-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="251c1-130">"\omega"</span></span>
- <span data-ttu-id="251c1-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="251c1-131">"\bra"</span></span>
- <span data-ttu-id="251c1-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="251c1-132">"\ket"</span></span>
- <span data-ttu-id="251c1-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="251c1-133">"\boldone"</span></span>
- <span data-ttu-id="251c1-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="251c1-134">"\\\\"</span></span>
- <span data-ttu-id="251c1-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="251c1-135">"\\"</span></span>
- <span data-ttu-id="251c1-136">"="</span><span class="sxs-lookup"><span data-stu-id="251c1-136">"="</span></span>
- <span data-ttu-id="251c1-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="251c1-137">"\frac"</span></span>
- <span data-ttu-id="251c1-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="251c1-138">"\text"</span></span>
- <span data-ttu-id="251c1-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="251c1-139">"\mapsto"</span></span>
- <span data-ttu-id="251c1-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="251c1-140">"\dagger"</span></span>
- <span data-ttu-id="251c1-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="251c1-141">"\to"</span></span>
- <span data-ttu-id="251c1-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="251c1-142">"\begin{cases}"</span></span>
- <span data-ttu-id="251c1-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="251c1-143">"\end{cases}"</span></span>
- <span data-ttu-id="251c1-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="251c1-144">"\operatorname"</span></span>
- <span data-ttu-id="251c1-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="251c1-145">"\braket"</span></span>
- <span data-ttu-id="251c1-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="251c1-146">"\id"</span></span>
- <span data-ttu-id="251c1-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="251c1-147">"\expect"</span></span>
- <span data-ttu-id="251c1-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="251c1-148">"\defeq"</span></span>
- <span data-ttu-id="251c1-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="251c1-149">"\variance"</span></span>
- <span data-ttu-id="251c1-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="251c1-150">"\dd"</span></span>
- <span data-ttu-id="251c1-151">"&"</span><span class="sxs-lookup"><span data-stu-id="251c1-151">"&"</span></span>
- <span data-ttu-id="251c1-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="251c1-152">"\begin{align}"</span></span>
- <span data-ttu-id="251c1-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="251c1-153">"\end{align}"</span></span>
- <span data-ttu-id="251c1-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="251c1-154">"\Lambda"</span></span>
- <span data-ttu-id="251c1-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="251c1-155">"\lambda"</span></span>
- <span data-ttu-id="251c1-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="251c1-156">"\Omega"</span></span>
- <span data-ttu-id="251c1-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="251c1-157">"\mathrm"</span></span>
- <span data-ttu-id="251c1-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="251c1-158">"\left"</span></span>
- <span data-ttu-id="251c1-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="251c1-159">"\right"</span></span>
- <span data-ttu-id="251c1-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="251c1-160">"\qquad"</span></span>
- <span data-ttu-id="251c1-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="251c1-161">"\times"</span></span>
- <span data-ttu-id="251c1-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="251c1-162">"\big"</span></span>
- <span data-ttu-id="251c1-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="251c1-163">"\langle"</span></span>
- <span data-ttu-id="251c1-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="251c1-164">"\rangle"</span></span>
- <span data-ttu-id="251c1-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="251c1-165">"\bigg"</span></span>
- <span data-ttu-id="251c1-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="251c1-166">"\Big"</span></span>
- <span data-ttu-id="251c1-167">"|"</span><span class="sxs-lookup"><span data-stu-id="251c1-167">"|"</span></span>
- <span data-ttu-id="251c1-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="251c1-168">"\mathbb"</span></span>
- <span data-ttu-id="251c1-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="251c1-169">"\vec"</span></span>
- <span data-ttu-id="251c1-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="251c1-170">"\in"</span></span>
- <span data-ttu-id="251c1-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="251c1-171">"\texttt"</span></span>
- <span data-ttu-id="251c1-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="251c1-172">"\ne"</span></span>
- <span data-ttu-id="251c1-173">"<"</span><span class="sxs-lookup"><span data-stu-id="251c1-173">"<"</span></span>
- <span data-ttu-id="251c1-174">">"</span><span class="sxs-lookup"><span data-stu-id="251c1-174">">"</span></span>
- <span data-ttu-id="251c1-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="251c1-175">"\leq"</span></span>
- <span data-ttu-id="251c1-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="251c1-176">"\geq"</span></span>
- <span data-ttu-id="251c1-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="251c1-177">"~~"</span></span>
- <span data-ttu-id="251c1-178">"~"</span><span class="sxs-lookup"><span data-stu-id="251c1-178">"~"</span></span>
- <span data-ttu-id="251c1-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="251c1-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="251c1-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="251c1-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="251c1-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="251c1-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="251c1-182">Vektory a matice</span><span class="sxs-lookup"><span data-stu-id="251c1-182">Vectors and Matrices</span></span>

<span data-ttu-id="251c1-183">Pro pochopení výpočetního prostředí je nezbytné, aby byly v některých zkušenostech vektory a matrice.</span><span class="sxs-lookup"><span data-stu-id="251c1-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="251c1-184">Poskytujeme stručný úvod do výše uvedeného článku a zúčastněné čtenáře se doporučuje přečíst standardní odkaz na lineární algebraický, jako je *Strang, G. (1993). Seznámení s lineárním algebraický (obj. 3). Wellesley, MA: Wellesley-Cambridge Press* nebo online odkaz, jako je [lineární algebraický](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="251c1-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="251c1-185">Vektor sloupce (nebo jednoduše [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ rozměru (nebo velikosti) $ n $ je kolekce $ n $ komplexních čísel $ (v_1, v_2, \ldots, v_n) $ uspořádaných jako sloupec:</span><span class="sxs-lookup"><span data-stu-id="251c1-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="251c1-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="251c1-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-187">v_1\\\\</span></span>
<span data-ttu-id="251c1-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-188">v_2\\\\</span></span>
<span data-ttu-id="251c1-189">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-189">\vdots\\\\</span></span>
<span data-ttu-id="251c1-190">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="251c1-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="251c1-191">Norma vektoru $ v $ je definována jako $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="251c1-192">Vektor je označován jako Jednotková norma (nebo případně se nazývá [*vektor jednotky*](https://en.wikipedia.org/wiki/Unit_vector)), pokud je jeho norma $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="251c1-193">[*Sousední objekt vektoru*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ je označený $ v ^ \dagger $ a je definován jako následující vektor řádku $ \* $ , kde označuje komplexně sdružené,</span><span class="sxs-lookup"><span data-stu-id="251c1-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="251c1-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="251c1-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="251c1-195">Nejběžnější způsob, jak vynásobit dva vektory dohromady, je [*vnitřní produkt*](https://en.wikipedia.org/wiki/Inner_product_space), označovaný také jako produkt s tečkou.</span><span class="sxs-lookup"><span data-stu-id="251c1-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="251c1-196">Vnitřní produkt poskytuje projekci jednoho vektoru na jiný a je nevýznamný v popisu, jak vyjádřit jeden vektor jako součet dalších jednodušších vektorů.</span><span class="sxs-lookup"><span data-stu-id="251c1-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="251c1-197">Vnitřní produkt v rozsahu $ u $ a $ v $ , označený $ \left \langle u, v \right \rangle $ je definován jako</span><span class="sxs-lookup"><span data-stu-id="251c1-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="251c1-198">\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="251c1-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="251c1-199">Tento zápis také umožňuje zapsat normu vektoru $ v $ do $ \sqrt { \langle v, v \rangle } $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="251c1-200">Je možné vynásobit vektor číslem $ c $ pro vytvoření nového vektoru, jehož záznamy jsou vynásobeny $ c $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="251c1-201">Můžeme také přidat dva vektory $ u $ a $ v $ k vytvoření nového vektoru, jehož položky jsou součtem položek $ u $ a $ v $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="251c1-202">Následující operace jsou znázorněny níže:</span><span class="sxs-lookup"><span data-stu-id="251c1-202">These operations are depicted below:</span></span>

<span data-ttu-id="251c1-203">$$\mathrm{Pokud } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="251c1-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-204">u_1\\\\</span></span>
<span data-ttu-id="251c1-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-205">u_2\\\\</span></span>
<span data-ttu-id="251c1-206">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-206">\vdots\\\\</span></span>
<span data-ttu-id="251c1-207">u_n \end{bmatrix} ~ \mathrm { a}~</span><span class="sxs-lookup"><span data-stu-id="251c1-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="251c1-208">ICES =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="251c1-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-209">v_1\\\\</span></span>
    <span data-ttu-id="251c1-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-210">v_2\\\\</span></span>
    <span data-ttu-id="251c1-211">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-211">\vdots\\\\</span></span>
    <span data-ttu-id="251c1-212">v_n \end{bmatrix} a ~ \mathrm { potom}~</span><span class="sxs-lookup"><span data-stu-id="251c1-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="251c1-213">Au a BV =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="251c1-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="251c1-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="251c1-216">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-216">\vdots\\\\</span></span>
<span data-ttu-id="251c1-217">au_n + bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="251c1-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="251c1-218">[*Matice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) o velikosti $ m \times n $ je kolekcí $ $ komplexních čísel MN uspořádaných v $ m $ řádcích a $ n $ sloupcích, jak je znázorněno níže:</span><span class="sxs-lookup"><span data-stu-id="251c1-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="251c1-219">$$4m =</span><span class="sxs-lookup"><span data-stu-id="251c1-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="251c1-220">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="251c1-221">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2N}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="251c1-222">M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { MN}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="251c1-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="251c1-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="251c1-224">Všimněte si, že vektor dimenze $ n $ je jenom matice o velikosti $ n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="251c1-225">Stejně jako u vektorů můžeme vynásobit matici číslem $ c $ , abyste získali novou matrici, kde je každá položka vynásobena řetězcem $ c $ , a můžeme přidat dvě matice stejné velikosti, aby se vytvořila nová matice, jejíž položky jsou součtem odpovídajících položek dvou matric.</span><span class="sxs-lookup"><span data-stu-id="251c1-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="251c1-226">Násobení a tensor součinů matic</span><span class="sxs-lookup"><span data-stu-id="251c1-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="251c1-227">Můžeme také vynásobit dvě matrice $ m $ dimenzí $ m \times n $ a $ n $ z dimenze $ n \times p, $ abyste získali novou matrici $ p $ dimenze $ m \times p $ následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="251c1-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="251c1-228">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="251c1-229">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2N}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="251c1-230">M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { MN}</span><span class="sxs-lookup"><span data-stu-id="251c1-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="251c1-231">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ {}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="251c1-232">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="251c1-233">N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { NP}</span><span class="sxs-lookup"><span data-stu-id="251c1-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="251c1-234">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ {}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="251c1-235">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="251c1-236">P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}</span><span class="sxs-lookup"><span data-stu-id="251c1-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="251c1-237">kde položky $ P $ jsou $ P_ { IK } = \sum _j M_ { IJ } N_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="251c1-238">Například položka $ P_ { 11 } $ je vnitřní součin prvního řádku v $ M $ s prvním sloupcem $ N $ . Vzhledem k tomu, že vektor je jednoduše speciálním případem matice, tato definice rozšiřuje na násobení vektoru matice.</span><span class="sxs-lookup"><span data-stu-id="251c1-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="251c1-239">Všechny matrice, které považujeme, budou buď čtvercové matice, kde počet řádků a sloupců je stejný, nebo vektory, které odpovídají pouze $ 1 $ sloupci.</span><span class="sxs-lookup"><span data-stu-id="251c1-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="251c1-240">Jednou speciální maticí je [*matice identity*](https://en.wikipedia.org/wiki/Identity_matrix)s označením $ \boldone $ , která má všechny jeho diagonální prvky rovny $ 1 $ a zbývající prvky rovnající se $ 0 $ :</span><span class="sxs-lookup"><span data-stu-id="251c1-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="251c1-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="251c1-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="251c1-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="251c1-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="251c1-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="251c1-245">V případě čtvercové matice $ a $ říkáme, že matice $ B $ je její [*invertovaná*](https://en.wikipedia.org/wiki/Invertible_matrix) , pokud je to $ AB = ba = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="251c1-246">Invertování matrice nemusí existovat, ale pokud existuje, je jedinečné a poznamenejte si ho $ ^ { -1 } $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="251c1-247">Pro libovolnou matrici $ m $ je sousední nebo sdružená transpozice $ M $ matice $ N $ , což $ N_ { IJ } = M_ { ji } ^ \* $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="251c1-248">Sousední $ $ jednotka M je obvykle označena jako $ M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="251c1-249">V $ $ případě hodnoty uu ^ [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ \dagger = u ^ \dagger u = \boldone $ nebo ekvivalentu $ u ^ { -1 } = U ^ \dagger $ říkáme, že matice u je jednotná.</span><span class="sxs-lookup"><span data-stu-id="251c1-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="251c1-250">Například nejdůležitější vlastnost maticových matric je, že zachovávají normu vektoru.</span><span class="sxs-lookup"><span data-stu-id="251c1-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="251c1-251">K tomu dochází, protože</span><span class="sxs-lookup"><span data-stu-id="251c1-251">This happens because</span></span> 

<span data-ttu-id="251c1-252">$$\langlev, v \rangle = v ^ \dagger v = v ^ \dagger u ^ u ^ { -1 } u v = ^ \dagger u ^ \dagger u v v = \langle , \rangle u$$</span><span class="sxs-lookup"><span data-stu-id="251c1-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="251c1-253">Matice $ m $ se označuje jako [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , pokud je to $ m = m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="251c1-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="251c1-254">Nakonec [*produkt tensor*](https://en.wikipedia.org/wiki/Tensor_product) (nebo Kronecker produkt) o dvou matricích $ m $ o velikosti $ m \times n $ a $ n $ velikosti $ p \times q $ je větší matice $ p = M \otimes n $ s velikostí $ MP \times NQ $ a získá se z $ M $ a $ n $ následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="251c1-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="251c1-255">M \otimes N &=</span><span class="sxs-lookup"><span data-stu-id="251c1-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="251c1-256">M_ { 11 } ~~ \cdots ~~ M_ { 1N }\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="251c1-257">M_ { M1 } ~~ \cdots ~~ M_ { MN  }</span><span class="sxs-lookup"><span data-stu-id="251c1-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="251c1-258">N_ { 11 } ~~ \cdots ~~ N_ { 1Q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="251c1-259">N_ { P1 } ~~ \cdots ~~ N_ { pq}</span><span class="sxs-lookup"><span data-stu-id="251c1-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="251c1-260">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="251c1-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="251c1-261">M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="251c1-262">M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="251c1-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="251c1-263">M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="251c1-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="251c1-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="251c1-265">To je vhodnější v některých příkladech:</span><span class="sxs-lookup"><span data-stu-id="251c1-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="251c1-266">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="251c1-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="251c1-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="251c1-268">\\\\[1,5 EM] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="251c1-269">=\begin{bmatrix}c a \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="251c1-270">a</span><span class="sxs-lookup"><span data-stu-id="251c1-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="251c1-271">a \ b \\\\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="251c1-272">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="251c1-273">určitého\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="251c1-274">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="251c1-275">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="251c1-276">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="251c1-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="251c1-278">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="251c1-279">trojrozměrné\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="251c1-280">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="251c1-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="251c1-281">AE \ AF \ je \ Bf \\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="251c1-282">AG \ Ah \ BG \ BH \\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="251c1-283">CE \ CF \ de \ DF \\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="251c1-284">\ ch \ DG \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="251c1-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="251c1-285">Konečná užitečná konvence zápisu okolních produktů tensor je to, že pro všechny vektory $ v $ nebo matrici $ M $ , $ v ^ { \otimes n } $ nebo $ m ^ { \otimes n } $ je krátká ruka pro $ n $ -přeložení opakovaného tensor produktu.</span><span class="sxs-lookup"><span data-stu-id="251c1-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="251c1-286">Příklad:</span><span class="sxs-lookup"><span data-stu-id="251c1-286">For example:</span></span>

\begin{align}
<span data-ttu-id="251c1-287">&\begin{bmatrix}1 \\\\ 0 1 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\</span><span class="sxs-lookup"><span data-stu-id="251c1-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="251c1-288">&\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ & \end{bmatrix} , 0, \qquad \begin{bmatrix} 0 & 1 \\\\ & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 0 & & 0 & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 0 0 0 0 0.1 0 0</span><span class="sxs-lookup"><span data-stu-id="251c1-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
