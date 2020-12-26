---
layout: post
type: blog
title: "TCS Mockvita 2 Questions with soln."
subtitle: "TCS Mockvita 2 Questions with soln"
description: "TCS Mockvita 2 questions with soln."
# image: assets/images/pic05.jpg
sortdescp: "TCS codevita season 9's mockvita2 questions with answers."
---

## Swayamvar

### Problem Description

A ceremony where a Bride chooses her Groom from an array of eligible bachelors is called Swayamvar. But this is a Swayamvar with difference. An array of Bride-to-be will choose from an array of Groom-to-be.

The arrangement at this Swayamvar is as follows
 - Brides-to-be are organized such that the most eligible bachelorette will get first chance to choose her Groom. Only then, the next most eligible bachelorette will get a chance to choose her Groom.
 - If the initial most eligible bachelorette does not get a Groom of her choice, none of the Brides-to-be have any chance at all to get married. So unless a senior bachelorette is out of the "queue", the junior bachelorette does not get a chance to select her Groom-to-be
 - Inital state of Grooms-to-be is such that most eligible bachelor is at the head of the "queue". The next most eligible bachelor is next in the queue. So on and so forth.
 - Now everything hinges on the choice of the bachelorette. The most eligible bachelorette will now meet the most eligible bachelor.
 - If bachelorette selects the bachelor, both, the bachelorette and the bachelor are now Bride and Groom respectively and will no longer be a part of the Swayamvar activity. Now, the next most eligible bachelorette will get a chance to choose her Groom. Her first option is the next most eligible bachelor (relative to initial state)
 - If the most eligible bachelorette passes the most eligible bachelor, the most eligible bachelor now moves to the end of the queue. The next most eligible bachelor is now considered by the most eligible bachelorette. Selection or Passing over will have the same consequences as explained earlier.
 - If most eligible bachelorette reaches the end of bachelor queue, then the Swayamvar is over. Nobody can get married.
 -Given a mix of Selection or Passing over, different pairs will get formed.

 **The selection criteria is as follows**
1. Each person either drinks rum or mojito. Bride will choose groom only if he drinks the same drink as her. 

<b>Note</b> : There are equal number of brides and grooms for the swayamvar.

Tyrion as the hand of the king wants to know how many pairs will be left unmatched. Can you help Tyrion?
<div class="heading-tab active">
   <h3 id="hconst">Constraints</h3>
</div>
<div class="content-tab" style="opacity: 1;">
   <p id="const"></p>
   <p>1&lt;= N &lt;= 10^4</p>
   <p></p>
</div>
<div class="heading-tab active">
   <h3 id="hinput">Input Format</h3>
</div>
<div class="content-tab" style="opacity: 1;">
   <p id="input"></p>
   <p>First line contains one integer N, which denotes the number of brides and grooms taking part in the swayamvar.</p>
   <p> Second line contains a string in lowercase, of length N containing initial state of brides-to-be. </p>
   <p>Third line contains a string in lowercase, of length N containing initial state of grooms-to-be. Each string contains only lowercase 'r' and 'm' stating person at that index drinks "rum"(for 'r') or mojito(for 'm').</p>
   <p></p>
</div>
<div class="heading-tab active">
   <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
   <h3 id="houtput">Output</h3>

<div class="content-tab" style="opacity: 1;">
   <p id="output"></p>
   <p>Output a single integer denoting the number of pairs left unmatched.</p>
   <p></p>
</div>
<div class="heading-tab active">
   <h3 id="htestcase">Timeout</h3>
</div>
<div class="content-tab" style="opacity: 1;">
   <p>1</p>
</div>
<div class="heading-tab active">
   <h3 id="hexplanation">Explanation</h3>
