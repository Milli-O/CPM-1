##Two Cell Adhesion
I simulate two CPM cells of the same type to demonstrate how adhesion energies affect cell shape and the cell-cell adhesion where $J_{cc}$ is the cell-cell adhesion and $J_{cm}$ is the cell-medium adhesion.

Case One :  When cell-cell adhesion is lower than the cell-medium adhesion, cells make as large a region of contact as possible while also attempting to satisfy their own volume constraints. 


$\href{https://github.com/Milli-O/CPM-1/blob/main/TwoCell_case1.avi}{https://github.com/Milli-O/CPM-1/blob/main/TwoCell_case1.avi}$

begin{align}\label{TC-c1}
    J = \begin{pmatrix}
        0 & 10 \\
        10 & 5
    \end{pmatrix}
\end{align}

Case Two:  When cell-cell adhesion is higher than the cell-medium adhesion, cells separate.

$\href{https://github.com/Milli-O/CPM-1/blob/main/TwoCell-case2.mp4}{https://github.com/Milli-O/CPM-1/blob/main/TwoCell-case2.mp4}$

\begin{align}\label{TC-c2}
    J = \begin{pmatrix}
        0 & 5 \\
        5 & 10
    \end{pmatrix}
\end{align}


##Same Cell Adhesion
This implementation is four cells of the same type and id. In previous simulations of same cells of the same type and ids, cells merged as one blob. This was to check after the implementing the cells boundaries, if the cells would still merge or rather stay close minimizing the over all energy.

This simulation was implemented using the J matrix in equation \eqref{TC-c1}.

$\href{https://github.com/Milli-O/CPM-1/blob/main/Samecells.mp4}{https://github.com/Milli-O/CPM-1/blob/main/Samecells.mp4}$


This simulation was implemented using the J matrix in equation \eqref{TC-c2}.

$\href{https://github.com/Milli-O/CPM-1/blob/main/Samecells-1.mp4}{https://github.com/Milli-O/CPM-1/blob/main/Samecells-1.mp4}$



##Cell Sorting
Moving on, I include an additional cell type called morula (now the two cell types; zygote and morula). The focus in this part of the work is to implement the idea is cell sorting as first done by Glazier and Graner and implemented in morpheus as $\href{https://morpheus.gitlab.io/model/m2007/}{https://morpheus.gitlab.io/model/m2007/}$. 

Two cell types are defined, each of which has a volume constraint specifying the cell's area (volume). The simulation shows two populations of spatially resolved cells that initially have organised checkerboard design. Through differential adhesion, the motile cells sort out and reorganize into a distribution in which the zygote cells is surrounded by the morula cells..

The adhesion matrix used is obtained from the description given for separation (b) in  $\href{https://morpheus.gitlab.io/model/m2007/}{https://morpheus.gitlab.io/model/m2007/}$ 

\begin{align}
    J &= \begin{pmatrix}
        J_{mm} & J_{m1} & J_{m2}\\
        J_{1m} & J_{11} & J_{12}\\
        J_{2m} & J_{21} & J_{22}
    \end{pmatrix}\\
    &=\begin{pmatrix}
        0 & 12 & 6\\
        12 & 6 & 16\\
        6 & 16 & 6
    \end{pmatrix}
\end{align}

where 
    $J_{mm}$ is medium-medium adhesion

    $J_{m1}$ is medium-zygote adhesion

    $J_{m2}$ is medium-morula adhesion

    $J_{11}$ is zygote-zygote adhesion

    $J_{12}$ is zygote-morula adhesion

    $J_{22}$ is morula-morula adhesion
 

In the simulation below, 40 cells (20 of morula and 20 of zygote cells) are placed in a checkerboard pattern within the lattice. Each cell has a volume of 25 and the target volumes are also set to be equal to the initial volume. Zygote cells are represented in the lattice as red and morula cells are represented as blue.

$\href{https://github.com/Milli-O/CPM-1/blob/main/CellSorting-separation.mp4}{https://github.com/Milli-O/CPM-1/blob/main/CellSorting-separation.mp4}$


I increased the size of the cells from 25pixels each to 100pixels each. Still maintaining initial volume to be equal to the target volume.

$\href{https://github.com/Milli-O/CPM-1/blob/main/CellSorting-1.mp4}{https://github.com/Milli-O/CPM-1/blob/main/CellSorting-1.mp4}$

