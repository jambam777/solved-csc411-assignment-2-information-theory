Download Link: https://assignmentchef.com/product/solved-csc411-assignment-2-information-theory
<br>
<ol>

 <li><strong> Information Theory. </strong>The goal of this question is to help you become more familiar with the basic equalities and inequalities of information theory. They appear in many contexts in machine learning and elsewhere, so having some experience with them is quite helpful. We review some concepts from information theory, and ask you a few questions.</li>

</ol>

Recall the definition of the entropy of a discrete random variable <em>X </em>with probability mass function. Here the summation is over all possible values of <em>x </em>∈ X, which (for simplicity) we assume is finite. For example, X might be {1<em>,</em>2<em>,…,N</em>}.

<ul>

 <li><strong> </strong>Prove that the entropy <em>H</em>(<em>X</em>) is non-negative.</li>

</ul>

An important concept in information theory is the relative entropy or the KL-divergence of two distributions <em>p </em>and <em>q</em>. It is defined as

KL<em>.</em>

The KL-divergence is one of the most commonly used measure of difference (or divergence) between two distributions, and it regularly appears in information theory, machine learning, and statistics. For this question, you may assume <em>p</em>(<em>x</em>) <em>&gt; </em>0 and <em>q</em>(<em>x</em>) <em>&gt; </em>0 for all <em>x</em>.

If two distributions are close to each other, their KL divergence is small. If they are exactly the same, their KL divergence is zero. KL divergence is not a true distance metric (since it isn’t symmetric and doesn’t satisfy the triangle inequality), but we often use it as a measure of dissimilarity between two probability distributions.

<ul>

 <li><strong> </strong>Prove that KL(<em>p</em>||<em>q</em>) is non-negative. <em>Hint: you may want to use Jensen’s Inequality, which is described in the Appendix.</em></li>

 <li><strong> </strong>The Information Gain or Mutual Information between <em>X </em>and <em>Y </em>is <em>I</em>(<em>Y </em>;<em>X</em>) =</li>

</ul>

<em>H</em>(<em>Y </em>) − <em>H</em>(<em>Y </em>|<em>X</em>). Show that

<em>I</em>(<em>Y </em>;<em>X</em>) = KL(<em>p</em>(<em>x,y</em>)||<em>p</em>(<em>x</em>)<em>p</em>(<em>y</em>))<em>,</em>

where <em>p</em>(<em>x</em>) = <sup>P</sup><em><sub>y </sub>p</em>(<em>x,y</em>) is the marginal distribution of <em>X</em>.

<ol start="2">

 <li><strong>Benefit of Averaging. </strong>Consider <em>m </em>estimators <em>h</em><sub>1</sub><em>,…,h<sub>m</sub></em>, each of which accepts an input <em>x </em>and produces an output <em>y</em>, i.e., <em>y<sub>i </sub></em>= <em>h<sub>i</sub></em>(<em>x</em>). These estimators might be generated through a Bagging procedure, but that is not necessary to the result that we want to prove. Consider the squared error loss function. Show that the loss of the average estimator</li>

</ol>

<em>,</em>

is smaller than the average loss of the estimators. That is, for any <em>x </em>and <em>t</em>, we have

<em>.</em>

<em>Hint: you may want to use Jensen’s Inequality, which is described in the Appendix.</em>

<ol start="3">

 <li><strong>AdaBoost. </strong>The goal of this question is to show that the AdaBoost algorithm changes the weights in order to force the weak learner to focus on difficult data points. Here we consider the case that the target labels are from the set {−1<em>,</em>+1} and the weak learner also returns a classifier whose outputs belongs to {−1<em>,</em>+1} (instead of {0<em>,</em>1}). Consider the <em>t</em>-th iteration of AdaBoost, where the weak learner is</li>

</ol>

<em>N</em>

<em>h<sub>t </sub></em>← argmin<sup>X</sup><em>w<sub>i</sub></em>I{<em>h</em>(<strong>x</strong><sup>(<em>i</em>)</sup>) 6= <em>t</em><sup>(<em>i</em>)</sup>}<em>,</em>

<em>h</em>∈H

<em>i</em>=1

the <em>w</em>-weighted classification error is

err         <em>,</em>

<em>i</em>=1

and the classifier coefficient is . (Here, log denotes the natural logarithm.) AdaBoost changes the weights of each sample depending on whether the weak learner <em>h<sub>t </sub></em>classifies it correctly or incorrectly. The updated weights for sample <em>i </em>is denoted byand is

<em> .</em>

Show that the error w.r.t. () is exactly       . That is, show that

err         <em>.</em>

<em>i</em>=1 <em>w</em><em>i</em>

Note that here we use the weak learner of iteration <em>t </em>and evaluate it according to the new weights, which will be used to learn the <em>t </em>+ 1-st weak learner. What is the interpretation of this result?

<strong>Tips:</strong>

