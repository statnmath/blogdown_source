---
title: Building a Static Blog with Blogdown, Hugo and GitHub
author: Jeeyoung Lee
date: '2018-01-31'
slug: building-a-static-blog-with-blogdown-hugo-and-github-rmd
categories: ["R"]
tags: ["R", "Blogdown", "Hugo", "GitHub"]
---

When I was an undergraduate student at University of Toronto, I created a [StatnMath google blog](http://statnmath.blogspot.ca/), simply because I wanted to review what I had learned at school. Actually I have one more, Korean version hosted by Tistory, [StatnMath Tistory](http://statnmath.tistory.com/). Sooner or later I realized that sharing what I learned is good for both readers and me. Thanks to amazing people sharing their knowledge and expertise, finally I got this beautiful template, [link](https://github.com/kakawait/hugo-tranquilpeak-theme) for free. I want to be part of them. As I am inspired by amazing people, I hope I can be a person who inspire others, especially newbies. So there is no reason to stop me from blogging. 


When I was a student, I did not know what do do and where to start. After I finished schools, I feel like NOW I am able to start my own journey in Data Science. I am really happy there are many things to learn, and more exciting thing is I am ready to learn. What I left is to find a place I can settle down, which supports markdown syntax. I have been searching open-source static site generators, instead of keeping the Google blog. And I am here. [`Hugo`](https://gohugo.io/), [`Blogdown`](https://bookdown.org/yihui/blogdown/) and [`GitHub`](https://github.com/).!! What a perfect combination to create this blog. Do you want to build a static blog hosted by GitHub, like this blog? Let's get started. Time is flying! <br/>



### <span style="color:#3498DB"> **The Basic Check Lists Before You Begin!** </span> <br/>
If you are OK with these questions, you are good to move on the next step. If you are not, you are still good to move on, meaning you have just a little more things you need to dig into. 


#### <span style="color:#666699"> **1.Hugo** </span>
[`Hugo`](https://gohugo.io/) is a open-source static website generators. It means you need to install Hugo in your computer first. It currently provides macOS, Windows, Linux and FreeBSD. Check out the installation in [here](https://gohugo.io/getting-started/installing/). As I am a Mac user, so I had to install [Brew](https://brew.sh/) first before I install Hugo. Brew can install the stuff which Apple didn't.  


#### <span style="color:#666699"> **2.Blogdown** </span> 
[Blogdown](https://bookdown.org/yihui/blogdown/) is an R package. The link provides the short book, authors by [Yihui Xie](https://bookdown.org/yihui/blogdown/yihui-xie.html), [Amber Thomas](https://bookdown.org/yihui/blogdown/amber-thomas.html) and [Alison Presmanes Hill](https://bookdown.org/yihui/blogdown/alison-presmanes-hill.html). Thanks to those wonderful people, we can create websites using R markdown and Hugo!!


#### <span style="color:#666699">**3.Deploy through where? GitHub vs Netlify**</span>
If you have two above, Hugo and Blogdown, then you can have your own website in your local computer. You need to deploy this website through using either [GitHub](https://github.com/) or [Netlify](https://www.netlify.com/) to everyone can see it. At the first time, I tired Netlify then moved into GitHub. No particular reasons. As I am a newbie, it is hard me to provide suggestions which one is better. As I am going to review with GitHub, in order not to bias toward which sites, here the links how to use Netlify are. 

  + Step-by-Step Guide : [link](https://www.netlify.com/blog/2016/09/29/a-step-by-step-guide-deploying-on-netlify/) <br/>
  + Comparison between GitHub and Netlify written by Netlify : [link](https://www.netlify.com/github-pages-vs-netlify/) <br/>
  + Move from GitHub to Netlify : [Rebecca Barter blog](http://www.rebeccabarter.com/blog/2017-06-29-website/) <br/>




### <span style="color:#3498DB">**Hugo + Blogdown + GitHub**</span> <br/> 
If you decide to use GitHub, meaning your website address will be **username.github.io**. Then follow this procedure. Actually, there are sooooooo much detailed posting how to set up. I am not going to go over the same procedure, but rather than I will focus on the tips you cannot ignore otherwise you cannot get it. <br/> 

You have two options, *Again? Yes!! Life is full of choices.* <br/>

  + Two Repositories : [tclavelle.github.io](https://tclavelle.github.io/blog/blogdown_github/) <br/> 
  + Two Branches : [Amber Thomas blog](https://amber.rbind.io/blog/2016/12/19/creatingsite/) <br/>

Yes, my main job in here is to introduce wonderful websites and blog postings. I am using two repositories, and I followed whole procedures mentioned above blog. 

**Tip 1. REMOVE! DELETE!! `readme.md` file when creating site!**  
The posting above also mentioned to delete the `readme.md` file, and do not add anything else that folder in GitHub. I still don't get it why I missed that part and had hard time to figure it out. But again, after you create the repositories, you will have `readme.md` file, you need to make sure you remove file before you create website. 

**Tip 2. Always check the working directory**  
After I removed the `readme.md` file, I failed and failed to deploy website. I though hard which part I was missing, or which part I did not pay attention to. My problem was I did not fully focus to check which I was in the working directory. 

No reasons not to check the working directory, `getwe()` in R!! If you want to set the working directory, use `setwd("path")`. When using `new_site` in R, check the current working directory and make sure your working directory should be in **GitHub**. In the command below, **dir = 'blogdown_source'** can create the website under the `blogdown_source` folder. 

```
getwd()
setwd("path/GitHub/")

# Create new site in our recently cloned blogdown repository
new_site(dir = 'blogdown_source', 
         theme = 'kakawait/hugo-tranquilpeak-theme',
         format = 'toml')
```

The steps are well explained in [tclavelle.github.io](https://tclavelle.github.io/blog/blogdown_github/). Thanks for great posting again! 

**Tip 3. All good at the local computer, then how to push it?**
As I was(am) quite new to GitHub, so I didn't know the detailed steps to push all files into GitHub. 


```
$ git status
``` 
This commands tells you which files are changed. These files should be pushed into GitHub. 

```
$ git add .
``` 
Adds the files in your local repositories, then stages them for commit.  

```
$ git comit -m "First Commit"
``` 
Commits the tracked changes and prepares them to be pushed to a remote repository.

```
$ git remote add origin <remote repository URL> 
```
Now you add the URL for the remote repository where your local repository will be pushed. 

```
$git push origin master
```
Now you push the changes in your local repository to GitHub. As I have two repositories, so I did for each repository. For the detailed information, check this reference [link](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/). 



Enjoy happy blogging, writing and coding!! Also, please share your hard work!! 