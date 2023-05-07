Download Link: https://assignmentchef.com/product/solved-math-281-workbook-3
<br>



<h1>Contents</h1>

<h2>Project Outline                                                                                                                                                   2</h2>

<strong>Workbook Questions [45 marks in questions + 5 general presentation = 50 points total] 3 </strong>[15 marks]: Question 1: Linear Advection . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 4 [15 marks]: Question 2: Diffusion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 5 [15 marks]: Question 3: Dispersion . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 6

<h1>Project Outline</h1>

The term project is divided into three section, each with a corresponding Jupyter workbook. Each workbook will ask you to investigate various aspects of numerical methods or PDEs. You will then be expected to submit a PDF report for each workbook, answering the questions. You are also expected to submit your workbooks (.ipynb files) along with your reports. The code, if run by the instructors / TAs, should reproduce the figures included in your reports. <em>You will submit the documents to Gradescope as a group.</em>

<strong>Files for Workbook 3       </strong>Instructions for accessing the files will be posted on Blackboard.

<strong>Sample Solutions </strong>As with the first two workbooks, you will be provided with a Jupyter notebook that illustrates some of the code that you will need to use to complete this part of the project. However, once again the provided solutions will be less complete than the previous workbooks, and may require you to integrate components from the previous workbooks.

<strong>Notes about Grading        </strong>Your grade on the reports will depend on:

<ul>

 <li>The over-all organization of your work</li>

 <li>The completeness and clarity of your answers</li>

 <li>How well you substantiate your claims with results (i.e. soundness of, and reference to, numerical findings), and how you connect the results to the underlying mechanics.</li>

 <li>How well you present your numerical findings (i.e. quality of graphs [note: quantity is not the same as quality!])</li>

</ul>

<strong>Note about Figures        </strong>Take care with your graphs. Some things to consider are:

