Download Link: https://assignmentchef.com/product/solved-cs5421-project-2-functional-dependencies-and-normalisation
<br>
In this project, we use Python 3.8. Use the Python file “project2.py” from Luminus files to answer the questions. You may add additional functions to help you answer the questions. However, do not change the name and the parameters of the given functions in the template file. You may import additional Python standard libraries (e.g itertools, copy) but not external libraries.

For all questions, we use the following representations. The schema is represented as a Python list of non-empty strings. For example, the schema {<em>A,B,C,D</em>} is represented as [’A’, ’B’, ’C’, ’D’]. Even though it is represented as a list, the order of the elements in the list does not matter and it must have unique elements. A functional dependency is represented as a list of two lists. The order of the two elements matters. For example, the functional dependency {<em>AB</em>}→{<em>C</em>} is represented as [[’A’, ’B’], [’C’]]. A set of functional dependencies is a list of functional dependencies. The order of the functional dependencies does not matters.

You may assume that the input to the questions is always valid (e.g. no empty string, no incomplete functional dependency). You do not need to validate the input. The code should be readable and commented properly.

<strong>Question 1 </strong>[3 marks]

(a) Write a function closure that takes three parameters: a schema, a set of functional dependencies and a set of attributes, which is the subset of the schema, and returns the closure of the set of attributes.

For example, the attribute closure of {<em>A,B</em>}, {<em>A,B</em>}<sup>+ </sup>= {<em>A,B,C,D</em>}, closure([’A’, ’B’, ’C’, ’D’], [[[’A’, ’B’], [’C’]], [[’C’], [’D’]]], [’A’, ’B’])

= [’A’, ’B’, ’C’, ’D’]

<h1>CS4221/CS5421</h1>

(b) Write a function all closures that takes two parameters, a schema and a set of functional dependencies, and returns the closure of all subsets of attributes excluding super keys that are not candidate keys. The results is represented as a list of functional dependencies of the form <em>S </em>→ <em>S</em><sup>+ </sup>where <em>S </em>is a subset of attributes. For example, all_closures([’A’, ’B’, ’C’, ’D’], [[[’A’, ’B’], [’C’]], [[’C’], [’D’]]])

= [[[’A’], [’A’]], [[’B’], [’B’]], [[’C’], [’C’, ’D’]], [[’D’], [’D’]],

[[’A’, ’B’], [’A’, ’B’, ’C’, ’D’]], [[’A’, ’C’], [’A’, ’C’, ’D’]],

<h1>[[’A’, ’D’], [’A’, ’D’]], [[’B’, ’C’], [’B’, ’C’, ’D’]],</h1>

[[’B’, ’D’], [’B’, ’D’]], [[’C’, ’D’], [’C’, ’D’]], [[’A’, ’C’, ’D’], [’A’, ’C’, ’D’]], [[’B’, ’C’, ’D’], [’B’, ’C’, ’D’]]]

<strong>Question 2 </strong>[7 marks]

<ul>

 <li>Write a function min cover that takes two parameters, a schema and a set of functional dependencies, and returns a minimal cover of the functional dependencies. The results is represented as a list of functional dependencies. For example, min_cover([’A’, ’B’, ’C’, ’D’, ’E’, ’F’],</li>

</ul>

[[[’A’], [’B’, ’C’]],[[’B’], [’C’,’D’]], [[’D’], [’B’]],

[[’A’,’B’,’E’], [’F’]]])

= [[[’A’], [’B’]], [[’B’], [’C’]], [[’B’], [’D’]],

[[’D’], [’B’]], [[’A’, ’E’], [’F’]]]

There might be more than one correct answer to this question.

<ul>

 <li>Write a function min covers that takes two parameters, a schema and a set of functional dependencies, and returns all minimal covers reachable from the set of functional dependencies. The results is represented as a list of minimal covers. Make sure that you clearly explained the rationale of the algorithm for this question in the indicated comment section in the code. For example, min_covers([’A’, ’B’, ’C’], [[[’A’], [’B’]],[[’B’], [’C’]], [[’C’], [’A’]]]) = [[[[’A’], [’B’]], [[’B’], [’C’]], [[’C’], [’A’]]]]</li>

</ul>

For the case above, we find only one minimal cover.

<ul>

 <li>Write a function all min covers that takes two parameters, a schema and a set of functional dependencies, and returns all minimal covers. The results is represented as a list of minimal covers. Make sure that you clearly explained the rationale of the algorithm for this question in the indicated comment section in the code. For example, min_covers([’A’, ’B’, ’C’], [[[’A’], [’B’]],[[’B’], [’C’]], [[’C’], [’A’]]])</li>

</ul>

= [

[[[’A’], [’C’]], [[’B’], [’A’]], [[’C’], [’A’]], [[’A’], [’B’]]], [[[’B’], [’C’]], [[’C’], [’A’]], [[’A’], [’B’]]],

[[[’C’], [’B’]], [[’A’], [’C’]], [[’C’], [’A’]], [[’B’], [’C’]]],

[[[’C’], [’B’]], [[’A’], [’C’]], [[’B’], [’A’]]],

[[[’B’], [’C’]], [[’A’], [’B’]], [[’B’], [’A’]], [[’C’], [’B’]]]

]

For the case above, we find five minimal covers.