</div>
<div class="content-tab" style="opacity: 1;">
   <p id="explanation"></p>
   <p>Example 1</p>
   <p>Input</p>
   <p>4</p>
   <p>rrmm</p>
   <p> mrmr</p>
   <p>Output</p>
   <p>0</p>
   <p>Explanation</p>
   <p>The bride at first place will only marry groom who drinks rum. So the groom at first place will join the end of the queue. Updated groom's queue is "rmrm".</p>
   <p>Now the bride at first place will marry the groom at first place. Updated bride's queue is "rmm" and groom's queue is "mrm".</p>
   <p>The process continues and at last there are no pairs left. So answer is 0.</p>

   <p>Example 2</p>
   <p>Input</p>
   <p>4</p>
   <p> rmrm</p>
   <p> mmmr</p>
   <p>Output</p>
   <p>2</p>
   <p>Explanation</p>
   <p>Following the above process 2 pairs will be left unmatched. Remember that bride will not move until she gets a groom of her choice.</p>

<h3>soln.</h3>
{% highlight python %}
N = int(input())
br = input()
br = br[::-1]
gr = input()
def removeElement(data,pos):
    tmpstr = data[0:pos]+data[pos+1:]
    return tmpstr
while(len(br)>0):
    flag = True
    tmpcntr = len(gr)-1
    while(tmpcntr>=0):
        if br[len(br)-1] == gr[tmpcntr]:
            br = removeElement(br,len(br)-1)
            gr = removeElement(gr,tmpcntr)
            flag=False
            break;
        else:
            tmpcntr=tmpcntr-1
    if flag:
        break
print(len(br))
{% endhighlight %}

<div >
   <p></p>
   <h2 id="problemname">Digit Pairs</h2>
   <div class="heading-tab active">
      
      <h3>Problem Description</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="problemdesc"></p>
      <p></p>
      <p>Given N three-digit numbers, your task is to find bit score of all N numbers and then print&nbsp;the number of pairs possible based on these calculated bit score.</p>
      <p></p>
      <p class="list_Paragraph">1. <b>Rule for calculating bit score from three digit number:</b> </p>
      <p>From the 3-digit number, </p>
      <p class="list_Paragraph">" extract largest digit and multiply by 11 then </p>
      <p class="list_Paragraph">" extract smallest digit multiply by 7 then</p>
      <p class="list_Paragraph">" add both the result for getting bit pairs.</p>
      <p>Note: - Bit score should be of 2-digits, if above results in a 3-digit bit score, simply ignore most significant digit.</p>
      <p>Consider following examples: </p>
      <p>Say, number is 286</p>
      <p>Largest digit is 8 and smallest digit is 2</p>
      <p>So, 8*11+2*7 =102 so ignore most significant bit , So bit score = 02.</p>
      <p>Say, Number is 123</p>
      <p>Largest digit is 3 and smallest digit is 1</p>
      <p>So, 3*11+7*1=40, so bit score is 40.</p>
      <p></p>
      <p class="list_Paragraph">2. <b>Rules for making pairs from above calculated bit scores</b> </p>
      <p>Condition for making pairs are</p>
      <p class="list_Paragraph">" Both bit scores should be in&nbsp;either odd position or even position to be eligible to form a pair.</p>
      <p class="list_Paragraph">" Pairs can be only made if&nbsp;most significant digit&nbsp;are same and&nbsp;at most two pair can be made&nbsp;for a given significant digit.</p>
      <p></p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hconst">Constraints</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="const"></p>
      <p>N&lt;=500</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hinput">Input Format</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="input"></p>
      <p>First line contains an integer N, denoting the count of numbers.</p>
      <p>Second line contains N 3-digit integers delimited by space</p>
      <p></p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="houtput">Output</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="output"></p>
      <p>One integer value denoting the number of bit pairs.</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="htestcase">Timeout</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p>1</p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hexplanation">Explanation</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="explanation"></p>
      <p>Example 1</p>
      <p>Input</p>
      <p> <a name="_GoBack"></a>8</p>
      <p> 234 567 321 345 123 110 767 111</p>
      <p>Output</p>
      <p>3</p>
      <p>Explanation</p>
      <p>After getting the most and least significant digits of the numbers and applying the formula given in Rule 1 we get the bit scores of the numbers as: </p>
      <p>58 12 40 76 40 11 19 18</p>
      <p>No. of pair possible are 3:</p>
      <p>40 appears twice at odd-indices 3 and 5 respectively. Hence, this is one pair. </p>
      <p>12, 11, 18 are at even-indices. Hence, two pairs are possible from these three-bit scores.</p>
      <p>Hence total pairs possible is 3</p>
      <p></p>
   </div>
