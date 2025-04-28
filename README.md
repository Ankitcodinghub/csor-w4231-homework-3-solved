# csor-w4231-homework-3-solved
**TO GET THIS SOLUTION VISIT:** [CSOR-W4231 Homework 3 Solved](https://www.ankitcodinghub.com/product/csor-w4231-brief-solutions-to-hw3-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;120416&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSOR-W4231  Homework 3 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
1. Solution to problem 1

Run Dijkstra’s algorithm twice, once from s and once from t to compute shortest s-v paths and shortest t-v paths in G. Store the computed distances in arrays ds and dt, respectively.

Then iterate over all pairs of cities in the list E0 to find the pair (x,y) that incurs the minimum s-t distance. For a fixed pair (x,y), the latter is given by

min{ds(x) + `(x,y) + dt(y),ds(y) + `(x,y) + dt(x)}

Running time: the total running time is Dijkstra’s plus O(|E0|). Depending on |E0|, we can decide which implementation to use.

2. Solution to problem 2

Suppose n boxes arrive in the order b1,b2,…,bn and weights w1,w2,…,wn.

Greedy algorithm: Pack the boxes in the order they arrive; when the next box does not fit, send the truck on its way.

Correctness: We will show that the greedy algorithm “always stays ahead” of any other solution (similarly to the proof of Dijkstra’s algorithm). To do so, it suffices to prove the following claim (why?): If the greedy algorithm loaded the first m trucks with p boxes, then no other algorithm can fit more boxes in the first m trucks. The proof of the claim is by a straightforward induction on m (left as an exercise).

3. Solution to problem 3

Let

OPT(n) = min total cost to place copies in n libraries, given that the book is placed in Ln.

Suppose we knew that in the optimal solution, Li is the last library before Ln that contains the book, where 0 ≤ i ≤ n−1. Then a request at library Lk with i+1 ≤ k ≤ n−1 will incur a delay of n − k. So the total user delay associated with libraries Li+1,…,Ln−1 is

Then the minimum total cost is given by the following recurrence:

Since we don’t know the index i a priori, we will look for the i that minimizes the above expression over all possible values for i. Therefore the recurrence is

• We want OPT(n).

• Boundary conditions: OPT(0) = 0.

Running time: O(n2); there are n subproblems, each requiring O(n) time to fill in.

• Space: O(n); maintain an array M such that M[i] = OPT(i).

4. Solution to problem 4

Let OPT(n,m) be the distance between a1,…,an and b1,…,bm.

Then either an is not mapped to bm in the optimal solution or it is. Hence

• OPT(n,m) = OPT(n,m − 1), if an is not mapped to bm; or

• OPT(n,m) = |an − bm| + OPT(n − 1,m), if an is mapped to bm

Therefore

OPT(n,m) = min{OPT(n,m − 1),|an − bm| + OPT(n − 1,m)}

• We want OPT(n,m).

• Boundary conditions: OPT(i,1) = Pik=1 |ak − b1| for i ≥ 0, OPT(0,j) = 0 for j ≥ 1

• Time: O(nm) (there are nm subproblems, each requires O(1) time)

• Space: O(nm) (DP table M[0..n,1..m]; (space can be improved))

• Order to fill in table: column-by-column.

5. Solution to problem 5

We want to cut a string s1s2 …sn of length n into m+1 pieces, where we know the positions of the m cuts in advance: the cuts will be made at positions p1,…,pm with 0 &lt; p1 ≤ p2 ≤ … ≤ pm &lt; n. If we let p0 = 0 and pm+1 = n, then s1 …sn = sp0+1 …spm+1. Let

OPT(0,m+1) = min cost to cut the entire string sp0+1 …spm+1 at fixed positions p1,…,pm.

More generally, for 0 ≤ i &lt; j ≤ m + 1, let

OPT(i,j) = min cost to cut the string spi+1 …spj at fixed positions pi+1,…,pj−1

Consider the overall optimal solution: the string consists of two pieces since every time we cut the string into two parts. Suppose we knew that the string was first cut at position pk∗ in the optimal solution. Then

OPT(0,m + 1) = OPT(0,k∗) + OPT(k∗,m + 1) + (n − 0)

Since we do not know the index k∗, and we want to minimize the overall cost, we have

OPT(0,m + 1) = min {OPT(0,k) + OPT(k,m + 1) + (pm+1 − p0)}

0&lt;k&lt;m+1

For subproblem OPT(i,j), the recurrence becomes OPT(i,j) = min {OPT(i,k) + OPT(k,j) + (pj − pi)}

i&lt;k&lt;j

• Boundary conditions: OPT(i,i + 1) = 0;

• Time: O(m3); there are O(m2) subproblems, each requiring O(m) time

• Space: O(m2); need fill in the upper half of an (m + 1) × (m + 1) matrix; each entry in the matrix corresponds to a subproblem OPT(i,j) for 0 ≤ i &lt; j ≤ m + 1.

• Fill in the matrix diagonal by diagonal.

Solutions to Recommended Exercises

1. Solution to recommended exercise 1

A greedy algorithm that sorts the customers by increasing order of service times and services them in this order is correct.

Running time: O(nlogn).

Correctness: by an exchange argument; for any ordering of the customers, let cj denote the j-th customer in the ordering. Then the total time is given by

n i−1 n

T = XXtcj = X(n − i)tci i=1 j=1 i=1

One can observe that if tci &gt; tcj for i &lt; j, then swapping the positions of the two customers gives a better ordering. Then the ordering tc1 ≤ tc2 ≤ … ≤ tcn provided by the greedy algorithm above is optimal.

2. Solution to recommended exercise 3

Let OPT(i) be the maximum revenue achievable up to week i.

OPT(i) = max{OPT(i − 1) + `i,OPT(i − 2) + hi}

• We want OPT(n).

• Boundary conditions: OPT(1) = max{`1,h1}.

• Time complexity: O(n); there are n subproblems, each requiring O(1) time to fill in.

• Space: maintain DP array M of size n (can be improved)

3. Solution to recommended exercise 4

Let OPT(i) = length of longest monotonically increasing subsequence ending with ai

Since the subsequence includes ai, we have

OPT(i) = 1 + max OPT(j)

1≤j&lt;i aj&lt;ai

• We want max OPT(i).

1≤i≤n

• Boundary conditions: OPT(0) = 0.

• Time complexity: O(n2); there are n subproblems to fill in, each requires O(n) time in a bottom-up fashion; return their maximum in O(n) time.

• Space: O(n)

4. Solution to recommended exercise 5

Let OPT(j) = max sum of subarray ending at j. Then

n o

OPT(n) = max OPT(n − 1) + A[n],0

and

n o

OPT(j) = max OPT(j − 1) + A[j],0 .

Boundary condition: OPT(0) = 0.

• We want the maximum length L of a contiguous subarray of A given by L = max OPT(j)

1≤j≤n

• There are n + 1 subproblems, each requiring O(1) time in a bottom-up computation. Thus computing L takes O(n) time.

• Space: O(n)

5. Solution to recommended exercise 6

Let OPT(i,j) = longest common substring of x,y terminating at xi,yj. Then

( ) = 1) , if xi = yj 0 , otherwise

