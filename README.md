# quadtree-circles-js

This is a circular implementation of this library by Timo Hausmann:
https://github.com/timohausmann/quadtree-js

This is not a collision engine, but an algorithm to narrow down objects of possible collision. 

Please read the tutorial if you want to know more about Quadtrees.

There are two examples in the examples directory. 

* red squares represent Quadtree Nodes
* empty white circles represent objects in our Quadtree
* the cursor is the area we constantly test for
* objects turned green are candidates for collision, returned from the recieve-function

## How to use

Create a new Quadtree with default values for max_objects (10) and max_levels (4)
<pre>
var myTree = new Quadtree({
	x: 0,
	y: 0,
	width: 400,
	height: 300
});
</pre>

If you want to specify max_objects and max_levels on your own, you can pass them as a 2nd and 3rd argument
<pre>
var myTree = new Quadtree({
	x: 0,
	y: 0,
	width: 800,
	height: 600
}, 5, 8);
</pre> 

Insert an element in the Quadtree
<pre>
myTree.insert({
	x : 200,
	y : 150,
	radius : 20
});
</pre>

Retrieve elements that "collide" with the given bounds
<pre>
var elements = myTree.retrieve({
	x : 150,
	y : 100,
	radius : 20
});
</pre>

Clear the Quadtree
<pre>
myTree.clear();
</pre>

Check out the examples for more information.