<ul>

 <li>labeling (what is plotted on the axes? What are their units [if any]?)</li>

 <li>legibility (labels, axis numbers, etc should be large enough to be easily read when included in the report</li>

 <li>captions are a useful way to give a (brief) explanation of what is shown in a figure.</li>

</ul>

<h1>Workbook Questions [45 marks in questions + 5 general presentation = 50 points total]</h1>

In the third and final component of the term project, you will investigate the dynamical behaviour of three physical mechanisms represented by PDEs. You will apply the tools from the previous workbooks in order to <em>numerically solve </em>the PDEs, and then analyze the behaviour of the system in both <em>physical- </em>and <em>spectral-space</em>. The idea is to qualitatively understand the dynamical impact of each mechanism / mathematical term. Understanding how each component of a PDE impacts the governing dynamics is critical to gaining insight into the over-all behaviour of the system reflected by the PDE.

Assume periodic boundary conditions for each question in the workbook. The initial conditions and domain for each question are given by

<em>u </em>= <em>u</em>(<em>x,t</em>) <em>u</em>(<em>x,</em>0) = sin(4<em>πx/L<sub>x</sub></em>) + 0<em>.</em>25sin(8<em>πx/L<sub>x</sub></em>) <em>x </em>∈ [−<em>L<sub>x</sub>/</em>2<em>,L<sub>x</sub>/</em>2] <em>t </em>∈ [0<em>,</em>50]

<em>L<sub>x </sub></em>= 10

<strong>Note about Simulations </strong>keep in mind that for at least the first two problems, you know qualitatively what kind of solution to expect. And so you are expected to recognize if your solution explodes or gives results wildly outside of the expected behaviour. Analysing simulation results is only meaningful if the simulation results themselves are sound.

<strong>Note about PDES </strong>notice that between the three cases, we are only changing the order of the spatial derivative. The physical mechanisms described by the three PDEs are often called, in order, <em>advection</em>, <em>diffusion</em>, and <em>dispersion</em>.

<strong>Note about Grading </strong>in addition to 45 marks spread across the three questions, there are five additional marks for over-all presentation.

<h2>[15 marks]: Question 1: Linear Advection</h2>

<em>∂<sub>t</sub>u </em>+ <em>U</em><sub>0</sub><em>∂<sub>x</sub>u </em>= 0;                                                 <em>U</em><sub>0 </sub>= 0<em>.</em>1

<ul>

 <li>Substitute the ansatz <em>u </em>= exp(<em>i</em>(<em>kx </em>− <em>ωt</em>)) into the PDE and solve for <em>ω </em>as a function of <em>k</em><a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>.</li>

</ul>

Substitute back into the ansatz and write it as a product of a term that oscillates in time and a term that decays/grows in time. Note that one or neither of these terms may simply be the constant 1 (one).

Using your understanding of representing functions as Fourier sums, how / what does this analysis reveal about the behaviour of the system? What temporal behaviour does it describe? Does it depend on wavenumber <em>k</em>?

<ul>

 <li>Using a second order finite difference scheme, compute a numerical solution to the PDE. Explain and justify your choice of

  <ul>

   <li>number of spatial gridpoints (Nx), and (ii) size of timestep (∆<em>t</em>).</li>

  </ul></li>

</ul>

Your choices should be such that the spatial features are cleanly resolved, and the time-step is sufficiently small to provide stability<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a>. <em>Do not </em>assume that the values given in the sample workbook are sufficient.

Create appropriate plots to show the evolution of the system. Qualitatively describe how the system evolves. How do these results compare with your Fourier analysis from part (a)?

<ul>

 <li>Compute (and plot) the root-mean-squared<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a> (RMS) error as a function of time. What does this tell you about the validity of your simulation? For reference / comparison, compute the RMS of the initial conditions.</li>

 <li>Compute and describe (and plot) the time evolution of the spectral power. How do these results compare to what you expect given your knowledge of the PDE? If there are any differences, can you explain / justify them using what you know about numerical methods?</li>

 <li>(i) Using the PDE, obtain an ODE for <em>E</em>(<em>t</em>) := <sup>R</sup><em><sub>x </sub>u</em><sup>2</sup>(<em>x,t</em>)<em>dx</em>, the domain integral of <em>u</em><sup>2</sup>. Is this result</li>

</ul>

consistent with your Fourier analysis in part (a)?

<ul>

 <li>Compute (and plot) the spatial integral of <em>E</em>(<em>t</em>) from your numerical solutions. Is this consistent with your predictions? Why or why not?</li>

</ul>

<h2>[15 marks]: Question 2: Diffusion</h2>

<em>∂<sub>t</sub>u </em>= <em>ν∂<sub>xx</sub>u</em>;                                                    <em>ν </em>= 0<em>.</em>1

<ul>

 <li>The CFL restriction that we use in advective problems doesn’t apply to diffusive processes, since information isn’t propagating in the same sense.</li>

</ul>

Consider again the linear advection equation, but this time with the derivatives replaced by finite differences:

<em>.</em>

Simple re-arranging then gives

<em>,</em>

which was the upper bound of our CFL restriction.<a href="#_ftn4" name="_ftnref4"><sup>[4]</sup></a>

Using a similar method, what result do you find for the diffusion equation?

<ul>

 <li>Remembering that we are assuming a periodic grid and uniform spacing, derive the centred, secondorder finite difference scheme for second derivatives. Recall that you can use the error-curve plots from the previous two workbooks to verify the order of your scheme. Include the error curve (error vs. ∆<em>x</em>) as evidence of the validity of your scheme.</li>

</ul>

To do this, you will need to write the Taylor expansions for <em>u<sub>i</sub></em><sub>−1</sub><em>,u<sub>i</sub>,u<sub>i</sub></em><sub>+1 </sub>out to the fourth-order term.

An appropriate code-snippet to compute this derivative would then be:

d2udx2 = ( np.roll(u, 1) – 2 * u + np.roll(u, -1) ) / ( delta x**2 )

<ul>

 <li>Repeat part (a) from question 1.</li>

 <li>Repeat part (b) from question 1.</li>

</ul>

Note that these simulations may take several minutes depending on your choices of ∆<em>x </em>and ∆<em>t</em>. You may find it beneficial to save your simulation results after computing them to avoid unnecessary recomputing.

<ul>

 <li>Repeat part (e) from question 1.</li>

</ul>

<h2>[15 marks]: Question 3: Dispersion</h2>

<em>∂<sub>t</sub>u </em>= <em>α∂<sub>xxx</sub>u</em>;                                                    <em>α </em>= 0<em>.</em>1

Repeat parts (a) – (e) from question 2.

For part (b), you will need to write the Taylor expansions for <em>u<sub>i</sub></em><sub>−2</sub><em>,u<sub>i</sub></em><sub>−1</sub><em>,u<sub>i</sub>,u<sub>i</sub></em><sub>+1</sub><em>,u<sub>i</sub></em><sub>+2 </sub>out to the fifth-order term. An appropriate code-snippet to compute this derivative would then be:

d3udx3 = (

<ul>

 <li>5 * np.roll(u, 2) + np.roll(u, 1)</li>

 <li>roll(u, -1) + 0.5 * np.roll(u, -2)</li>

</ul>

) / ( delta x**3 )

When analyzing your numerical simulations, you may find it beneficial to run additional simulations that include the sin terms from the initial conditions separately.

<a href="#_ftnref1" name="_ftn1">[1]</a> this equation is known as the dispersion relation

<a href="#_ftnref2" name="_ftn2">[2]</a> A good way to test your choice of ∆<em>t </em>is to run a second simulation with 0<em>.</em>5∆<em>t </em>(but the same Nx). If the results are nearly identical [and no obviously bad things are happening], then you can have some faith in your results.

r

<a href="#_ftnref3" name="_ftn3">[3]</a> 3RMS =              meanh(<em>u</em>true − <em>u</em>numerical)2i

<a href="#_ftnref4" name="_ftn4">[4]</a> Recall that we needed to use a substantially smaller time step for the purpose of stability, but this gives us a reference point to work from, and tells us how to scale the time-step when the grid changes.