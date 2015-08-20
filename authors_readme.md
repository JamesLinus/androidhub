## Contributing to the Intel Android Hub!
Hello authors! Ready to contribute to a website and skip Wordpress or whatever other CMS people are making you use? We've got a completely open source environment ready for you to write your articles in markdown, jade, or HTML. 

&nbsp;
&nbsp;


##### Required Tools
> These tools need to be installed on your machine, hopefully they're already there. We also expect you to have a Github account, and have used CLI tools a bit

- [Node/NPM](https://nodejs.org/)
- [Roots](http://roots.cx/) `npm i -g roots`
- [Bower](http://bower.io/) `npm i -g bower`
- Git


&nbsp;
&nbsp;


## Setup
1. Fork
2. Clone your fork
3. Install project dependencies `npm i && bower i`

&nbsp;

#### Overview
There's lot o stuff in the project folder, how about I point you to what's relevant for you? =)

```dir
this_project/
└─── data/
    └─── authors/
    		your_github_handle.yaml
    		someone_else.yaml
    		...
└─── posts/
    └─── your_github_handle/
    		your-post-file-name.jade
            ...
```

`your_github_handle.yaml` is a file dedicated to meta data about you, the author. This information is used around the site whenever we're talking about you. 
`posts/your_github_handle` is your own folder to create your posts in.

Not too bad right? Tell us about yourself as an author, then go write posts. 


&nbsp;
&nbsp;


## Init
If this is your first time contributing to the hub, you'll need to create yourself by putting some data into some files. We've got a handy author kickoff script that does lots of the work for you, so let's start there.

##### Kick it off!
In your terminal, type `npm run new-author`

##### So what's gonna happen?
Enter your github handle into the cli prompt, this creates a .yaml entry for you in `data/authors/`, which will look like this. 

```yaml
# Personal Info
displayname:  ''
nickname:     ''
website:      ''
title:        ''

# Social Networks
twitter:      ''
github:       '{{github_handle}}'
codepen:      ''
```

It also creates a folder for you in `posts/{{your_handle}}/` which will hold onto your posts. We'll talk about that next.


&nbsp;
&nbsp;


## Write
If you're familiar with blog engines like [Ghost](https://ghost.org/) or [Jekyll](http://jekyllrb.com/), then you'll be right at home with the Intel Android Hub's blog architecture. What's awesome about this architecture though, you're not limited to just Markdown, you can write [Jade](http://jade-lang.com/), [Coffeescript](http://coffeescript.org/), [etc](http://jade-lang.com/reference/filters/)! We felt that most authors would prefer markdown, so that's the style we'll talk about here. Plus, if you know Jade, then you're likely already familiar with it's ability to do markdown.

##### Example Post:

```jade
---
title:      'My First Post!'
tags:       [android]
categories: [ideate, launch]
heroimage:  ''
excerpt:    'Short description of the article'
---

extends ../views/layouts/_single

block content
  :markdown
    Here's my first post. **How exciting!**
```

First thing you'll notice is the "front matter." This is yaml style data that get consumed by the architecture and becomes the article meta data. Nothing too strange about the front matter right? It is worth noting, that there is no `url` front matter key, and that's because the post url will be generated based off the file name of your post. So the pretty url and post title are separate.

But, then we get into some Jade with the `extends` statement, and if you don't know Jade, [check this link](http://jade-lang.com/reference/extends/) for their excellent break down. The main part you'll be working with is what's inside of the `block content`. This example post is using markdown, and that's simply done by putting any markdown inside of the :markdown Jade [filter](http://jade-lang.com/reference/filters/). 

Go markdown crazy. With just markdown alone you can make a very interesting and dynamic article. For the Jade fans or adventurous, you can write your whole post in Jade, include scripts, and basically make your post like you would an HTML page. So in terms of blog post capabilities, this is about as unfettered as it gets!


&nbsp;
&nbsp;


## Preview
`roots watch`

Run that awesome command from your terminal, and a live reload web server will fire up and open a tab in your browser. Your post, given it's followed the format and instructions, will appear in the feed. Navigate to it, and you'll have your dev setup ready to go. At this point, we're hoping for a very easy editing scenario for you.

Just to remind ya, every time you save your post, the server will compile and update. Why work any other way right?


&nbsp;
&nbsp;


## Tests
`npm run test`

This project is equipped with a test suite to verify and validate your post entries. There are certain required fields, etc, and before you submit your pull request, it would behoove you to run the test suite on your work. This test will be run as a first step by the pull request approver. It's a really easy way to know if you've covered all your bases too.


&nbsp;
&nbsp;


## Pull Request
Aw snap, you're ready to push your work to the world. The final step is for you to submit a pull request to the original repo from your fork. Open source is a beautiful thing isn't it? Your pull request will be reviewed and if accepted, will trigger a build in the site. Soon after that, you'll find your work has been deployed to the site, ready for sharing.

