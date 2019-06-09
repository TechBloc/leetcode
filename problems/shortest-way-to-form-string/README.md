<!--|This file generated by command(leetcode description); DO NOT EDIT.    |-->
<!--+----------------------------------------------------------------------+-->
<!--|@author    Openset <openset.wang@gmail.com>                           |-->
<!--|@link      https://github.com/openset                                 |-->
<!--|@home      https://github.com/openset/leetcode                        |-->
<!--+----------------------------------------------------------------------+-->

[< Previous](https://github.com/openset/leetcode/tree/master/problems/distant-barcodes "Distant Barcodes")
　　　　　　　　　　　　　　　　
[Next >](https://github.com/openset/leetcode/tree/master/problems/confusing-number "Confusing Number")

## 1055. Shortest Way to Form String (Medium)

<p>From any string, we can form a <i>subsequence</i> of that string by deleting some number of characters (possibly no deletions).</p>

<p>Given two strings <code>source</code> and <code>target</code>, return the minimum number of subsequences of <code>source</code> such that their concatenation equals <code>target</code>. If the task is impossible, return <code>-1</code>.</p>

<p>&nbsp;</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input: </strong>source = <span id="example-input-1-1">&quot;abc&quot;</span>, target = <span id="example-input-1-2">&quot;abcbc&quot;</span>
<strong>Output: </strong><span id="example-output-1">2</span>
<strong>Explanation: </strong>The target &quot;abcbc&quot; can be formed by &quot;abc&quot; and &quot;bc&quot;, which are subsequences of source &quot;abc&quot;.
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input: </strong>source = <span id="example-input-2-1">&quot;abc&quot;</span>, target = <span id="example-input-2-2">&quot;acdbc&quot;</span>
<strong>Output: </strong><span id="example-output-2">-1</span>
<strong>Explanation: </strong>The target string cannot be constructed from the subsequences of source string due to the character &quot;d&quot; in target string.
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input: </strong>source = <span id="example-input-3-1">&quot;xyz&quot;</span>, target = <span id="example-input-3-2">&quot;xzyxz&quot;</span>
<strong>Output: </strong><span id="example-output-3">3</span>
<strong>Explanation: </strong>The target string can be constructed as follows &quot;xz&quot; + &quot;y&quot; + &quot;xz&quot;.
</pre>

<p>&nbsp;</p>

<p><strong>Note:</strong></p>

<ol>
	<li>Both the <code>source</code> and <code>target</code> strings consist of only lowercase English letters from &quot;a&quot;-&quot;z&quot;.</li>
	<li>The lengths of <code>source</code> and <code>target</code> string are between <code>1</code> and <code>1000</code>.</li>
</ol>

### Related Topics
  [[Greedy](https://github.com/openset/leetcode/tree/master/tag/greedy/README.md)]
  [[Dynamic Programming](https://github.com/openset/leetcode/tree/master/tag/dynamic-programming/README.md)]

### Similar Questions
  1. [Is Subsequence](https://github.com/openset/leetcode/tree/master/problems/is-subsequence) (Medium)

### Hints
<details>
<summary>Hint 1</summary>
Which conditions have to been met in order to be impossible to form the target string?
</details>

<details>
<summary>Hint 2</summary>
If there exists a character in the target string which doesn't exist in the source string then it will be impossible to form the target string.
</details>

<details>
<summary>Hint 3</summary>
Assuming we are in the case which is possible to form the target string, how can we assure the minimum number of used subsequences of source?
</details>

<details>
<summary>Hint 4</summary>
For each used subsequence try to match the leftmost character of the current subsequence with the leftmost character of the target string, if they match then erase both character otherwise erase just the subsequence character whenever the current subsequence gets empty, reset it to a new copy of subsequence and increment the count, do this until the target sequence gets empty. Finally return the count.
</details>