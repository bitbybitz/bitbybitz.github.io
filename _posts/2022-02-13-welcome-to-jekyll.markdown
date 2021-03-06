---
layout: post
title:  "Github Pages & Jekyll!"
date:   2022-02-13 14:47:46 -0500
categories: jekyll update
---

## Links
- [Github Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)
- [Markdown Guide](https://www.markdownguide.org/)
- [Markdown Editor](https://dillinger.io/)

## What Is Jekyll
Jekyll is a popular static site generator which takes Markdown and HTML and creates a complete static site with this content. You can specify the design and layout template on your own. Tweak the site’s look and feel, URLs, data displayed on the page and more. 

Before you can start using jekyll to create your blog, you will need to install ruby, jekyll, git, and VS Code. I’ll wont walk  through the entire installation process and setup on macOS so this will mainly be a walkthrough of the setup and deployment process

## Install Software
- [Ruby](https://www.ruby-lang.org/en/documentation/installation/)
- [Bundler](https://bundler.io/)
- [Jekyll](https://jekyllrb.com/docs/installation/)
- [VS Code](https://code.visualstudio.com/download)

## Create a Repository for Your Site
1. In the upper right corner of your github, click the plus button and select **New Repository**
2. Use the **Owner** drop down and select the account you want as owner of the repo.
3. Type the name of your repo. If you are creating an org or user site, the repo must be named <user>.github.io or <org>.github.io
4. Choose your repo’s visibility as public.

## Create Your Site
Before you create the site, you will need a repository for your site on github.

1. Open your terminal
2. Navigate to the location where you want to store your sites source files and create a directory for your repository. 

```jsx
mkdir bitbybit-blog
```

3. Initialize your local git repository

```jsx
git init
```

4. Choose a publishing source
    a. The default publishing source for user and organization sites is the root of the default branch for the repo. The default branch for project sites is the root of the gh-pages branch
    b. You can publish your site from any branch in the repo, either from the root of the repo on that branch or from the /docs folder on that branch.
    c. If you choose the /docs folder of any branch, github pages will read everything to publish your site, including the CNAME file from the docs folder. This would be set up if you wanted to use a custom domain for you github pages site.
7. Create a new jekyll site 

```jsx
jekyll new --skip-bundle .
```

8. Open the Gemfile that jekyll created and add a # to the beginning of the line that starts with gem “jekyll” to comment out this line
9. Add the github-pages gem by editing the line starting with # gem “github-pages” to 

```jsx
gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins
```

10. Save and close the gemfile then 

```jsx
bundle install
```

11. You can test your site locally using the following command

```jsx
bundle exec jekyll serve
```

12. Add and commit your work

```jsx
git add .
git commit -m "Initial github pages site with jekyll"
```

13. Add your repo on github as a remote 

```jsx
git remote add origin https://github.com/bitbybitz/bitbybitz.github.io.git
```

14. Push the repo to github

```jsx
git push -u origin main
```

15. On github, navigate to your repo and under the repo name click **settings**
16. In the **Code & Operations** section click **Pages**
17. To see your published site under **Github Pages** click your site’s URL
