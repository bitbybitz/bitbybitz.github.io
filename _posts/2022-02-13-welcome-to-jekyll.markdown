---
layout: post
title:  "Github Pages & Jekyll!"
date:   2022-02-13 14:47:46 -0500
categories: jekyll update
---

## What Is Jekyll

Jekyll is a popular static site generator which takes Markdown and HTML and creates a complete static site with this content. You can specify the design and layout template on your own. Tweak the site’s look and feel, URLs, data displayed on the page and more. 

Before you can start using jekyll to create your blog, you will need to install ruby, jekyll, git, and VS Code. I’ll wont walk  through the entire installation process and setup on macOS so this will mainly be a walkthrough of the setup and deployment process

## Install Software
- Ruby
- Jekyll
- VS Code

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

1. Initialize your local git repository

```jsx
git init
```

5. Choose a publishing source
    1. The default publishing source for user and organization sites is the root of the default branch for the repo. The default branch for project sites is the root of the gh-pages branch
    2. You can publish your site from any branch in the repo, either from the root of the repo on that branch or from the /docs folder on that branch.
    3. If you choose the /docs folder of any branch, github pages will read everything to publish your site, including the CNAME file from the docs folder. This would be set up if you wanted to use a custom domain for you github pages site.
6. Create a new jekyll site 

```jsx
jekyll new --skip-bundle .
```

7. Open the Gemfile that jekyll created and add a # to the beginning of the line that starts with gem “jekyll” to comment out this line
8. Add the github-pages gem by editing the line starting with # gem “github-pages” to 

```jsx
gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins
```

9. Save and close the gemfile then 

```jsx
bundle install
```

10. You can test your site locally using the following command

```jsx
bundle exec jekyll serve
```

11. Add and commit your work

```jsx
git add .
git commit -m "Initial github pages site with jekyll"
```

12. Add your repo on github as a remote 

```jsx
git remote add origin https://github.com/bitbybitz/bitbybitz.github.io.git
```

13. Push the repo to github

```jsx
git push -u origin main
```

14. On github, navigate to your repo and under the repo name click **settings**
15. In the **Code & Operations** section click **Pages**
16. To see your published site under **Github Pages** click your site’s URL
