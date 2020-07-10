---
title: vektory a matice v popisu pro výpočetní výkon – Popis: Naučte se základy práce s vektory a maticemi.
Autor: QuantumWriter UID: Microsoft.. koncepty. Vectors MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. téma: No-Loc:
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

# <a name="vectors-and-matrices"></a>Vektory a matice

Pro pochopení výpočetního prostředí je nezbytné, aby byly v některých zkušenostech vektory a matrice. Poskytujeme stručný úvod do výše uvedeného článku a zúčastněné čtenáře se doporučuje přečíst standardní odkaz na lineární algebraický, jako je *Strang, G. (1993). Seznámení s lineárním algebraický (obj. 3). Wellesley, MA: Wellesley-Cambridge Press* nebo online odkaz, jako je [lineární algebraický](http://joshua.smcvt.edu/linearalgebra/).

Vektor sloupce (nebo jednoduše [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ rozměru (nebo velikosti) $ n $ je kolekce $ n $ komplexních čísel $ (v_1, v_2, \ldots, v_n) $ uspořádaných jako sloupec:

$$ICES=\begin{bmatrix}
v_1\\\\
v_2\\\\
\vdots\\\\
v_n\end{bmatrix}$$

Norma vektoru $ v $ je definována jako $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ . Vektor je označován jako Jednotková norma (nebo případně se nazývá [*vektor jednotky*](https://en.wikipedia.org/wiki/Unit_vector)), pokud je jeho norma $ 1 $ . [*Sousední objekt vektoru*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ je označený $ v ^ \dagger $ a je definován jako následující vektor řádku $ \* $ , kde označuje komplexně sdružené,

$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & v_n ^ *\end{bmatrix}$$

Nejběžnější způsob, jak vynásobit dva vektory dohromady, je [*vnitřní produkt*](https://en.wikipedia.org/wiki/Inner_product_space), označovaný také jako produkt s tečkou.  Vnitřní produkt poskytuje projekci jednoho vektoru na jiný a je nevýznamný v popisu, jak vyjádřit jeden vektor jako součet dalších jednodušších vektorů.  Vnitřní produkt v rozsahu $ u $ a $ v $ , označený $ \left \langle u, v \right \rangle $ je definován jako

$$
\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Tento zápis také umožňuje zapsat normu vektoru $ v $ do $ \sqrt { \langle v, v \rangle } $ .

Je možné vynásobit vektor číslem $ c $ pro vytvoření nového vektoru, jehož záznamy jsou vynásobeny $ c $ . Můžeme také přidat dva vektory $ u $ a $ v $ k vytvoření nového vektoru, jehož položky jsou součtem položek $ u $ a $ v $ . Následující operace jsou znázorněny níže:

$$\mathrm{Pokud } ~ u=\begin{bmatrix}
u_1\\\\
u_2\\\\
\vdots\\\\
u_n \end{bmatrix} ~ \mathrm { a}~
ICES=\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \vdots\\\\
    v_n \end{bmatrix} a ~ \mathrm { potom}~
Au a BV=\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\vdots\\\\
au_n + bv_n \end{bmatrix} .
$$

[*Matice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) o velikosti $ m \times n $ je kolekcí $ $ komplexních čísel MN uspořádaných v $ m $ řádcích a $ n $ sloupcích, jak je znázorněno níže:

$$4m= 
\begin{bmatrix}
M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\
M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2N}\\\\
\ddots\\\\
M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { MN}\\\\
\end{bmatrix}.$$

Všimněte si, že vektor dimenze $ n $ je jenom matice o velikosti $ n \times 1 $ . Stejně jako u vektorů můžeme vynásobit matici číslem $ c $ , abyste získali novou matrici, kde je každá položka vynásobena řetězcem $ c $ , a můžeme přidat dvě matice stejné velikosti, aby se vytvořila nová matice, jejíž položky jsou součtem odpovídajících položek dvou matric. 

## <a name="matrix-multiplication-and-tensor-products"></a>Násobení a tensor součinů matic

Můžeme také vynásobit dvě matrice $ m $ dimenzí $ m \times n $ a $ n $ z dimenze $ n \times p, $ abyste získali novou matrici $ p $ dimenze $ m \times p $ následujícím způsobem:

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1N}\\\\
    M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2N}\\\\
    \ddots\\\\
    M_ { M1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { MN}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ {}\\\\
N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\
\ddots\\\\
N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { NP}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ {}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\
\ddots\\\\
P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}
\end{bmatrix}
\end{align}

kde položky $ P $ jsou $ P_ { IK } = \sum _j M_ { IJ } N_ { JK } $ . Například položka $ P_ { 11 } $ je vnitřní součin prvního řádku v $ M $ s prvním sloupcem $ N $ . Vzhledem k tomu, že vektor je jednoduše speciálním případem matice, tato definice rozšiřuje na násobení vektoru matice. 

Všechny matrice, které považujeme, budou buď čtvercové matice, kde počet řádků a sloupců je stejný, nebo vektory, které odpovídají pouze $ 1 $ sloupci. Jednou speciální maticí je [*matice identity*](https://en.wikipedia.org/wiki/Identity_matrix)s označením $ \boldone $ , která má všechny jeho diagonální prvky rovny $ 1 $ a zbývající prvky rovnající se $ 0 $ :

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$

V případě čtvercové matice $ a $ říkáme, že matice $ B $ je její [*invertovaná*](https://en.wikipedia.org/wiki/Invertible_matrix) , pokud je to $ AB = ba = \boldone $ . Invertování matrice nemusí existovat, ale pokud existuje, je jedinečné a poznamenejte si ho $ ^ { -1 } $ . 

Pro libovolnou matrici $ m $ je sousední nebo sdružená transpozice $ M $ matice $ N $ , což $ N_ { IJ } = M_ { ji } ^ \* $ . Sousední $ $ jednotka M je obvykle označena jako $ M ^ \dagger $ . V $ $ případě hodnoty uu ^ [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ \dagger = u ^ \dagger u = \boldone $ nebo ekvivalentu $ u ^ { -1 } = U ^ \dagger $ říkáme, že matice u je jednotná.  Například nejdůležitější vlastnost maticových matric je, že zachovávají normu vektoru.  K tomu dochází, protože 

$$\langlev, v \rangle = v ^ \dagger v = v ^ \dagger u ^ u ^ { -1 } u v = ^ \dagger u ^ \dagger u v v = \langle , \rangle u$$  

Matice $ m $ se označuje jako [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , pokud je to $ m = m ^ \dagger $ .

Nakonec [*produkt tensor*](https://en.wikipedia.org/wiki/Tensor_product) (nebo Kronecker produkt) o dvou matricích $ m $ o velikosti $ m \times n $ a $ n $ velikosti $ p \times q $ je větší matice $ p = M \otimes n $ s velikostí $ MP \times NQ $ a získá se z $ M $ a $ n $ následujícím způsobem:

\begin{align}
    M \otimes N&=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ M_ { 1N }\\\\
        \ddots\\\\
        M_ { M1 } ~~ \cdots ~~ M_ { MN  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1Q  }\\\\
        \ddots\\\\
        N_ { P1 } ~~ \cdots ~~ N_ { pq}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

To je vhodnější v některých příkladech:

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        a \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1,5 EM] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}c a \\\\ d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}
$$

a

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d\end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h\end{bmatrix}
     =
    \begin{bmatrix}
    určitého\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    b\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    trojrozměrné\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    AE \ AF \ je \ Bf\\\\
    AG \ Ah \ BG \ BH\\\\
    CE \ CF \ de \ DF\\\\
    \ ch \ DG \ DH \end{bmatrix} .
$$

Konečná užitečná konvence zápisu okolních produktů tensor je to, že pro všechny vektory $ v $ nebo matrici $ M $ , $ v ^ { \otimes n } $ nebo $ m ^ { \otimes n } $ je krátká ruka pro $ n $ -přeložení opakovaného tensor produktu.  Zde je příklad:

\begin{align}
&\begin{bmatrix}1 \\\\ 0 1 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ & \end{bmatrix} , 0, \qquad \begin{bmatrix} 0 & 1 \\\\ & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 0 & & 0 & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 0 0 0 0 0.1 0 0
\end{align}