<ul>

 <li>Start from err<sup>0</sup><em><sub>t </sub></em>and divide the summation to two sets of <em>E </em>= {<em>i </em>: <em>h<sub>t</sub></em>(<strong>x</strong><sup>(<em>i</em>)</sup>) 6= <em>t</em><sup>(<em>i</em>)</sup>} and its complement <em>E<sup>c </sup></em>= {<em>i </em>: <em>h<sub>t</sub></em>(<strong>x</strong><sup>(<em>i</em>)</sup>) = <em>t</em><sup>(<em>i</em>)</sup>}.</li>

 <li>Note that</li>

</ul>

<em>.</em>

<strong>Appendix: Convexity and Jensen’s Inequality. </strong>Here, we give some background on convexity which you may find useful for some of the questions in this assignment. You may assume anything given here.

Convexity is an important concept in mathematics with many uses in machine learning. We briefly define convex set and function and some of their properties here. Using these properties are useful in solving some of the questions in the rest of this homework. If you are interested to know more about convexity, refer to Boyd and Vandenberghe, Convex Optimization, 2004.

A set <em>C </em>is <em>convex </em>if the line segment between any two points in <em>C </em>lies within <em>C</em>, i.e., if for any <em>x</em><sub>1</sub><em>,x</em><sub>2 </sub>∈ <em>C </em>and for any 0 ≤ <em>λ </em>≤ 1, we have

<em>λx</em><sub>1 </sub>+ (1 − <em>λ</em>)<em>x</em><sub>2 </sub>∈ <em>C.</em>

For example, a cube or sphere in R<em><sup>d </sup></em>are convex sets, but a cross (a shape like X) is not.

A function <em>f </em>: R<em><sup>d </sup></em>→ R is <em>convex </em>if its domain is a convex set and if for all <em>x</em><sub>1</sub><em>,x</em><sub>2 </sub>in its domain, and for any 0 ≤ <em>λ </em>≤ 1, we have

<em>f</em>(<em>λx</em><sub>1 </sub>+ (1 − <em>λ</em>)<em>x</em><sub>2</sub>) ≤ <em>λf</em>(<em>x</em><sub>1</sub>) + (1 − <em>λ</em>)<em>f</em>(<em>x</em><sub>2</sub>)<em>.</em>

This inequality means that the line segment between (<em>x</em><sub>1</sub><em>,f</em>(<em>x</em><sub>1</sub>)) and (<em>x</em><sub>2</sub><em>,f</em>(<em>x</em><sub>2</sub>)) lies above the graph of <em>f</em>. A convex function looks like `. We say that <em>f </em>is <em>concave </em>if −<em>f </em>is convex. A concave function looks like a.

Some examples of convex and concave functions are (you do not need to use most of them in your homework, but knowing them is useful):

<ul>

 <li>Powers: <em>x<sup>p </sup></em>is convex on the set of positive real numbers when <em>p </em>≥ 1 or <em>p </em>≤ 0. It is concave for 0 ≤ <em>p </em>≤ 1.</li>

 <li>Exponential: <em>e<sup>ax </sup></em>is convex on R, for any <em>a </em>∈ R.</li>

 <li>Logarithm: log(<em>x</em>) is concave on the set of positive real numbers.</li>

 <li>Norms: Every norm on R<em><sup>d </sup></em>is convex.</li>

 <li>Max function: <em>f</em>(<em>x</em>) = max{<em>x</em><sub>1</sub><em>,x</em><sub>2</sub><em>,…,x<sub>d</sub></em>} is convex on R<em><sup>d</sup></em>.</li>

 <li>Log-sum-exp: The function <em>f</em>(<em>x</em>) = log(<em>e<sup>x</sup></em><sup>1 </sup>+ <em>… </em>+ <em>e<sup>x</sup></em><em><sup>d</sup></em>) is convex on R<em><sup>d</sup></em>.</li>

</ul>

An important property of convex and concave functions, which you may need to use in your homework, is <em>Jensen’s inequality</em>. Jensen’s inequality states that if <em>φ</em>(<em>x</em>) is a convex function of <em>x</em>, we have <em>φ</em>(E[<em>X</em>]) ≤ E[<em>φ</em>(<em>X</em>)]<em>.</em>

In words, if we apply a convex function to the expectation of a random variable, it is less than or equal to the expected value of that convex function when its argument is the random variable. If the function is concave, the direction of the inequality is reversed.

Jensen’s inequality has a physical interpretation: Consider a set X = {<em>x</em><sub>1</sub><em>,…,x<sub>N</sub></em>} of points on R. Corresponding to each point, we have a probability <em>p</em>(<em>x<sub>i</sub></em>). If we interpret the probability as mass, and we put an object with mass <em>p</em>(<em>x<sub>i</sub></em>) at location (<em>x<sub>i</sub>,φ</em>(<em>x<sub>i</sub></em>)), then the centre of gravity of these objects, which is in R<sup>2</sup>, is located at the point (E[<em>X</em>]<em>,</em>E[<em>φ</em>(<em>X</em>)]). If <em>φ </em>is convex `, the centre of gravity lies above the curve <em>x </em>7→ <em>φ</em>(<em>x</em>), and vice versa for a concave function a.