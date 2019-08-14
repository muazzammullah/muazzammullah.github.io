---
title: How I solved codingbats makeChocolate problem
date: 2019-02-18 16:58:05 Z
---

### This problem is slightly different than makeBricks.

Instead of returning whether making the goal length is possible or not like in makeBricks.We instead have to return exactly the number of small bricks to use to get to the goal length.

"We want make a package of goal kilos of chocolate. We have small bars (1 kilo each) and big bars (5 kilos each). Return the number of small bars to use, assuming we always use big bars before small bars. Return -1 if it can't be done."

After brainstorming on a small clip-it note sized paper(yet again) I went about coding the solution.

This is what i came up with for this problem

Case 1 : If all the small blocks of length 1 and big blocks of length 5 put together cannot make up the goal,you can already return -1

Case 2 : if you take the remainder after dividing the goal by the length of the big blogs ,so 5,if you have less small blocks than the remainder then obviously would not be able to make the goal length and there return -1

\-This last case is where makeBricks differs from makeChocolate

Case 3 : So,i found that if the goal is less than 10,then you could just mod the goal by 5 and that result would be the number of small blocks  to use.

\-After that we could actually just return goal-(big*5).This is because it is not necessary to make another if statement because the Case above is false.

So for this one i decided that putting the code down would be better

{% highlight python %} 

def make_chocolate(small, big, goal):

  if(small+big*5<goal):

    return -1

  elif small<goal%5:

    return -1

  else:

    if(goal<10):

      return goal%5

    return goal-(big*5)

{% endhighlight %} 