Download Link: https://assignmentchef.com/product/solved-cs217-magic-square
<br>
<strong>Question: To write a program for generating magic square of odd size using pointer arithmetic.</strong>

An 3×3 <em>normal magic square </em>is an arrangement of the numbers 1, 2, 3, … <em>n</em><sup>2</sup> in a square array, with the property that the sum of every row and column, as well as both diagonals, is the same number.  An example of a 3×3 normal magic square is




<table width="75">

 <tbody>

  <tr>

   <td width="25">6</td>

   <td width="23">1</td>

   <td width="28">8</td>

  </tr>

  <tr>

   <td width="25">7</td>

   <td width="23">5</td>

   <td width="28">3</td>

  </tr>

  <tr>

   <td width="25">2</td>

   <td width="23">9</td>

   <td width="28">4</td>

  </tr>

 </tbody>

</table>

You can verify that each of the three rows, the three columns, and the two diagonals add to 15.

Algorithm: To build a magic square we will be using  Loubere’s algorithm which is as follows:

<strong>Step 1: </strong>Begin by placing a 1 in the middle location of the top row:




<table width="75">

 <tbody>

  <tr>

   <td width="21"> </td>

   <td width="29">1</td>

   <td width="25"> </td>

  </tr>

  <tr>

   <td width="21"> </td>

   <td width="29"> </td>

   <td width="25"> </td>

  </tr>

  <tr>

   <td width="21"> </td>

   <td width="29"> </td>

   <td width="25"> </td>

  </tr>

 </tbody>

</table>

<strong>Step 2: </strong>We then write successive integers in an upward-right diagonal path (i.e. in the right column of row above current inserted element position), with the following special cases:

<ol>

 <li>When this upward-right movement would result in a location outside the boundaries of the square, we place the new number at the opposite end of the row or column that would contain the new number, if the rows and columns were not bounded.</li>

 <li>If the upward-right square is already occupied, place the new number directly below the current one.</li>

</ol>

In the 3×3 case, this gives us the following sequence of placements:

1.Place 1 in the middle location of the top row.

<table width="75">

 <tbody>

  <tr>

   <td width="21"> </td>

   <td width="29">1</td>

   <td width="25"> </td>

  </tr>

  <tr>

   <td width="21"> </td>

   <td width="29"> </td>

   <td width="25"> </td>

  </tr>

  <tr>

   <td width="21"> </td>

   <td width="29"> </td>

   <td width="25"> </td>

  </tr>

 </tbody>

</table>

<ol start="2">

 <li>Next place 2 on the above row and right column (Step 2 a). Since there is no row above first row so we place the 2 in the last row and next column.</li>

</ol>

<table width="75">

 <tbody>

  <tr>

   <td width="18"> </td>

   <td width="26">1</td>

   <td width="31"> </td>

  </tr>

  <tr>

   <td width="18"> </td>

   <td width="26"> </td>

   <td width="31"> </td>

  </tr>

  <tr>

   <td width="18"> </td>

   <td width="26"> </td>

   <td width="31">2</td>

  </tr>

 </tbody>

</table>

<ol start="3">

 <li>Next place 3 on the above row and right column (Step 2 a). Since there is no right column row so we place the 3 in the previous row and first column.</li>

</ol>

<table width="75">

 <tbody>

  <tr>

   <td width="25"> </td>

   <td width="23">1</td>

   <td width="28"> </td>

  </tr>

  <tr>

   <td width="25">3</td>

   <td width="23"> </td>

   <td width="28"> </td>

  </tr>

  <tr>

   <td width="25"> </td>

   <td width="23"> </td>

   <td width="28">2</td>

  </tr>

 </tbody>

</table>

<ol start="4">

 <li>Next place 4 on the above row and right column (Step 2 a). Since this place is already occupied place 4 below 3 (Step 2 b).</li>

</ol>

<table width="75">

 <tbody>

  <tr>

   <td width="25"> </td>

   <td width="23">1</td>

   <td width="28"> </td>

  </tr>

  <tr>

   <td width="25">3</td>

   <td width="23"> </td>

   <td width="28"> </td>

  </tr>

  <tr>

   <td width="25">4</td>

   <td width="23"> </td>

   <td width="28">2</td>

  </tr>

 </tbody>

</table>

<ol start="5">

 <li>Next place 5 on the above row and right column of number 4 (Step 2 a).</li>

</ol>

<table width="75">

 <tbody>

  <tr>

   <td width="25"> </td>

   <td width="23">1</td>

   <td width="28"> </td>

  </tr>

  <tr>

   <td width="25">3</td>

   <td width="23">5</td>

   <td width="28"> </td>

  </tr>

  <tr>

   <td width="25">4</td>

   <td width="23"> </td>

   <td width="28">2</td>

  </tr>

 </tbody>

</table>

<ol start="6">

 <li>Next place 6 on the above row and right column of number 5 (Step 2 a).</li>

</ol>




<table width="75">

 <tbody>

  <tr>

   <td width="25"> </td>

   <td width="23">1</td>

   <td width="28">6</td>

  </tr>

  <tr>

   <td width="25">3</td>

   <td width="23">5</td>

   <td width="28">7</td>

  </tr>

  <tr>

   <td width="25">4</td>

   <td width="23"> </td>

   <td width="28">2</td>

  </tr>

 </tbody>

</table>

<ol start="7">

 <li>Next place 7 on the above row and right column of number 6 (Step 2 a). Since this place is already occupied by 4 place 7 below 6.</li>

</ol>

<table width="75">

 <tbody>

  <tr>

   <td width="25"> </td>

   <td width="23">1</td>

   <td width="28">6</td>

  </tr>

  <tr>

   <td width="25">3</td>

   <td width="23">5</td>

   <td width="28">7</td>

  </tr>

  <tr>

   <td width="25">4</td>

   <td width="23"> </td>

   <td width="28">2</td>

  </tr>

 </tbody>

</table>

<ol start="8">

 <li>Next place 8 on the above row and right column of number 7 (Step 2 a). Since this place is already outside the boundaries, place 8 in the first row and first column.</li>

</ol>

<table width="75">

 <tbody>

  <tr>

   <td width="25">8</td>

   <td width="23">1</td>

   <td width="28">6</td>

  </tr>

  <tr>

   <td width="25">3</td>

   <td width="23">5</td>

   <td width="28">7</td>

  </tr>

  <tr>

   <td width="25">4</td>

   <td width="23"> </td>

   <td width="28">2</td>

  </tr>

 </tbody>

</table>

<ol start="9">

 <li>Finally, place 9 on the above row and right column of number 8 (Step 2 a). Since this place is already outside the boundaries as there is no row above first row so we place the 9 in the last row and next column to complete our magic square.</li>

</ol>

<table width="75">

 <tbody>

  <tr>

   <td width="25">8</td>

   <td width="23">1</td>

   <td width="28">6</td>

  </tr>

  <tr>

   <td width="25">3</td>

   <td width="23">5</td>

   <td width="28">7</td>

  </tr>

  <tr>

   <td width="25">4</td>

   <td width="23">9</td>

   <td width="28">2</td>

  </tr>

 </tbody>

</table>




Now see if you can follow this algorithm to build a 5×5 magic square (Follow step by step to build the magic ).

17 24 1      8    15

23 5     7    14 16

4     6    13 20 22

<ul>

 <li>12 19 21 3</li>

 <li>18 25 2 9</li>

</ul>

Once done your goal is to write the code for generating a magic square of odd size using the above algorithm. Make sure that the sum of all of the rows of generated magic square and sum of all of its columns and diagonals must be same. ()