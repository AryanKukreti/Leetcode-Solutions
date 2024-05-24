<h2><a href="https://leetcode.com/problems/container-with-most-water">11. Container With Most Water</a></h2><h3>Medium</h3><hr><p>You are given an integer array <code>height</code> of length <code>n</code>. There are <code>n</code> vertical lines drawn such that the two endpoints of the <code>i<sup>th</sup></code> line are <code>(i, 0)</code> and <code>(i, height[i])</code>.</p>

<p>Find two lines that together with the x-axis form a container, such that the container contains the most water.</p>

<p>Return <em>the maximum amount of water a container can store</em>.</p>

<p><strong>Notice</strong> that you may not slant the container.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>
<img alt="" src="https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg" style="width: 600px; height: 287px;" />
<pre>
<strong>Input:</strong> height = [1,8,6,2,5,4,8,3,7]
<strong>Output:</strong> 49
<strong>Explanation:</strong> The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> height = [1,1]
<strong>Output:</strong> 1
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>n == height.length</code></li>
	<li><code>2 &lt;= n &lt;= 10<sup>5</sup></code></li>
	<li><code>0 &lt;= height[i] &lt;= 10<sup>4</sup></code></li>
</ul>


## The Approach


We know that water container is a rectangle so area will be simply **lxb** = area so either we need to increase the length or the breadth to maximise the area . Placing the pointer at two ends creates maximises the length now the interesting part if you move any of the two pointer then you are reducing the length so to balance it you must increase the breadth(height) . There are two pointer pointing to two different height now obviously we need to move that pointer which has less height among the two and we move the pointer unless it finds a height that is greater than its previous value and then calculates the area and store

To find the maximum water storage between two pillars with given heights, we'll use a "Two Pointer" approach. We'll start with pointers at the first and last pillars and calculate the water storage area between them. We'll move the pointer associated with the shorter pillar inward, as it limits the height of the container.

Here's how it works using the given input:

We start with two pointers, one at the first pillar (height = 1) and the other at the last pillar (height = 7).

We calculate the water storage area, which is the minimum height (1) times the distance between the pillars (8), giving us an initial area of 8.
Since the pointer at the first pillar (1) is shorter than the pointer at the last pillar (7), we move it inward to the next pillar (height = 8).

Now, we recalculate the water storage area using the new height (8) and the same distance between the pillars (8), giving us an area of 64.
The pointer at the last pillar remains in place since the height (7) is greater than the previous height.
We continue this process, moving the pointers inward and recalculating the area, until the pointers converge.
Finally, we return the maximum water storage area found, which is 49.
This approach efficiently finds the maximum water storage area between two pillars, considering the height and distance between them.=
