---
keywords: fastai
title: Working with git branches and Github repositories
toc: true
badges: true
categories: [Git]
permalink: /working-with-git-branches-and-github/
description: 
nb_path: _notebooks/2022-08-12-working-with-git-branches-and-github.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-08-12-working-with-git-branches-and-github.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Some-Basic-Commands-on-Getting-Updates-from-a-Remote-Repo">Some Basic Commands on Getting Updates from a Remote Repo<a class="anchor-link" href="#Some-Basic-Commands-on-Getting-Updates-from-a-Remote-Repo"> </a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<ul>
<li><a href="https://docs.github.com/en/get-started/using-git/getting-changes-from-a-remote-repository">Getting changes from a remote repository</a><ul>
<li><code>git fetch</code> : retrieve new work without merging those changes into your own branches, ex: <code>git fetch remotename</code></li>
<li><code>git merge</code>: combines your local changes with updates in the repo, ex: <code>git merge remotename/branchname</code></li>
<li><code>git pull</code>: a shortcut for completing both <code>git fetch</code> and <code>git merge</code></li>
</ul>
</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<ul>
<li>For more details: check <a href="https://docs.github.com/en/get-started/quickstart/github-flow">git flow</a></li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="What-you'll-need">What you'll need<a class="anchor-link" href="#What-you'll-need"> </a></h2><ul>
<li>a <a href="(https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token">Person Access Token</a>)</li>
<li>a link to your empty <a href="https://docs.github.com/en/get-started/quickstart/create-a-repo">github repository</a></li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><br></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Clone-an-empty-repository-from-github,-create-a-main-branch,-and-then-push-it-to-remote">Clone an empty repository from github, create a main branch, and then push it to remote<a class="anchor-link" href="#Clone-an-empty-repository-from-github,-create-a-main-branch,-and-then-push-it-to-remote"> </a></h2><p>Clone an empty repository from github</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="err">!</span><span class="n">git</span> <span class="n">clone</span> <span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">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</span><span class="nd">@github</span><span class="o">.</span><span class="n">com</span><span class="o">/</span><span class="n">intodeeplearning</span><span class="o">/</span><span class="n">test</span><span class="o">.</span><span class="n">git</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Cloning into &#39;test&#39;...
warning: You appear to have cloned an empty repository.
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Set identity</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">git</span> <span class="n">status</span>
<span class="n">git</span> <span class="n">config</span> <span class="n">user</span><span class="o">.</span><span class="n">email</span> <span class="s2">&quot;intodeeplearning@gmail.com&quot;</span>
<span class="n">git</span> <span class="n">config</span> <span class="n">user</span><span class="o">.</span><span class="n">name</span> <span class="s2">&quot;intodeeplearning&quot;</span>
<span class="c1">#git push -u origin test</span>

<span class="c1">#git fetch origin</span>
<span class="c1">#git checkout test</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>On branch master

No commits yet

