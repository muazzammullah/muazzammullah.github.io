---
title: How I solved Codingbat's makeBricks problem
date: 2019-02-18 16:20:26 Z
---

### Make if statements for what will not result in the goal

So I stumbled upon a well known problem on codingbat called makeBricks.It goes like this

"We want to make a row of bricks that is **goal** inches long. We have a number of small bricks (1 inch each) and big bricks (5 inches each). Return true if it is possible to make the goal by choosing from the given bricks. This is a little harder than it looks and can be done without any loops"

Now I did spend the time and effort to use loops,but after i saw how ineffiecient the looping approach is i just deleted everything and started again.

After scratching about on a piece of paper I started to check what  [clues codingbat themselves give you](https://codingbat.com/doc/practice/makebricks-solution-code.html "fff").One sentence stuck with me "Think about cases where the goal is **not** possible .. easier"

After brainstorming on a small clip-it note sized paper I went about coding the solution.

This is what i came up with.

\-If all the small blocks of length 1 and big blocks of length 5 put together cannot make up the goal,you can already assume false.

\-if you take the remainder after dividing the goal by the length of the big blogs ,so 5,if you have less small blocks than the remainder then obviously would not be able to make the goal length.

\-Other than that every other test case instance should be true.

So,I was actually willing to put the code out here on this blog but then I thought,"hey what if you just want some pointers and dont want to see the solution,so that you can do this yourself".