</div>

<div >
   <p></p>
   <h2 id="problemname">Dole Out Cadbury</h2>
   <div class="heading-tab active">
      
      <h3>Problem Description</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="problemdesc"></p>
      <p>You are a teacher in reputed school. During Celebration Day you were assigned a task to distribute Cadbury such that maximum children get the chocolate. You have a box full of Cadbury with different width and height. You can only distribute largest square shape Cadbury. So if you have a Cadbury of length 10 and width 5, then you need to break Cadbury in 5X5 square and distribute to first child and then remaining 5X5 to next in queue</p>
      <p></p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hconst">Constraints</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="const"></p>
      <p>0&lt;P&lt;Q&lt;1501</p>
      <p>0&lt;R&lt;S&lt;1501</p>
      <p></p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hinput">Input Format</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="input"></p>
      <p>First line contains an integer P that denotes minimum length of Cadbury in the box</p>
      <p>Second line contains an integer Q that denotes maximum length of Cadbury in the box</p>
      <p>Third line contains an integer R that denotes minimum width of Cadbury in the box</p>
      <p> <a name="_GoBack"></a>Fourth line contains an integer S that denotes maximum width of Cadbury in the box</p>
      <p></p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="houtput">Output</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="output"></p>
      <p>Print total number of children who will get chocolate.</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="htestcase">Timeout</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p>1</p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hexplanation">Explanation</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="explanation"></p>
      <p>Example 1</p>
      <p>Input</p>
      <p class="normal_(Web)">5</p>
      <p class="normal_(Web)">7</p>
      <p class="normal_(Web)">3</p>
      <p class="normal_(Web)">4</p>
      <p>Output</p>
      <p>24</p>
      <p>Explanation</p>
      <p class="normal_(Web)">Length is in between 5 to 7 and width is in between 3 to 4.</p>
      <p class="normal_(Web)">So we have 5X3,5X4,6X3,6X4,7X3,7X4 type of Cadbury in the box.</p>
      <p class="normal_(Web)"></p>
      <p class="normal_(Web)">If we take 5X3 :</p>
      <p class="normal_(Web)">First, we can give 3X3 square Cadbury to 1st child .Then we are left with 3X2. Now largest square is 2X2 which will be given to next child. Next, we are left with two&nbsp; 1X1 part of Cadbury which will be given to another two children.</p>
      <p class="normal_(Web)">And so on</p>
      <p></p>
   </div>
</div>
<h3>Soln.</h3>
{% highlight python %}
p = int(input())
q = int(input())
r = int(input())
s = int(input())
sum = 0
def countpb(i):
    x=i[0]
    y=i[1]
    cnt = 1
    if x>y:
        return cnt+countpb(list([x-y,y]))
    elif y>x:
        return cnt+countpb(list([x,y-x]))
    else:
        return cnt
for i in range(p,q+1):
    for j in range(r,s+1):
        sum = sum + countpb(list([i,j]))
print(sum)

{% endhighlight %}

