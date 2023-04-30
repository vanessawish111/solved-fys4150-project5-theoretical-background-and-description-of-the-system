Download Link: https://assignmentchef.com/product/solved-fys4150-project5-theoretical-background-and-description-of-the-system
<br>
<h2>Theoretical background and description of the system</h2>

The goal of this project is to develop a Monte Carlo simulation of the spread of an infectious disease. We will use the classical SIRS model of to develop the necessary transition probabilities for the simulation. Interpreting the simulation requires a thorough understanding of the SIRS model, so a deterministic approach is used in conjunction with Monte Carlo methods.

The main purpose of creating such a simulation is to investigate how a disease spreads throughout a given population over time. Then we can make predictions about whether or not a certain disease has the capacity to establish itself within the population, i.e. a fraction of the population remains infected after the system reaches equilibrium.

The <a href="https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology">SIRS model</a> considers an isolated population of <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>N</mi></math>">N</span></em>N people which are divided into three separate groups:

<ul>

 <li>Susceptible (S): those without immunity to the disease,</li>

 <li>Infected (I): those who are currently infected with the disease,</li>

 <li>Recovered (R): those who have been infected in the past and have developed an immunity to the disease.</li>

</ul>

A person can move from one group to another only in the cyclic order suggested by the name of the model <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>S</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>I</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>R</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>S</mi></math>">S</span></em>→<em>I</em>→<em>R</em>→<em>S</em>S→I→R→S. The rate of transmission <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>a</mi></math>">a</span></em>a, the rate of recovery <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi></math>">b</span></em>b and the rate of immunity loss <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>c</mi></math>">c</span></em>c help describe the flow of people moving between the three groups. The population is assumed to mix homogeneously and total population is assumed to remain constant so that

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto1&quot;><mtext>(1)</mtext></mtd><mtd><mi>N</mi><mo>=</mo><mi>S</mi><mo stretchy=&quot;false&quot;>(</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>+</mo><mi>I</mi><mo stretchy=&quot;false&quot;>(</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>+</mo><mi>R</mi><mo stretchy=&quot;false&quot;>(</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>.</mo></mtd></mlabeledtr></mtable></math>">N</span></em>=<em>S</em>(<em>t</em>)+<em>I</em>(<em>t</em>)+<em>R</em>(<em>t</em>).(1)(1)N=S(t)+I(t)+R(t).

For the simple case, we will assume that the dynamics of the epidemic occur during a time scale much smaller than the average person’s lifetime. Hence the effect of the birth and death rate of the population is ignored.

From these assumptions, a set of coupled differential equations can be constructed to form the classical SIRS model:

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto2&quot;><mtext>(2)</mtext></mtd><mtd><mtable columnalign=&quot;right left&quot; rowspacing=&quot;3pt&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;true&quot;><mtr><mtd><msup><mi>S</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mi>c</mi><mi>R</mi><mo>&amp;#x2212;</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac></mtd></mtr><mtr><mtd><msup><mi>I</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mo>&amp;#x2212;</mo><mi>b</mi><mi>I</mi></mtd></mtr><mtr><mtd><msup><mi>R</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mi>b</mi><mi>I</mi><mo>&amp;#x2212;</mo><mi>c</mi><mi>R</mi></mtd></mtr></mtable></mtd></mlabeledtr></mtable></math>">S</span></em>′<em>I</em>′<em>R</em>′=<em>cR</em>−<em>aSIN</em>=<em>aSIN</em>−<em>bI</em>=<em>bI</em>−<em>cR</em>(2)(2)S′=cR−aSINI′=aSIN−bIR′=bI−cR

Note that for small populations, one may choose to write <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>a</mi><mi>S</mi><mi>I</mi></math>">aSI</span></em>aSI instead of <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac></math>">aSIN</span></em>aSIN since the number of susceptibles which become infected depend more on the absolute number of infected people rather than the infected fraction of the population.

Though this set does not have analytic solutions like the closely-related SIR model, the equilibrium solutions are simple to obtain. The constraint in (1) reduces this three dimensional system into a two dimensional one so that the equation for <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><msup><mi>R</mi><mo>&amp;#x2032;</mo></msup></math>">R</span></em>′R′ can just be omitted:

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto3&quot;><mtext>(3)</mtext></mtd><mtd><mtable columnalign=&quot;right left&quot; rowspacing=&quot;3pt&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;true&quot;><mtr><mtd><msup><mi>S</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mi>c</mi><mo stretchy=&quot;false&quot;>(</mo><mi>N</mi><mo>&amp;#x2212;</mo><mi>S</mi><mo>&amp;#x2212;</mo><mi>I</mi><mo stretchy=&quot;false&quot;>)</mo><mo>&amp;#x2212;</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac></mtd></mtr><mtr><mtd><msup><mi>I</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mo>&amp;#x2212;</mo><mi>b</mi><mi>I</mi></mtd></mtr></mtable></mtd></mlabeledtr></mtable></math>">S</span></em>′<em>I</em>′=<em>c</em>(<em>N</em>−<em>S</em>−<em>I</em>)−<em>aSIN</em>=<em>aSIN</em>−<em>bI</em>(3)(3)S′=c(N−S−I)−aSINI′=aSIN−bI

The steady state is found by setting both equations in (3) equal to zero. Let <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>s</mi></math>">s</span></em>s, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>i</mi></math>">i</span></em>i, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>r</mi></math>">r</span></em>r denote the fractions of people in <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>S</mi></math>">S</span></em>S, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>I</mi></math>">I</span></em>I, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>R</mi></math>">R</span></em>R, respectively. Then the fractions of people in each group at equilibrium are:

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto4&quot;><mtext>(4)</mtext></mtd><mtd><mtable columnalign=&quot;right left&quot; rowspacing=&quot;3pt&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;true&quot;><mtr><mtd><msup><mi>s</mi><mo>&amp;#x2217;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mfrac><mi>b</mi><mi>a</mi></mfrac><mo>,</mo></mtd></mtr><mtr><mtd><msup><mi>i</mi><mo>&amp;#x2217;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mfrac><mrow><mn>1</mn><mo>&amp;#x2212;</mo><mfrac><mi>b</mi><mi>a</mi></mfrac></mrow><mrow><mn>1</mn><mo>+</mo><mfrac><mi>b</mi><mi>c</mi></mfrac></mrow></mfrac><mo>,</mo></mtd></mtr><mtr><mtd><msup><mi>r</mi><mo>&amp;#x2217;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mfrac><mi>b</mi><mi>c</mi></mfrac><mfrac><mrow><mn>1</mn><mo>&amp;#x2212;</mo><mfrac><mi>b</mi><mi>a</mi></mfrac></mrow><mrow><mn>1</mn><mo>+</mo><mfrac><mi>b</mi><mi>c</mi></mfrac></mrow></mfrac><mo>.</mo></mtd></mtr></mtable></mtd></mlabeledtr></mtable></math>">s</span></em>∗i∗r∗=<em>ba</em>,=1−<em>ba</em>1+<em>bc</em>,=<em>bc</em>1−<em>ba</em>1+<em>bc</em>.(4)(4)s∗=ba,i∗=1−ba1+bc,r∗=bc1−ba1+bc.

Here, the asterisk (<span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><msup><mi></mi><mo>&amp;#x2217;</mo></msup></math>">∗</span>∗) signifies that these fractions are at equilibrium. Notice that each fraction must be a number between 0 and 1, and that the three fractions must add up to 1. Thus the equations in (4) suggest that the rate of recovery <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi></math>">b</span></em>b must be less than the rate of transmission <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>a</mi></math>">a</span></em>a for the number of infected people at equilibrium to be greater than zero. In other words, the disease establishes itself in the population only if <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi><mo>&amp;lt;</mo><mi>a</mi></math>">b</span></em>&lt;<em>a</em>b&lt;a.

<strong>For this project you can collaborate with fellow students and you can hand in a common report.</strong> This project (together with projects 3 and 4) counts 1/3 of the final mark.

<h3>Part a) setting up the differential equations</h3>

We will create four different populations to investigate the effect of increasing the rate of recovery <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi></math>">b</span></em>b and crossing the “threshold”. Each population consists of 400 people, 100 of which were initially infected and 300 of which were initially susceptible. We fix the rate of transmission <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>a</mi></math>">a</span></em>a and the rate of immunity loss <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>c</mi></math>">c</span></em>c between populations, but let the rate of recovery <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi></math>">b</span></em>b be varied because it is the one parameter which can be reasonably controlled by the actions of human society (access to health care, development of new medicines, etc). Note that the rates have units of inverse time. The table here lists a possible set of parameters for the four different populations.

<table>

 <thead>

  <tr>

   <td><strong>Rate</strong></td>

   <td><strong>A</strong></td>

   <td><strong>B</strong></td>

   <td><strong>C</strong></td>

   <td><strong>D</strong></td>

  </tr>

 </thead>

 <tbody>

  <tr>

   <td>a</td>

   <td>4</td>

   <td>4</td>

   <td>4</td>

   <td>4</td>

  </tr>

  <tr>

   <td>b</td>

   <td>1</td>

   <td>2</td>

   <td>3</td>

   <td>4</td>

  </tr>

  <tr>

   <td>c</td>

   <td>0.5</td>

   <td>0.5</td>

   <td>0.5</td>

   <td>0.5</td>

  </tr>

 </tbody>

</table>

The rates of transmission are given by the parameter <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>a</mi></math>">a</span></em>a, recovery by <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi></math>">b</span></em>b, and immunity loss <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>c</mi></math>">c</span></em>c for populations <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>A</mi></math>">A</span></em>A, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>B</mi></math>">B</span></em>B, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>C</mi></math>">C</span></em>C, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>D</mi></math>">D</span></em>D.

We treat the population as a continuous variable. Develop a Runge-Kutta fourth order code to solve the above equations.

Discuss your results and present your interpreations.

<h3>Part b), moving to a Monte Carlo simulation</h3>

The set of differential equations in (2) inherently assume that <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>S</mi></math>">S</span></em>S, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>I</mi></math>">I</span></em>I, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>R</mi></math>">R</span></em>R are continuous variables, when they are discrete in reality. We can use the idea of randomness to remedy this issue by defining a set of transition probabilities for the possible moves a person can take from one state to another: <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>S</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>I</mi></math>">S</span></em>→<em>I</em>S→I, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>I</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>R</mi></math>">I</span></em>→<em>R</em>I→R, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>R</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>S</mi></math>">R</span></em>→<em>S</em>R→S. To obtain the specific values for each probability, we first notice from (2) that in a small time step <span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">Δ<em>t</em></span>Δt, the number of people moving from <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>S</mi></math>">S</span></em>S to <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>I</mi></math>">I</span></em>I is approximately <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">aSIN</span></em>Δ<em>t</em>aSINΔt. Likewise, about <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi><mi>I</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">bI</span></em>Δ<em>t</em>bIΔt move from <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>I</mi></math>">I</span></em>I to <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>R</mi></math>">R</span></em>R and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>c</mi><mi>R</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">cR</span></em>Δ<em>t</em>cRΔt move from <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>R</mi></math>">R</span></em>R to <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>S</mi></math>">S</span></em>S.

Now we let <span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">Δ<em>t</em></span>Δt be small enough so that <em>at most</em> one person moves from a given group to another. Since

<span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto5&quot;><mtext>(5)</mtext></mtd><mtd><mtable columnalign=&quot;right left&quot; rowspacing=&quot;3pt&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;true&quot;><mtr><mtd /><mtd><mi></mi><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>max</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo maxsize=&quot;1.623em&quot; minsize=&quot;1.623em&quot;>{</mo></mrow><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo maxsize=&quot;1.623em&quot; minsize=&quot;1.623em&quot;>}</mo></mrow><mo>=</mo><mfrac><mi>a</mi><mi>N</mi></mfrac><msup><mrow><mo>(</mo><mfrac><mi>N</mi><mn>2</mn></mfrac><mo>)</mo></mrow><mn>2</mn></msup><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo>=</mo><mfrac><mrow><mi>a</mi><mi>N</mi></mrow><mn>4</mn></mfrac><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo>,</mo></mtd></mtr><mtr><mtd /><mtd><mi></mi><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>max</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo maxsize=&quot;1.623em&quot; minsize=&quot;1.623em&quot;>{</mo></mrow><mi>b</mi><mi>I</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo maxsize=&quot;1.623em&quot; minsize=&quot;1.623em&quot;>}</mo></mrow><mo>=</mo><mi>b</mi><mi>N</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo>,</mo></mtd></mtr><mtr><mtd /><mtd><mi></mi><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>max</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo maxsize=&quot;1.623em&quot; minsize=&quot;1.623em&quot;>{</mo></mrow><mi>c</mi><mi>R</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo maxsize=&quot;1.623em&quot; minsize=&quot;1.623em&quot;>}</mo></mrow><mo>=</mo><mi>c</mi><mi>N</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo>,</mo></mtd></mtr></mtable></mtd></mlabeledtr></mtable></math>">max{<em>aSIN</em>Δ<em>t</em>}=<em>aN</em>(<em>N</em>2)2Δ<em>t</em>=<em>aN</em>4Δ<em>t</em>,</span>max{<em>bI</em>Δ<em>t</em>}=<em>bN</em>Δ<em>t</em>,max{<em>cR</em>Δ<em>t</em>}=<em>cN</em>Δ<em>t</em>,(5)(5)max{aSINΔt}=aN(N2)2Δt=aN4Δt,max{bIΔt}=bNΔt,max{cRΔt}=cNΔt,

the time step is then given by

<span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto6&quot;><mtext>(6)</mtext></mtd><mtd><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo>=</mo><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>min</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo maxsize=&quot;1.623em&quot; minsize=&quot;1.623em&quot;>{</mo></mrow><mfrac><mn>4</mn><mrow><mi>a</mi><mi>N</mi></mrow></mfrac><mo>,</mo><mfrac><mn>1</mn><mrow><mi>b</mi><mi>N</mi></mrow></mfrac><mo>,</mo><mfrac><mn>1</mn><mrow><mi>c</mi><mi>N</mi></mrow></mfrac><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo maxsize=&quot;1.623em&quot; minsize=&quot;1.623em&quot;>}</mo></mrow><mo>.</mo></mtd></mlabeledtr></mtable></math>">Δ<em>t</em>=min{4<em>aN</em>,1<em>bN</em>,1<em>cN</em>}</span>.(6)(6)Δt=min{4aN,1bN,1cN}.

This construction allows us to reinterpret the values <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">aSIN</span></em>Δ<em>t</em>aSINΔt, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi><mi>I</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">bI</span></em>Δ<em>t</em>bIΔt, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>c</mi><mi>R</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi></math>">cR</span></em>Δ<em>t</em>cRΔt as transition probabilties:

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto7&quot;><mtext>(7)</mtext></mtd><mtd><mtable columnalign=&quot;right left&quot; rowspacing=&quot;3pt&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;true&quot;><mtr><mtd><mi>P</mi><mo stretchy=&quot;false&quot;>(</mo><mi>S</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>I</mi><mo stretchy=&quot;false&quot;>)</mo></mtd><mtd><mi></mi><mo>=</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo>,</mo></mtd></mtr><mtr><mtd><mi>P</mi><mo stretchy=&quot;false&quot;>(</mo><mi>I</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>R</mi><mo stretchy=&quot;false&quot;>)</mo></mtd><mtd><mi></mi><mo>=</mo><mi>b</mi><mi>I</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo>,</mo></mtd></mtr><mtr><mtd><mi>P</mi><mo stretchy=&quot;false&quot;>(</mo><mi>R</mi><mo stretchy=&quot;false&quot;>&amp;#x2192;</mo><mi>S</mi><mo stretchy=&quot;false&quot;>)</mo></mtd><mtd><mi></mi><mo>=</mo><mi>c</mi><mi>R</mi><mi mathvariant=&quot;normal&quot;>&amp;#x0394;</mi><mi>t</mi><mo>.</mo></mtd></mtr></mtable></mtd></mlabeledtr></mtable></math>">P</span></em>(<em>S</em>→<em>I</em>)<em>P</em>(<em>I</em>→<em>R</em>)<em>P</em>(<em>R</em>→<em>S</em>)=<em>aSIN</em>Δ<em>t</em>,=<em>bI</em>Δ<em>t</em>,=<em>cR</em>Δ<em>t</em>.(7)(7)P(S→I)=aSINΔt,P(I→R)=bIΔt,P(R→S)=cRΔt.

For each possible move, a random number between 0 and 1 is generated. If the number is less than the probability for the move, the move is taken.

Develop now a Monte Carlo algorithm which implements the last equations using the same parameters <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>N</mi></math>">N</span></em>N, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>a</mi></math>">a</span></em>a, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>b</mi></math>">b</span></em>b, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>c</mi></math>">c</span></em>c for each population. Compare your results to those obtained with the deterministic differential equation solver and discuss your findings.

You will need to find the fraction of people when the system has been equilibrated. You will need to find the equlibrium expectation values and corresonding standard deviations.

<h3>Part c) Improvements, vital dynamics</h3>

The same principles used in this simple model can be extended to include more details about the population and disease.

For instance, vital dynamics can be easily added to the system so that the model can describe the spread of diseases which occur over longer stretches of time. If <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>e</mi></math>">e</span></em>e is the birth rate, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>d</mi></math>">d</span></em>d is the death rate, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><msub><mi>d</mi><mi>I</mi></msub></math>">d</span></em>IdI is the death rate of infected people due to the disease, then the modified differential equations are given by:

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto8&quot;><mtext>(8)</mtext></mtd><mtd><mtable columnalign=&quot;right left&quot; rowspacing=&quot;3pt&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;true&quot;><mtr><mtd><msup><mi>S</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mi>c</mi><mi>R</mi><mo>&amp;#x2212;</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mo>&amp;#x2212;</mo><mi>d</mi><mi>S</mi><mo>+</mo><mi>e</mi><mi>N</mi></mtd></mtr><mtr><mtd><msup><mi>I</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mo>&amp;#x2212;</mo><mi>b</mi><mi>I</mi><mo>&amp;#x2212;</mo><mi>d</mi><mi>I</mi><mo>&amp;#x2212;</mo><msub><mi>d</mi><mi>I</mi></msub><mi>I</mi></mtd></mtr><mtr><mtd><msup><mi>R</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mi>b</mi><mi>I</mi><mo>&amp;#x2212;</mo><mi>c</mi><mi>R</mi><mo>&amp;#x2212;</mo><mi>d</mi><mi>R</mi></mtd></mtr></mtable></mtd></mlabeledtr></mtable></math>">S</span></em>′<em>I</em>′<em>R</em>′=<em>cR</em>−<em>aSIN</em>−<em>dS</em>+<em>eN</em>=<em>aSIN</em>−<em>bI</em>−<em>dI</em>−<em>d</em>II=<em>bI</em>−<em>cR</em>−<em>dR</em>(8)(8)S′=cR−aSIN−dS+eNI′=aSIN−bI−dI−dIIR′=bI−cR−dR

Here, we have assumed that all the babies born into the population are initially susceptible.

Add now these additions to your ODE solver and Monte Carlo solver and discuss the results.

<h3>Part d) Seasonal Variation</h3>

For diseases such as influenza, the rate of transmission depends largely on the time of year. During the colder months, individuals are more likely to spend time in closer proximity to one another, resulting in a rate of transmission which oscillates. So we can let <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>a</mi></math>">a</span></em>a be given by

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto9&quot;><mtext>(9)</mtext></mtd><mtd><mi>a</mi><mo stretchy=&quot;false&quot;>(</mo><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>=</mo><mi>A</mi><mi>c</mi><mi>o</mi><mi>s</mi><mo stretchy=&quot;false&quot;>(</mo><mi>&amp;#x03C9;</mi><mi>t</mi><mo stretchy=&quot;false&quot;>)</mo><mo>+</mo><msub><mi>a</mi><mn>0</mn></msub><mo>,</mo></mtd></mlabeledtr></mtable></math>">a</span></em>(<em>t</em>)=<em>Acos</em>(<em>ωt</em>)+<em>a</em>0,(9)(9)a(t)=Acos(ωt)+a0,

where <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><msub><mi>a</mi><mn>0</mn></msub></math>">a</span></em>0a0 is the average transmission rate, <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>A</mi></math>">A</span></em>A is the maximum deviation from <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><msub><mi>a</mi><mn>0</mn></msub></math>">a</span></em>0a0, and <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>&amp;#x03C9;</mi></math>">ω</span></em>ω is the frequency of oscillation. Study the the effect of seasonal variations as well, with both the ODE and Monte Carlo solver. Try different values of the above new parameters and discuss your results.

<h3>Part e) Vaccination</h3>

Diseases with available vaccinations allow people to move directly from <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>S</mi></math>">S</span></em>S to <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>R</mi></math>">R</span></em>R, breaking the cyclic structure of the SIRS model. We assume that a susceptible individual’s choice to become vaccinated does not depend on how many other susceptibles are vaccinated. We may, however, assume that the rate of vaccination <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>f</mi></math>">f</span></em>f can depend on the time, since this rate may oscillate during the course of a year and/or increase as awareness and medical research increases. Then the system of differential equations become

<em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-_auto10&quot;><mtext>(10)</mtext></mtd><mtd><mtable columnalign=&quot;right left&quot; rowspacing=&quot;3pt&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;true&quot;><mtr><mtd><msup><mi>S</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mi>c</mi><mi>R</mi><mo>&amp;#x2212;</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mo>&amp;#x2212;</mo><mi>f</mi></mtd></mtr><mtr><mtd><msup><mi>I</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mfrac><mrow><mi>a</mi><mi>S</mi><mi>I</mi></mrow><mi>N</mi></mfrac><mo>&amp;#x2212;</mo><mi>b</mi><mi>I</mi></mtd></mtr><mtr><mtd><msup><mi>R</mi><mo>&amp;#x2032;</mo></msup></mtd><mtd><mi></mi><mo>=</mo><mi>b</mi><mi>I</mi><mo>&amp;#x2212;</mo><mi>c</mi><mi>R</mi><mo>+</mo><mi>f</mi></mtd></mtr></mtable></mtd></mlabeledtr></mtable></math>">S</span></em>′<em>I</em>′<em>R</em>′=<em>cR</em>−<em>aSIN</em>−<em>f</em>=<em>aSIN</em>−<em>bI</em>=<em>bI</em>−<em>cR</em>+<em>f</em>(10)(10)S′=cR−aSIN−fI′=aSIN−bIR′=bI−cR+f

Add now the effect of vaccination via the parameter <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>f</mi></math>">f</span></em>f and discuss again your results. Play around with different values of the parameter <em><span data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>f</mi></math>">f</span></em>f.

<h2>Introduction to numerical projects</h2>

Here follows a brief recipe and recommendation on how to write a report for each project.

<ul>

 <li>Give a short description of the nature of the problem and the eventual numerical methods you have used.</li>

 <li>Describe the algorithm you have used and/or developed. Here you may find it convenient to use pseudocoding. In many cases you can describe the algorithm in the program itself.</li>

 <li>Include the source code of your program. Comment your program properly.</li>

 <li>If possible, try to find analytic solutions, or known limits in order to test your program when developing the code.</li>

 <li>Include your results either in figure form or in a table. Remember to label your results. All tables and figures should have relevant captions and labels on the axes.</li>

 <li>Try to evaluate the reliabilty and numerical stability/precision of your results. If possible, include a qualitative and/or quantitative discussion of the numerical stability, eventual loss of precision etc.</li>

 <li>Try to give an interpretation of you results in your answers to the problems.</li>

 <li>Critique: if possible include your comments and reflections about the exercise, whether you felt you learnt something, ideas for improvements and other thoughts you’ve made when solving the exercise. We wish to keep this course at the interactive level and your comments can help us improve it.</li>

 <li>Try to establish a practice where you log your work at the computerlab. You may find such a logbook very handy at later stages in your work, especially when you don’t properly remember what a previous test version of your program did. Here you could also record the time spent on solving the exercise, various algorithms you may have tested or other topics which you feel worthy of mentioning.</li>

</ul>

<h2>Format for electronic delivery of report and programs</h2>

The preferred format for the report is a PDF file. You can also use DOC or postscript formats or as an ipython notebook file. As programming language we prefer that you choose between C/C++, Fortran2008 or Python. The following prescription should be followed when preparing the report:

<ul>

 <li>Use <strong>Canvas</strong> to hand in your projects, log in at <a href="https://www.uio.no/english/services/it/education/canvas/">https://www.uio.no/english/services/it/education/canvas/</a> with your normal UiO username and password.</li>

 <li>Upload <strong>only</strong> the report file! For the source code file(s) you have developed please provide us with your link to your github domain. The report file should include all of your discussions and a list of the codes you have developed. Do not include library files which are available at the course homepage, unless you have made specific changes to them. Alternatively, you can just upload the address to your GitHub or GitLab repository.</li>

 <li>In your git repository, please include a folder which contains selected results. These can be in the form of output from your code for a selected set of runs and input parameters.</li>

 <li>In this and all later projects, you should include tests (for example unit tests) of your code(s).</li>

 <li>Comments from us on your projects, approval or not, corrections to be made etc can be found under your <strong>Canvas</strong> domain and are only visible to you and the teachers of the course.</li>

</ul>