nothing to commit (create/copy files and use &#34;git add&#34; to track)
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Create a main branch and push it to remote</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">echo</span> <span class="s1">&#39;#test&#39;</span> <span class="o">&gt;&gt;</span> <span class="n">README</span><span class="o">.</span><span class="n">md</span>
<span class="n">git</span> <span class="n">add</span> <span class="n">README</span><span class="o">.</span><span class="n">md</span>
<span class="n">git</span> <span class="n">commit</span> <span class="o">-</span><span class="n">m</span> <span class="s2">&quot;initial commit&quot;</span>
<span class="n">git</span> <span class="n">branch</span> <span class="o">-</span><span class="n">M</span> <span class="n">main</span>
<span class="n">git</span> <span class="n">push</span> <span class="o">-</span><span class="n">u</span> <span class="n">origin</span> <span class="n">main</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>[master (root-commit) 1643b7b] initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
Counting objects: 3, done.
Writing objects: 100% (3/3), 217 bytes | 217.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/intodeeplearning/test.git
 * [new branch]      main -&gt; main
Branch &#39;main&#39; set up to track remote branch &#39;main&#39; from &#39;origin&#39;.
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><br></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Create-a-new-branch-from-the-main-branch,-make-changes,-and-then-merge">Create a new branch from the main branch, make changes, and then merge<a class="anchor-link" href="#Create-a-new-branch-from-the-main-branch,-make-changes,-and-then-merge"> </a></h2><p>Clone a branch from github repo</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="err">!</span><span class="n">git</span> <span class="n">clone</span> <span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">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</span><span class="nd">@github</span><span class="o">.</span><span class="n">com</span><span class="o">/</span><span class="n">intodeeplearning</span><span class="o">/</span><span class="n">test</span><span class="o">.</span><span class="n">git</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Cloning into &#39;test&#39;...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), done.
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">git</span> <span class="n">status</span>
<span class="c1">#create a new branch</span>
<span class="n">git</span> <span class="n">checkout</span> <span class="o">-</span><span class="n">b</span> <span class="n">test2</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>On branch main
Your branch is up to date with &#39;origin/main&#39;.

nothing to commit, working tree clean
Switched to a new branch &#39;test2&#39;
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Create a new branch from main branch, and make a commit</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test</span>

<span class="n">git</span> <span class="n">config</span> <span class="n">user</span><span class="o">.</span><span class="n">email</span> <span class="s2">&quot;intodeeplearning@gmail.com&quot;</span>
<span class="n">git</span> <span class="n">config</span> <span class="n">user</span><span class="o">.</span><span class="n">name</span> <span class="s2">&quot;intodeeplearning&quot;</span>

<span class="n">echo</span> <span class="s1">&#39;#test2&#39;</span> <span class="o">&gt;&gt;</span> <span class="n">README2</span><span class="o">.</span><span class="n">md</span>
<span class="n">git</span> <span class="n">add</span> <span class="o">.</span> <span class="n">README2</span><span class="o">.</span><span class="n">md</span>
<span class="n">git</span> <span class="n">commit</span> <span class="o">-</span><span class="n">m</span> <span class="s1">&#39;add README2.md&#39;</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>[test2 bf43a76] add README2.md
 1 file changed, 1 insertion(+)
 create mode 100644 README2.md
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Push this newly created branch to remote</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">sh</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">git</span> <span class="n">push</span> <span class="o">-</span><span class="n">u</span> <span class="n">origin</span> <span class="n">test2</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Branch &#39;test2&#39; set up to track remote branch &#39;test2&#39; from &#39;origin&#39;.
</pre>
</div>
</div>

<div class="output_area">

<div class="output_subarea output_stream output_stderr output_text">
<pre>remote: 
remote: Create a pull request for &#39;test2&#39; on GitHub by visiting:        
remote:      https://github.com/intodeeplearning/test/pull/new/test2        
remote: 
To https://github.com/intodeeplearning/test.git
 * [new branch]      test2 -&gt; test2
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>You can either merge the main branch with test3 branch on github, or locally by:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">sh</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">git</span> <span class="n">checkout</span> <span class="n">main</span>
<span class="n">git</span> <span class="n">merge</span> <span class="n">test2</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Your branch is up to date with &#39;origin/main&#39;.
Updating 1643b7b..bf43a76
Fast-forward
 README2.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 README2.md
</pre>
</div>
</div>

<div class="output_area">

<div class="output_subarea output_stream output_stderr output_text">
<pre>Switched to branch &#39;main&#39;
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Delete a branch</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">sh</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">git</span> <span class="n">branch</span> <span class="o">-</span><span class="n">d</span> <span class="n">test2</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Deleted branch test2 (was bf43a76).
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><br></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Clone-a-branch-from-a-github-repo">Clone a branch from a github repo<a class="anchor-link" href="#Clone-a-branch-from-a-github-repo"> </a></h2>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="err">!</span><span class="n">git</span> <span class="n">clone</span> <span class="o">--</span><span class="n">branch</span> <span class="n">test2</span> <span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">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</span><span class="nd">@github</span><span class="o">.</span><span class="n">com</span><span class="o">/</span><span class="n">intodeeplearning</span><span class="o">/</span><span class="n">test</span><span class="o">.</span><span class="n">git</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Cloning into &#39;test&#39;...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), done.
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><br></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Fetch-a-remote-branch">Fetch a remote branch<a class="anchor-link" href="#Fetch-a-remote-branch"> </a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>List all the remote tracking branches</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">git</span> <span class="n">branch</span> <span class="o">-</span><span class="n">r</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>  <span class="ansi-red-fg">origin/HEAD</span> -&gt; origin/main
  <span class="ansi-red-fg">origin/main</span>
  <span class="ansi-red-fg">origin/test2</span>
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Fetch one remote branch</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">git</span> <span class="n">fetch</span> <span class="n">origin</span> <span class="n">main</span>

<span class="c1">#you can also fetch the all the branches by: git fetch origin</span>
<span class="n">git</span> <span class="n">checkout</span> <span class="n">main</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>From https://github.com/intodeeplearning/test
 * branch            main       -&gt; FETCH_HEAD
Branch &#39;main&#39; set up to track remote branch &#39;main&#39; from &#39;origin&#39;.
Switched to a new branch &#39;main&#39;
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test</span>
<span class="n">git</span> <span class="n">branch</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>* <span class="ansi-green-fg">main</span>
  test2
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><br></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Push-an-unrelated-branch-to-github-repo">Push an unrelated branch to github repo<a class="anchor-link" href="#Push-an-unrelated-branch-to-github-repo"> </a></h2>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">mkdir</span> <span class="n">test3</span> 
<span class="n">cd</span> <span class="n">test3</span>
<span class="n">echo</span> <span class="s1">&#39;#test3&#39;</span> <span class="o">&gt;&gt;</span> <span class="n">README3</span><span class="o">.</span><span class="n">md</span>
<span class="n">git</span> <span class="n">init</span>
<span class="n">git</span> <span class="n">config</span> <span class="n">user</span><span class="o">.</span><span class="n">email</span> <span class="s2">&quot;intodeeplearning@gmail.com&quot;</span>
<span class="n">git</span> <span class="n">config</span> <span class="n">user</span><span class="o">.</span><span class="n">name</span> <span class="s2">&quot;intodeeplearning&quot;</span>

<span class="n">git</span> <span class="n">add</span> <span class="o">.</span> <span class="n">README3</span><span class="o">.</span><span class="n">md</span>
<span class="n">git</span> <span class="n">commit</span> <span class="o">-</span><span class="n">m</span> <span class="s1">&#39;add README3.md&#39;</span>
<span class="n">git</span> <span class="n">branch</span> <span class="o">-</span><span class="n">M</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">remote</span> <span class="n">add</span> <span class="n">origin</span> <span class="n">https</span><span class="p">:</span><span class="o">//</span><span class="n">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</span><span class="nd">@github</span><span class="o">.</span><span class="n">com</span><span class="o">/</span><span class="n">intodeeplearning</span><span class="o">/</span><span class="n">test</span><span class="o">.</span><span class="n">git</span>
<span class="n">git</span> <span class="n">push</span> <span class="o">-</span><span class="n">u</span> <span class="n">origin</span> <span class="n">test3</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Initialized empty Git repository in /content/test3/.git/
[master (root-commit) 0ebfb4e] add README3.md
 1 file changed, 1 insertion(+)
 create mode 100644 README3.md
Counting objects: 3, done.
Writing objects: 100% (3/3), 226 bytes | 226.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
remote: 
remote: Create a pull request for &#39;test3&#39; on GitHub by visiting:
remote:      https://github.com/intodeeplearning/test/pull/new/test3
remote: 
To https://github.com/intodeeplearning/test.git
 * [new branch]      test3 -&gt; test3
Branch &#39;test3&#39; set up to track remote branch &#39;test3&#39; from &#39;origin&#39;.
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><br></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Merge-Two-Unrelated-Branches">Merge Two Unrelated Branches<a class="anchor-link" href="#Merge-Two-Unrelated-Branches"> </a></h3><p><a href="https://stackoverflow.com/questions/49243844/git-cannot-merge-unrelated-branches">ref</a></p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">status</span>
<span class="n">git</span> <span class="n">branch</span>

<span class="n">git</span> <span class="n">branch</span> <span class="o">-</span><span class="n">r</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>On branch test3
Your branch is up to date with &#39;origin/test3&#39;.

nothing to commit, working tree clean
* <span class="ansi-green-fg">test3</span>
  <span class="ansi-red-fg">origin/test3</span>
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">fetch</span> <span class="n">origin</span>
<span class="n">git</span> <span class="n">checkout</span> <span class="n">main</span>
<span class="n">git</span> <span class="n">checkout</span> <span class="o">-</span><span class="n">b</span> <span class="n">test3</span><span class="o">-</span><span class="mi">1</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), done.
From https://github.com/intodeeplearning/test
 * [new branch]      main       -&gt; origin/main
 * [new branch]      test2      -&gt; origin/test2
