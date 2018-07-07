---
categories: jekyll update
date: "2016-07-10T00:00:00Z"
title: Scope Review
---

Today I was reviewing the concept of scope  in Javascript, and thanks to the workshop at <a href="http://nodeschool.io/">nodeschool</a>, I believe I have a better understanding of how scope works.

Suppose we are given the following functions:

{{< highlight javascript >}}
  function egg() {
    var prep = "scrambled";
    function bacon() {
      var amount = 4;
      }
    }
  {{< / highlight >}}

In this example, the function egg only has access to the variable prep, but the function bacon has access to both variables (i.e. amount and prep). This isn't too confusing and one easy metaphor to remember this concept can be found on LearnCode.academy's youtube video on <a href= "https://www.youtube.com/watch?v=SBwoFkRjZvE&list=PLoYCgNOIyGABI011EYc-avPOsk1YsMUe_&index=">scopes</a>. One of the examples given in the video is a metaphor that explains the relationship of scope as similar to that of a parent's cookies and her child's cookies. The child (in this case the nested function bacon) has access to her parent's cookies , but the child will not in turn let her parent take her own cookies. This nesting of functions (or scope chain) can extend even further and so can the previous metaphor.

Suppose we extend the example in the following way:


{{< highlight javascript >}}   
     function egg() {
     function bacon() {
       }
       function toast() {
         function butter() {
         }
       }
     }
  {{< / highlight >}}


The function bacon now has access to the function egg but the function toast does not have access to the function bacon. The function butter has access to the function toast and it also has access to the outermost function (egg).

If we wish to extend the previous metaphor to this example, we could treat the functions bacon and toast as siblings and the function butter as the child of the function butter. The children (bacon and toast) both have access to their parent's cookies, but they do not have access to each others cookies (how many kids willingly share cookies anyway). Following the same logic (or chain), we can say that the grandchild (butter) has access to her parent's (toast) cookies and also her grandparent's cookies (egg). In other words, the chain extends from the grandchild to the grandmother but not vice versa.

I hope you found this explanation somewhat helpful (and not too silly). In my next post, I will go over a concept related to scopes: closures. If you have any questions or comments, please tweet to me <a href="https://twitter.com/SethLachman">@SethLachman</a>.