<div >
   <p></p>
   <h2 id="problemname">Petrol Pump</h2>
   <div class="heading-tab active">
      
      <h3>Problem Description</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="problemdesc"></p>
      <p>A big group of students, starting a long journey on different set of vehicles need to fill petrol in their vehicles.</p>
      <p>As group leader you are required to minimize the time they spend at the petrol pump to start the journey at the earliest. You will be given the quantity of petrol (in litres) that can be filled in each vehicle. There are two petrol vending machines at the petrol pump. You need to arrange the vehicles in such a way that they take shortest possible time to fill all the vehicles and provide the time taken in seconds as output. Machine vends petrol @ 1litre/second.</p>
      <p>Assume that there is no time lost between switching vehicles to start filling petrol.</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hconst">Constraints</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="const"></p>
      <p>1&lt;= Number of vehicles &lt; 50.</p>
      <p>0 &lt;= Quantity of petrol required in any vehicle &lt;= 200 </p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hinput">Input Format</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="input"></p>
      <p>First line will provide the quantity of petrol (separated by space) that can be filled in each vehicle.</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="houtput">Output</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="output"></p>
      <p>Shortest possible time to fill petrol in all the vehicles.</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="htestcase">Timeout</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p>1</p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hexplanation">Explanation</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="explanation"></p>
      <p>Example 1</p>
      <p>Input</p>
      <p>1 2 3 4 5 10 11 3 6 16</p>
      <p>Output</p>
      <p>31</p>
      <p>Explanation</p>
      <p>First Petrol vending machine will cater to vehicles taking - 16, 6, 4, 3, 2 litres of petrol (Total 31 sec)</p>
      <p>Second machine will cater to vehicles taking - 11, 10, 5, 3, 1 litres of petrol (Total 30 sec)</p>
      <p>Example 2</p>
      <p>Input</p>
      <p>25 30 35 20 90 110 45 70 80 12 30 35 85</p>
      <p>Output</p>
      <p>335</p>
      <p>Explanation</p>
      <p>First Petrol vending machine will cater to vehicles taking - 80, 45, 35, 30, 25, 12, 85, 20 litres of petrol.</p>
      <p>Second machine will cater to vehicles taking - 90, 70, 35, 30, 110 litres of petrol. Since second machine will take more time, total time to fill petrol in all vehicles will be 335 seconds.</p>
      <p></p>
   </div>
</div>
<div >
   <p></p>
   <h2 id="problemname">Grooving Monkeys</h2>
   <div class="heading-tab active">
      
      <h3>Problem Description</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="problemdesc"></p>
      <p>N monkeys are invited to a party where they start dancing. They dance in a circular formation, very similar to a Gujarati Garba or a Drum Circle. The dance requires the monkeys to constantly change positions after every 1 second.</p>
      <p>The change of position is not random &amp; you, in the audience, observe a pattern. Monkeys are very disciplined &amp; follow a specific pattern while dancing. </p>
      <p>Consider N = 6, and an array monkeys = {3,6,5,4,1,2}.</p>
      <p>This array (1-indexed) is the dancing pattern. The value at monkeys[i], indicates the new of position of the monkey who is standing at the ith position.</p>
      <p>Given N &amp; the array monkeys[ ], find the time after which all monkeys are in the initial positions for the 1st time.</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hconst">Constraints</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="const"></p>
      <p>1&lt;=t&lt;=10 (test cases)</p>
      <p>1&lt;=N&lt;=10000 (Number of monkeys)</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hinput">Input Format</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="input"></p>
      <p>First line contains single integer t, denoting the number of test cases.</p>
      <p>Each test case is as follows -</p>
      <p>Integer N denoting the number of monkeys.</p>
      <p>Next line contains N integer denoting the dancing pattern array, monkeys[].</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="houtput">Output</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="output"></p>
      <p>t lines,</p>
      <p>Each line must contain a single integer T, where T is the minimum number of seconds after which all the monkeys are in their initial position.</p>
      <p></p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="htestcase">Timeout</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p>1</p>
   </div>
   <div class="heading-tab active">
      
      <h3 id="hexplanation">Explanation</h3>
   </div>
   <div class="content-tab" style="opacity: 1;">
      <p id="explanation"></p>
      <p>Example 1</p>
      <p>Input</p>
      <p>1</p>
      <p>6</p>
      <p>3 6 5 4 1 2</p>
      <p>Output</p>
      <p>6</p>
      <p>Explanation</p>
      <p>Consider N = 6, and an array monkeys = {3,6,5,4,1,2}.</p>
      <p>Suppose monkeys are a,b,c,d,e,f, &amp; Initial position (at t = 0) -&gt; a,b,c,d,e,f</p>
      <p> <a name="__DdeLink__157_3637044758"></a>At t = 1 -&gt; e,f,a,d,c,b</p>
      <p>a will move to 3rd position, b will move to 6th position, c will move to 5th position, d will move to 4th position, e will move to 1st position and f will move to 2nd position. Thus from a,b,c,d,e,f at t =0, we get e,f,a,d,c,b at t =1. Recursively applying same transpositions, we get following positions for different values of t.</p>
      <p>At t = 2 -&gt; c,b,e,d,a,f</p>
      <p>At t = 3 -&gt; a,f,c,d,e,b</p>
      <p>At t = 4 -&gt; e,b,a,d,c,f</p>
      <p>At t = 5 -&gt; c,f,e,d,a,b</p>
      <p>At t = 6 -&gt; a,b,c,d,e,f</p>
      <p></p>
      <p>Since at t = 6, we got the original position, therefore the answer is 6.</p>
      <p></p>
   </div>