Branch &#39;main&#39; set up to track remote branch &#39;main&#39; from &#39;origin&#39;.
Switched to a new branch &#39;main&#39;
Switched to a new branch &#39;test3-1&#39;
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">log</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre><span class="ansi-yellow-fg">commit 1643b7be3c79e6002df550f0a457816c52c84c38</span><span class="ansi-yellow-fg"> (</span><span class="ansi-cyan-intense-fg ansi-bold">HEAD -&gt; </span><span class="ansi-green-intense-fg ansi-bold">test3-1</span><span class="ansi-yellow-fg">, </span><span class="ansi-red-intense-fg ansi-bold">origin/main</span><span class="ansi-yellow-fg">, </span><span class="ansi-green-intense-fg ansi-bold">main</span><span class="ansi-yellow-fg">)</span>
Author: intodeeplearning &lt;intodeeplearning@gmail.com&gt;
Date:   Fri Aug 12 15:42:04 2022 +0000

    initial commit
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><code>git cherry-pick test3</code> copies the commit from test3 to test3-1</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">cherry</span><span class="o">-</span><span class="n">pick</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">status</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>[test3-1 0c4713e] add README3.md
 Date: Fri Aug 12 15:42:08 2022 +0000
 1 file changed, 1 insertion(+)
 create mode 100644 README3.md
