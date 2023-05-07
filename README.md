Download Link: https://assignmentchef.com/product/solved-ir-assignment-3
<br>



Information Retrieval in High Dimensional Data







Please hand in your solutions via Moodle. Use the attached Jupyter notebook.

Solutions must be handed in by groups. Please state the names of your group members at a prominent place in your submission. (For example, at the beginning of your provided notebook or in a separate text file.)

<h1>The Kernel Trick</h1>

Task 1: [25 points] On Moodle you will find a Jupyter-Notebook that contains a function for dimensionality reduction via PCA. The function linear_pca expects a data matrix <strong>X </strong>∈ R<em><sup>p</sup></em><sup>×<em>N </em></sup>and a number of PCs <em>k </em>and returns the first <em>k </em>PCA scores for the matrix <strong>X</strong>.

<ul>

 <li>Provide code that tests the function with selected images from the provided MNIST training dataset by visualizing the first 2 scores in a scatter plot.</li>

 <li>Complete the function gram_pca such that it has the same functionality as linear_pca but expects a gram matrix <strong>K </strong>= <strong>X</strong><sup>&gt;</sup><strong>X </strong>instead of the data matrix <strong>X </strong>as its input. Do not assume that <strong>K </strong>was produced from centered data. Note: It is important to be consistent in notation here. E.g., for a data matrix of 1000 MNIST images, we have <strong>X </strong>∈ R784×1000 and <strong>K </strong>∈ R1000×1000.</li>

 <li>Test your implementation and show that gram_pca(dot(X.T,X), k) yields results equivalent to those of linear_pca(X, k).</li>

 <li>There is as an unknown vector space H, equipped with an inner product h·<em>,</em>iH and a function</li>

</ul>

<em>ϕ </em>: R<em><sup>p </sup></em>→ H<em>,</em>

such that

holds for every <strong>x</strong><em>,</em><strong>y </strong>∈ R<em><sup>p</sup></em>. The expression on the right-hand side of the equation is called the <em>Gaussian kernel </em>and <em>σ </em>is a parameter to choose by hand.

The function gaussian_kernel_pca expects a data matrix <strong>X</strong>, a reduced dimension number <em>k </em>and a parameter <em>σ</em>. It returns the first <em>k Kernel PCA </em>scores of the data. In other words, the function returns the first <em>k </em>PCA scores of

<em>ϕ</em>(<strong>x</strong><sub>1</sub>)<em>,ϕ</em>(<strong>x</strong><sub>2</sub>)<em>,…,ϕ</em>(<strong>x</strong><em><sub>N</sub></em>)<em>,</em>

where <strong>x</strong><em><sub>i </sub></em>denotes the <em>i</em>-th data sample/<em>i</em>-th column of the data matrix. The function gaussian_kernel_pca is already written, but for it to work, the function compute_gaussian_gram_matrix must return correct results. Complete compute_gaussian_gram_matrix accordingly.

<ul>

 <li>Test gaussian_kernel_pca with some MNIST train images and <em>σ </em>= 1000.</li>

</ul>