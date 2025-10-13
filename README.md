# Drishtikon 

A simple, fast, Hugo theme that can be used for blogging and as a portfolio website.

![./images/screengrab.png](https://github.com/kishenarayan/drishtikon/blob/main/images/screengrab.png)

Welcome to drishtikon (*perspective*). Stay a while! Drishtikon is a minimal [Hugo](https://gohugo.io/) theme that takes inspiration from Andrew Hwan Park's [Brutalist Blog](https://hw4n.com/brutalist-blog/) and Tyler McRobert's [Bridget](https://tylermcrobert.com/bridget-baker). Additionally, this theme uses the [Inter](https://rsms.me/inter/) typeface originally developed by Rasmus Andersson.

![./images/postsgrab.png](https://github.com/kishenarayan/drishtikon/blob/main/images/postsgrab.png)

![./images/writingsgrab.png](https://github.com/kishenarayan/drishtikon/blob/main/images/writingsgrab.png)

![./images/photosgrab.png](https://github.com/kishenarayan/drishtikon/blob/main/images/photosgrab.png)

[Here](https://kishenarayan.github.io) is a link to my personal website which uses the same theme. 





## Installation

Before starting, make sure you have installed [Hugo](https://gohugo.io/installation/) and [Go](https://go.dev/doc/install). To check that both of these are installed, 

```bash
$ go version
```
```bash
$ hugo version
```
### Git Submodule 

First, when you are in your main hugo site folder, 

```bash
$ git submodule add https://github.com/kishenarayan/drishtikon.git themes/drishtikon
```

Then in your ```hugo.toml``` file, add the following: 

```toml
theme: 'drishtikon'
```

To update the theme: 
```bash
$ git submodule update --rebase --remote
```

### Hugo Submodule 

First, when you are in your main hugo site folder, 

```bash 
$ hugo mod init github.com/<your_user>/<your_project>
```

Then, in your  ```hugo.toml``` file, add the following:

```toml
[module]
  [[module.imports]]
    path = 'github.com/kishenarayan/drishtikon'
```


To update the theme:
```bash
$ hugo mod get -u github.com/kishenarayan/drishtikon
```

For more information, check out the [docs](https://gohugo.io/hugo-modules/use-modules/).

### Cloning

You can also clone this theme's repository into your own hugo site by doing the following, 

```bash 
 $ git clone https://github.com/kishenarayan/drishtikon.git themes/drishtikon
```

To update the theme: 

```bash
$ cd themes/drishtikon
$ git pull
```

## Usage 

### ```hugo.toml```

Ensure your ```hugo.toml``` has the following structure (modify as necessary for your purposes): 

```toml 
baseURL = 'https://example.com"
languageCode = 'en-us'
title = 'your-title'
theme = 'drishtikon'

[markup]
  [markup.goldmark]
    [markup.goldmark.extensions]
      [markup.goldmark.extensions.passthrough]
        enable = true
        [markup.goldmark.extensions.passthrough.delimiters]
          block = [['\[', '\]'], ['$$', '$$']]
          inline = [['\(', '\)']]

[caches]
  [caches.images]
    dir = ':cacheDir/images'

[params]
    # Uncomment if you have a logo image
    # logo = "/path-to-your-logo"

    # Profile section for homepage
    profilePhoto = "/path-to-your-profile-photo"
    profileDescription = """Add a profile description."""
    profileUpdates = "Add your updates."
    github = "https://github.com/yourusername"
    email = "mailto:your.email@example.com"
    linkedin = "https://www.linkedin.com/"
    pinterest = "https://www.pinterest.com/"
    cv = "/path-to-your-cv"
    math = true

    # Uncomment if you want to customize the colors
    # backgroundColor = "#f9dc90"
    # linksColor = "#805690"
    # textColor = "#333"
    # fontFamily = "Inter"
    # tableHeaderColor = "#d46f93"
    # tableContentColor = "#f89e9d"
    # tableRowHoverColor = "#ffbbba"
    # writingCardBackground = "#fdf1cd"    

[menu]
    [[menu.main]]
        name = "posts"
        url = "/posts/"
        weight = 10
    [[menu.main]]
        name = "writings"
        url = "/writings/"
        weight = 20
    [[menu.main]]
        name = "photos"
        url = "/photos/"
        weight = 30

```
This theme uses [KaTeX](https://katex.org/) for mathematics typesetting. 

## Adding Content

### Set-Up 

Ensure that your ```content``` folder has the following structure: 

```bash 
content
├───photos
├───posts
└───writings 
``` 

### Posts 

To add a post, simply create a new markdown file ```post-title.md``` in the ```posts``` folder. 

### Writings 

To add a writing, simply create a new markdown file ```writing-title.md``` in the ```writing``` folder. In the frontmatter of the markdown file put ```category: ```. The available categories are ```research```, ```expository```, and ```projects```. 

### Photos 

To add photos, you must first add an album folder to the ```photos``` folder. Here is an example of what the strucutre of ```photos``` could look like. 

```bash 
photos 
├───album1
└───album2 
```

Ensure there is an ```_index.md``` file  in the ```photos``` folder and each of the album folders you add. The frontmatter of this file should look like:

```markdown 
---
title: "Your Album Title"
---
```

Then to add a photo, inside an album folder, add a markdown file ```photo1.md```. It's front matter should look like: 
```markdown
---
title: "Your Photo Title"
description: "Your Photo Description"
image: "/path-to-your-photo" 
weight: 1
---
``` 

### Site Logo

To replace the logo of the website put your image/svg file into into the `icons` directory of your website static directory. Then in your `hugo.toml` file uncomment the `logo` line and put the path to your logo.

## Almost Done

To see your site live, use Hugo's built-in local server by running: 

```bash
$ hugo server
```
and navigate to  http://localhost:1313.

## Contributing

All bug reports and pull requests are welcome under https://github.com/kishenarayan/drishtikon.

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).