• We want the subproblem of maximum value.

• Boundary conditions: OPT(i,0) = 0 for all i, OPT(0,j) = 0 for all j.

• We can construct an (m+1)×(n+1) DP table to compute each OPT(i,j). The longest common substring of x,y is given by the max entry in the table.

• Running time: O(mn). There are Θ(mn) subproblems, each requires O(1) time when computed in a bottom-up fashion. Returning the subproblem of maximum value takes O(mn) time.

• Space: O(mn) (can be improved)

• Fill in the DP table row-by-row.

Solutions to EdStem Further Practice Problems

1. Solution to EdStem Further Practice Problem 1

(a) Let OPT(W) be the max value we can get by using total weight at most W. The last item in an optimal solution achieving value OPT(W) can be any of the input items, as long as its weight doesn’t exceed W. Hence OPT(W) = max {OPT(W − wi)) + vi, if wi ≤ W}

1≤i≤n

More generally,

OPT(w) = max {OPT(w − wi)) + vi, if wi ≤ w}

1≤i≤n

• We want OPT(W).

• Boundary conditions: OPT(w) = 0 for w = 0.

• Time: O(nW) (there are O(W) subproblems, each requiring O(n) time)

• Space: O(W)

(b) Let OPT(n,W) be the max value we can get by selecting any subset of the first n items with total weight at most W. Let S∗ be an optimal solution. Then the n-th item either appears in S∗ or it doesn’t; note that if wn &gt; W, then it cannot appear in S∗. Hence



n o

 max OPT(n − 1,W),OPT(n − 1,W − wn) + vn , if wn ≤ W OPT(n,W) =

 OPT(n − 1,W) , otherwise

More generally, for 0 ≤ i ≤ n, 0 ≤ w ≤ W, we have



n o

 max OPT(i − 1,w),OPT(i − 1,w − wi) + vi , if wi ≤ w OPT(i,w) =

 OPT(i − 1,w) , otherwise

• We want OPT(n,W).

• Boundary conditions: OPT(0,w) = 0 for 0 ≤ w ≤ W, OPT(i,0) = 0 for 1 ≤ i ≤ n.

• Time: O(nW) (there are O(nW) subproblems, each requiring O(1) time)

• Space: O(nW) // can be improved if we only care about optimal value— how?

• Order to fill in table: row by row

2. Solution to EdStem Further Practice Problem 2

Let OPT(i,j,k) be the length of the longest common subsequence of the prefixes of X,Y,Z ending at i,j,k respectively. Then

(

1 + OPT(i − 1,j − 1,k − 1) , if xi = yj = zk

OPT(i,j,k) = max{OPT(i − 1,j,k),OPT(i,j − 1,k),OPT(i,j,k − 1)} , otherwise

• We want OPT(m,n,p).

Boundary conditions: OPT(0,j,k) = 0 for all j,k; OPT(i,0,k) = 0 for all i,k; OPT(i,j,0) = 0 for all i,j.

• Time: O(n3), for m,p = O(n); O(n3) subproblems, O(1) time to fill in in a bottom-up fashion

• Space: O(n3), for m,p = O(n) // can be improved.

• Fill in 3D matrix by increasing i, j, k in three nested for loops.

The reconstruction algorithm is recursive and linear in n for m,p = O(n).