On branch test3-1
nothing to commit, working tree clean
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">checkout</span> <span class="n">main</span>
<span class="n">git</span> <span class="n">merge</span> <span class="n">test3</span><span class="o">-</span><span class="mi">1</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Switched to branch &#39;main&#39;
Your branch is up to date with &#39;origin/main&#39;.
Updating 1643b7b..0c4713e
Fast-forward
 README3.md | 1 <span class="ansi-green-fg">+</span>
 1 file changed, 1 insertion(+)
 create mode 100644 README3.md
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">push</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Counting objects: 3, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 284 bytes | 284.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/intodeeplearning/test.git
   1643b7b..0c4713e  main -&gt; main
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-python"><pre><span></span><span class="o">%%</span><span class="n">shell</span>
<span class="n">cd</span> <span class="n">test3</span>
<span class="n">git</span> <span class="n">branch</span>
<span class="n">git</span> <span class="n">branch</span> <span class="o">-</span><span class="n">d</span> <span class="n">test3</span> 
<span class="n">git</span> <span class="n">branch</span> <span class="o">-</span><span class="n">d</span> <span class="n">test3</span><span class="o">-</span><span class="mi">1</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>* <span class="ansi-green-fg">main</span>
  test3
  test3-1
warning: deleting branch &#39;test3&#39; that has been merged to
         &#39;refs/remotes/origin/test3&#39;, but not yet merged to HEAD.
Deleted branch test3 (was 0ebfb4e).
Deleted branch test3-1 (was 0c4713e).
</pre>
</div>
</div>

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre></pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

</div>
 

