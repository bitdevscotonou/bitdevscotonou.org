# BitDevs Cotonou

Simple Jekyll site for hosting all of the links from meetups past and future.

## Development throught Ruby and Jekyll

You'll need [Ruby & Jekyll](https://jekyllrb.com/docs/installation/) to run the
site locally. Once they're setup:

- Clone the repository and go into the directory
- Run `bundle install`
- Run `jekyll serve`
- Go to http://localhost:4000

## Development throught Docker

Ensure you have docker running on your machine then :

- Clone this repository and go into the directory

### Throught Dockerfile

```
  docker build -t <image_name> .
  docker run -p 4000:4000 <image_name>
```

### Throught Docker Compose

```
 docker compose build --no-cache
 docker compose up
```
```
 docker compose up --build -V
```
### Files Structures 

Litle changes have been made to the file structure to make it easier to navigate and to make it more intuitive.



```
BitdevsCotonou/
├── _data/
│   ├── i18n/
│   │   ├── en.yml
│   │   └── fr.yml
│   └── settings.yml
├── _includes/
│   ├── head.html
│   ├── header.html
│   └── lang-switcher.html
├── _layouts/
│   ├── default.html
│   └── post.html
├── _pages/
│   ├── en/
│   │   ├── about.md
│   │   ├── events.md
│   │   └── index.md
│   └── fr/
│       ├── about.md
│       ├── events.md
│       └── index.md
├── _posts/
│   ├── en/
│   │   └── YYYY-MM-DD-title-goes-here.md
│   └── fr/
│       └── YYYY-MM-DD-title-goes-here.md
├── assets/
│   ├── css/
│   │   └── main.scss
│   ├── js/
│   └── images/
├── _config.yml
├── Dockerfile
├── docker-compose.yml
├── Gemfile
└── README.md
```

## Making a Post
 ### READ BEFORE : 
`/en/` is related to English language and `/fr/` is related to French language.
### Create a new markdown file in the `_posts` directory. The file name
To make a new post, make a new file in `_posts/` with a title of
`YYYY-MM-DD-title-goes-here`. At the top of the file you'll want to provide the
following information:

```md
---
layout: post # Always post
type: socratic # or whitepaper for a whitepaper series
title: "Name of the Post"
lang: `en` for English or `fr` for French
meetup: "https://lu.ma/y7cff6uz"
---
```

After that, it's just simple markdown. The site will auto-generate the rest.

## Changing Site Data

All site configurations are either contained in `_config.yml` or
`_data/settings.yml`. Some data is duplicated between the two due to the way
Jekyll injects variables, so be sure to update both.

## Changing i18n configurations : 
All i18n configurations are contained in `_data/i18n/` except the default lang and routing ones which are contained in `_config.yml`

## Attributions

Thanks to [LeNPaul](https://github.com/LeNPaul/jekyll-starter-kit) for the
Jekyll starter kit this was forked from.
