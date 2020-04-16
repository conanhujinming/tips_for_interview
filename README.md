# tips_for_interview
Some of my thoughts about interview. 我的一些面试心得。中文版请点[这里](https://github.com/conanhujinming/tips_for_interview/blob/master/README-zh_CN.md) 。

I had some interviews this year in China for summer intern and full time job. This is just a collection of my thoughts about interview. 

I have now interviewed with several first-tier companies from China (such as Alibaba) and several global companies (such as Google), with only one rejection letter. After a period of interview preparation and several interview experiences, I summed up some personal experiences for reference only.

## Claim

All interview skills and tips are based on a solid foundation: the interviewee is already qualified enough. In 2018, I worked as an intern at a startup company, and I interviewed several candidates during the autumn. As far as I am concerned, if the interviewee is not qualified enough, it is not quite meaningful to learn these tips or tricks: an experienced interviewer can easily ask an interviewee some follow-up questions to check it. Interview skills and experience are meaningful, but **learning these skills can only help a qualified interviewee, instead of an unqualified one, to exert their strength to a greater extent**. **There is no shortcut for learning: nothing replaces hard work.** I hope that every interviewee can understand this truth as soon as possible.

On the other hand, there are exactly some students suffering from the lack of interview skills: they are quite qualified, but for some reasons they do not perform well in the interview. In fact, different companies have different interview cultures. For example, Google's interviewer hopes that the interviewee can become a colleague who is willing to work together. The interviewer from ByteDance may hope that the interviewee has a solid foundation in math, algorithm, coding, and engineering. Such a person is more likely to become a "person who can solve problems." However, as an interview candidate, we don't really need to address the culture of each company. There should be some common points in the interview. In my opinion, the key to the interview is that the interviewee should realize that this is not only a test, **but also a conversation that is full of communication and communication.** I hope that every interviewee can understand this truth as soon as possible.

In addition to the two most important points mentioned above, there are some other relatively common interview skills and tips for interviews. This article is intended to summarize some of the general interview skills and tips for such students.

## Programming Part

During the interview process, the interviewer often gives several algorithm problems, requiring the interviewee to provide ideas or write down the code. In most companies' interviews, the performance of this part is very important, and for some global companies, the performance of this part is decisive (even the only important one). For the preparation of this part, the first to recommend is websites like [LeetCode](https://leetcode.com/problemset/algorithms/). Here are some points that may be critical in an interview.

### A Very Simple Example

Here is a very simple question. The following tips will be illustrated with this question. The problem is to calculate the height of a binary tree. A simple implementation is as follows:

```
int getHeightOfBinaryTree(TreeNode* root) {
    if (!root) return 0;
    int left_height = getHeightOfBinaryTree(root->left);
    int right_height = getHeightOfBinaryTree(root->right);
    return max(left_height, right_height) + 1;
}
```

### Practice Whiteboard Programming

The programming part of the interview is often whiteboard programming: the interviewer either asks the interviewee to write code in a place such as Google Doc, or simply asks to write code on a white paper. In this case, the experience of coding is completely different from the experience of using IDE in daily life. Take Google Doc as an example. Many people (such as me) can hardly write code that can be compiled at first, let alone write bug-free code. On the other hand, without the IDE, the difficulty of debugging will be greatly increased. The difficulty of writing code on white paper goes even further. The method of adapting to whiteboard programming is also very simple, and only a sufficient amount of practice is required.

### Ask Clarification Questions

It is extremely important to ask clarification questions. If you don't understand the problem clearly, you should immediately ask some questions that will help you understand. For example: What is the range of data? What is the size range of this array? Can you give an example? If the input is this, what the output should be, and so on. One of the questions that can be asked in this simple question is what is the height of the binary tree (as far as I know, the definition of height is not the same for all textbooks)?

Many interviewers deliberately throw a vague problem firstly during the interview. In fact, they want the interviewee to be able to understand the problem after some inquiry. In this process, the interviewee can demonstrate his or her **analytical skills and communication skills**. The importance of the former can be found in the first chapter of Programming Pearls: careful analysis of a small problem can sometimes yield tremendous practical benefits. The importance of the latter is that the communication process is very similar to the process in which the interviewer discusses problems with colleagues after he or she joins the company. Obviously, an interviewee who is not able to communicate easily can hardly be a good colleague.

If there is no clarification question, what may happen? In the worst case, the interviewee may spend a lot of time solving a completely wrong question, and he or she will fail naturally. Or more luckily, he or she meets a nice interviewer and gives some tips to tell the interviewee that he or she is in the wrong direction, but this will not only waste a lot of precious interview time, but also reduce the interviewer's evaluation of the interviewee. When I was in a interview with Google, the interviewer gave me a question that sounds difficult and needs to be solved using dynamic programming. The interviewer gave me such a hard problem just at the beginning of the interview, which was too unfriendly for me! So I asked, "What is the range of the data?" The interviewer told me that the range of the array is an integer from 0-10. In this case, the problem becomes a greedy problem that can be solved with only 6 lines of code. If I didn't ask this question, the difficulty of the interview obviously increased greatly.

### Confirm the Function Signature with the Interviewer

After clarifing the problem, I think it is reasonable to confirm the function signature with the interviewer, that is, what are the inputs, what are the outputs, and so on. The cost of this step is very low, and it is very important. First, this tells the interviewer that you value the design of the function signature, which is valuable in practical applications. Second, this can further help you confirm that you understand the meaning of the question. A reasonable function signature might be similar to the function signature in the LeetCode problems. The signature in the above code is a reasonable signature.

### Confirm the Solving Idea with the Interviewer

After you have an idea, be sure to check with the interviewer if this idea is reasonable. You can explain to the interviewer why your ideas are reasonable and the interviewer may discuss some of the key points with you. There are several advantages with doing this. First, in the process of presentation, your thinking will become clearer (the interviewer acts as a little yellow duck). Second, it also shows that you value communication. Third, and perhaps most importantly, if your thinking is not correct, nice interviewers will prompt you even to point out of the error, so that you will at least not waste too much time on a wrong idea. **Don't write the code directly after getting an idea without confirming with the interviewer.** In particular, if your thinking has any assumptions about the data, or if you need to **modify the input data**, it is reasonable to confirm with the interviewer.

If you think that this problem is similar with a classic problem, or you can use a classic algorithm to solve it; then point it out. For example, calculating the height of a binary tree is actually a post-order traversal. You can point it out directly.

### Confirm Edge/Corner Case

Be sure to think about the edge cases of the code before you start writing code or when you are writing code. Some most typical edge cases can be: Will the data overflow? Is the pointer likely to be NULL? Is the linked list acyclic? Will the size of the array be zero? Will the inputs be completely incompatible with the requirements of the question? In the simple example, the corner case is that the height should be 0 when the root pointer is a null pointer. When you are aware of the existence of corner cases, you can ask the interviewer how to deal with it, or tell the interviewer directly what handling you think is reasonable. The handling of edge cases is also extremely important when developing software. Neglecting an edge case can have a great impact on program robustness, which may directly cause huge economic losses or even casualties.

### Use Highly Readable Variable Names and Function Names in Your Code

When writing code, try to use readable function names and variable names. For example, to calculate the depth of a binary tree, the function signature can be `int getHeightOfBinaryTree(TreeNode* root) `and the input is called `root` (not `node`). The variable name of the height of the left subtree can be called `left_height`. And so on. The main purpose of this operation is to let the interviewer see your good coding habits.

### Keep Communicating with the Interviewer When Writing Code

When implementing the algorithm, it is necessary to avoid writing without communicating with the interviewer. In fact, when writing some key codes, you can tell the interviewer which part you are implementing. In the previous example, you can tell the interviewer that `int left_height = getHeightOfBinaryTree(root->left) `is calculating the height of the left subtree (good function names and variable names actually make this line self-explanatory) `int root_height= max(left_height, right_height) + 1` calculates the height of the current root node based on the heights of the left and right subtrees.

Of course, in this simple example, communication may not seem so important, but it can be very important when dealing with much more complex problems. For example, the follow-up of the example is to implement the same function without recursion, or further, use a constant space to achieve the same function. In such a problem (the code can be as long as dozens of lines), communication is crucial. You need to communicate with the interviewer to ensure that he/she understands your thoughts and status, and you also need to communicate to clear your thoughts. Such kind of communication when writing code is also a very important ability after you join the company.

### Test with a Simple Case After Writing the Code

After you have finished writing the code, don't be rush to tell the interviewer that you have finished it. You'd better run one/several simple test cases manually. Note that the process of running this test case should be seen and easily understood by the interviewer, which often requires some practice. For example, the way I run the test case on Google Doc is to write the current values of the intermediate variables on the screen, and use the cursor to tell the interviewer which line of code the program is running now, what is the current value of each variable, etc. There are many benefits to active testing. First, this tells the interviewer that you value testing, and testing is very, very important in actual production. Second, a simple example can often find a lot of small errors like typo. Third, if your sample is good, you can even use this example to find bugs in the program and correct it. This is always better than the interviewer finds and tells you that there are bugs in the program. When testing, you can also confirm that your program handles boundary data very well.

When I was in an interview for a global company, the habit of actively testing gave me a big reward. In the first place, I wrote a program that was not very complicated (about 20 lines), but because of emotional stress, the program contained a relatively hidden bug. After I finished, I ran a simple example as usual, which took me about 3 minutes, but let me noticed the bug. I quickly fixed this bug. When I got to the "Do you have any question to ask" part of the interview, I asked the interviewer what is the best part of my interview. He told me: "You found your bug with a small test case. In fact, I noticed the bug as you writing the code. I was hesitant to remind you. Then you started testing and found the bug." The result of this interview was that I received the notice of pass about half an hour after the interview.

### Give the Complexity of the Algorithm

### Discuss the Trade-Off

## Computer Basic Knowledge Part

### Capture the Point of Questions

### Talk about Your Own Insight

### Explain with Your Own Experience

### Neither Talk Too Much Nor Too Litter 



## Project Part

### Briefly Introduce the Project Background

### Introducing the Project's Approach

### Point Out the Difficulties And Solutions in the Project



## Paper Part

### Briefly Introduce the Background of Your Research

### Introduce Your Paper Like Giving a Talk
