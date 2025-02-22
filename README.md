# lab03-grammars
Name: Xiaoxiao(Crystal) Zou & Ruijun(Daniel) Zhong  

## 1. Wheat grammar puzzle
Look at these iterations (n = 1, 2, 3) of a one-rule grammar. Using the built in symbols in Houdini, design a grammar that produces this output. Take a screenshot of your rules.\
<img width="200" alt="square1" src="https://user-images.githubusercontent.com/1758825/193949661-a3a0e1f7-7d68-4b9e-8384-d9991e1e9fd2.png">
<img width="200" alt="square2" src="https://user-images.githubusercontent.com/1758825/193949853-cf2306b3-3537-4c24-91b5-0a3083bc87c0.png">
<img width="200" alt="square3" src="https://user-images.githubusercontent.com/1758825/193949859-5e432b4b-f18d-48b5-a9e9-8d7dba255955.png">

  Angle: 20  
![](1.png)

## 2. Square grammar puzzle
How about this one? Take a screenshot of your rules.\
<img width="200" alt="square1" src="https://user-images.githubusercontent.com/1758825/193949895-87cdfb43-da7c-4867-ab1b-107e1ba9d2a7.png">
<img width="200" alt="square2" src="https://user-images.githubusercontent.com/1758825/193949904-a9cdfe0f-319e-4ca8-9935-dd338217a7cf.png">
<img width="200" alt="square3" src="https://user-images.githubusercontent.com/1758825/193949910-928e5993-ce26-4681-80f8-ffeb54be4dcf.png">  
Angle: 90  
![](2.png)

## 3. Custom plant
Choose a plant in the world. Working off a reference, design a grammar that mimics the structure of that plant. Unlike our simple puzzles, please use multiple rules for greater complexity. Think carefully about the structure of your grammar! EXPLAIN the structure of your plant in the README. What are the components? What do each of the rules do? Be sure to also include images of a few iterations of your output plant. 
 
![](3.png)
![](3.1.png)
![](3.3.png)
![](3.2.png)

 ### Parameters:
 * Angle: 50 * randscale
 * Step size: 0.08

 ### Explanation of Rule:
 We use the rules to simulate dandelion:  
 F = \ / \ /C: 
  * Turn Left-Rgiht-Left of C  

 A = FFFF[//[++F]][\\[+F]][/[-F]][\[--F]] & B = B=FFFF[//[++F]][\\[+F]][/[-F]][\[--F]]: 
   * FFFF = Move forward 4 times
   * [//[++F]]: Save the dandelion's state, Right-Right-Forward, then return to the saved state.
   * [\\[+F]]: Save the dandelion's state, Left-Right-Forward, then return to the saved state.
   * [/[-F]]: Save the dandelion's state, Left-Forward, then return to the saved state.
   * [\[--F]]: Save the dandelion's state, Left-Left-Forward, then return to the saved state.

C = [A][B]:
* Make system branches twice A then B.

