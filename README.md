Download Link: https://assignmentchef.com/product/solved-cs3760-artificial-intelligence-projects-1
<br>



<h1>Overview</h1>

<strong>Files: </strong>The files are available in the class git repo (and also on Moodle). The the course page for instructions on access the git server. The name of this assignment is contest1. You should only edit MySolver.py and description.txt.

<strong>Grading:      </strong>Each assignment will be graded as follows:

<table width="460">

 <tbody>

  <tr>

   <td width="124">30%</td>

   <td width="336">Performance on test problem instances relative to reference implementations (this will be based on your final version)</td>

  </tr>

  <tr>

   <td width="124">40%</td>

   <td width="336">Code quality: correctness, use of AI methods, clarity, etc.</td>

  </tr>

  <tr>

   <td width="124">30%</td>

   <td width="336">Description of algorithm used, why it is effective and the steps to took to improve it</td>

  </tr>

  <tr>

   <td width="124">up to 5% bonus</td>

   <td width="336">Performance relative to your classmates</td>

  </tr>

 </tbody>

</table>







<h1>What to change in MySolver.py</h1>

You should carefully go through the code in MySolver, you don’t have to work about the code in the other files. It’s similarly to the code we discussed in class for breadth-first search but there are some differences:

<ul>

 <li>It uses a priority queue to do breadth-first search. States are inserted with the priority equal to their depth in the search tree. The priority queue will always return the item with the lowest priority value.</li>

 <li>Instead of storing the nodes that have been expanded, it stores all of the that have either been expanded or put in the frontier. This makes it faster to search if any new states have been seen before. (Searching a priority-queue is slow.)</li>

 <li>There is a check in the while loop to make sure you have not exceeded the maximum time.</li>

</ul>

You should focus on changing two things in the code to get an efficient algorithm:

<ul>

 <li>Implement a useful heuristic function (possibly the sum of the Manhattan distances between each tiles location and it’s desired location.</li>

 <li>Change the priority that states are inserted in the priority queue with to implement A* search.</li>

</ul>

<h1>Running your program</h1>

You can test your code of various puzzles of different sizes and complexity. On the last page are some examples where the optimal solution length is known. You can run the program on one of these as follows:

python Run.py 3 120 -m ULLURRDDLLUURDR

This will try to solve a 3×3 puzzle with a known starting position and a time limit of 120 seconds. If you are running on a machine with cs1graphics installed, you can see what you solution looks like by adding an option:

python Run.py 3 120 -m ULLURRDDLLUURDR -g 200

where the 200 is the size of the graphics window. You can type python Run.py to see all of the options.

<h1>Hints</h1>

To do well consider the following:

<ul>

 <li>To have it run faster while you are testing use pypy3 instead of python; it’s a faster implementation of python. I will be using it to test your programs. It is installed on the Linux lab computers. On hooper you can use pypy (pypy3 should be installed soon.)</li>

 <li>Submit agents often. Test them, find improvements, document and submit again.</li>

 <li>Try basic algorithms/heuristics first.</li>

 <li>A webpage worth looking at</li>

</ul>

<strong>– </strong>http://kociemba.org/themen/fifteen/fifteensolver.html

<ul>

 <li>Ask questions and read discussions on the Moodle forum for this assignment</li>

</ul>

<h1>Examples</h1>

Here are some examples that you can run your code on to ensure that you are finding the optimal solutions. The ones with shorter solutions are usually easier to solve. You should test on those first.

<table width="516">

 <tbody>

  <tr>

   <td width="39"><strong>Size</strong></td>

   <td width="421"><strong>Moves to generate</strong></td>

   <td width="56"><strong>Length</strong></td>

  </tr>

  <tr>

   <td width="39">3</td>

   <td width="421">LDDRR</td>

   <td width="56">5</td>

  </tr>

  <tr>

   <td width="39">3</td>

   <td width="421">LURDLULURD</td>

   <td width="56">10</td>

  </tr>

  <tr>

   <td width="39">3</td>

   <td width="421">ULLURRDDLLUURDR</td>

   <td width="56">15</td>

  </tr>

  <tr>

   <td width="39">3</td>

   <td width="421">UULDDLUURDLDRULURRDD</td>

   <td width="56">20</td>

  </tr>

  <tr>

   <td width="39">3</td>

   <td width="421">ULDLUURDLDRRULLDRULURRDDL</td>

   <td width="56">25</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">RULDRURRDD</td>

   <td width="56">10</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">LUULURRDLDDLLUU</td>

   <td width="56">15</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">LUUULDDRDLLURRRUULDL</td>

   <td width="56">20</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">LUURDLULURRDDDLULDRU</td>

   <td width="56">20</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">LLLUUURDLURRRDDDLULDLURUU</td>

   <td width="56">25</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">UUULDRDDLUULURRDLURDDLDRU</td>

   <td width="56">25</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">UULURDDLLDLUURRURDLDLLURDRDLLU</td>

   <td width="56">30</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">ULUURDLLDDRRULLLURURDDDLUURULDDLDRR</td>

   <td width="56">35</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">LULUULDDDRRUULDDRUURULDRDLULLDRULUR</td>

   <td width="56">35</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">UULULDRULLDDRURULDLDDRRRULULDDLUURU</td>

   <td width="56">35</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">UUULDLDRDLULDRRRUULULDDLURDDRRUUULDRULLD</td>

   <td width="56">40</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">UUULLDDLDRRRUULLURDDLLDRUURDRUULDLDRDRUU</td>

   <td width="56">40</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">ULLDRRULULDRDLULURRRULLLDRDLDRULURRURDLDDLUUU</td>

   <td width="56">45</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">UULDLUULDRRURDDLDLULURULDDDRUURULDRDRUULDRDDL</td>

   <td width="56">45</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">LUURDDLULLUURDDLDRUURURDDLDLULURRDLLURURDDLUURRDLD</td>

   <td width="56">50</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">LLUURDDLULDRRRULLURRDDLUUULDLDRRRDLLLURRUURDDLULUR</td>

   <td width="56">50</td>

  </tr>

  <tr>

   <td width="39">4</td>

   <td width="421">LLLUURULDRRDRULDDRULDLURUULDDLURDRRUULDLURDRULLLDR</td>

   <td width="56">50</td>

  </tr>

 </tbody>

</table>