</div>
<h3>Soln.</h3>
{% highlight python %}
T = int(input())
def checkbr(arr,arr2):
    temp = list(arr)
    for i in range(0,len(arr)):
        temp[i]=arr[arr2[i]-1]
    arr=list(temp)
    if sorted(arr) != arr:
        return checkbr(arr,arr2)+1
    else:
        return 1
while(T>0):
    T = T-1
    n = int(input())
    arr = [int(x) for x in input().split()]
    print(checkbr(list(sorted(arr)),list(arr)))

{% endhighlight %}


<div >
<p></p>
<h2 id="problemname">Death Battle</h2>
<h3>Problem Description</h3>
<p id="problemdesc"></p>
<p>In a crossover fantasy universe, Houin Kyoma is up in a battle against a powerful monster Nomu that can kill him in a single blow. However being a brilliant scientist Kyoma found a way to pause time for exactly M seconds. Each second, Kyoma attacks Nomu with certain power, which will reduce his health points by that exact power. Initially Nomu has H Health Points. Nomu dies when his Health Points reach 0. Normally Kyoma performs Normal Attack with power A. Besides from Kyoma"s brilliance, luck plays a major role in events of this universe. Kyoma"s Luck L is defined as probability of performing a super attack. A super attack increases power of Normal Attack by C. Given this information calculate and print the probability that Kyoma kills Nomu and survives. If Kyoma dies print "RIP".</p>
<p></p>
<h3 id="hconst">Constraints</h3>
<p id="const"></p>
<p>0 &lt; T &lt;= 50</p>
<p>1 &lt;= A, H, C, L1, L2 &lt;= 1000</p>
<p>1 &lt;= M &lt;= 20.</p>
<p>L1&lt;=L2</p>
<p></p>
<h3 id="hinput">Input Format</h3>
<p id="input"></p>
<p>First line is integer T denoting number of test cases.</p>
<p>Each test case consist of single line with space separated numbers A H L1 L2 M C. Where luck L is defined as L1/L2. Other numbers are, as described above.</p>
<p></p>
<h3 id="houtput">Output</h3>
<p id="output"></p>
<p>Print probability that Kyoma kills Nomu in form P1/P2 where P1&lt;=P2 and gcd(P1,P2)=1. If impossible, print "RIP" without quotes.</p>
<p></p>
<!--
   <h3 id="hexample">Examples</h3>
   <p id="example"></p>
   -->
<h3 id="htestcase">Timeout</h3>
<p>1</p>
<h3 id="hexplanation">Explanation</h3>
<p id="explanation"></p>
<p>Example 1</p>
<p>Input</p>
<p>2</p>
<p>10 33 7 10 3 2</p>
<p>10 999 7 10 3 2</p>
<p>Output</p>
<p class="body_Text">98/125</p>
<p class="body_Text">RIP</p>
<p></p>