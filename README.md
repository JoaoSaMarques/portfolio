# Portfolio

## Index


## How to work with this:

### Projects

To add projects to your Projects page:
- Go to `wwwroot/data/projects.json`
- Add a new entry following the template

Example, if you want to add a project 7 after the project 6, the current layout ends in:

```
[
    {
        "slug": "project-6",
        "title": "Project 6",
        "thumbnail": "/assets/project6.jpg",
        "heroImage": "/assets/project6.jpg",
        "shortDescription": "Short description of the project.",
        "longDescription": "Another placeholder project for upcoming experiments in visual design, prototypes, or collaborations.",
        "link": "https://example.com"
    }
]
```

You'd have to add a `,` after the last `}` and copy the same structure:

```
[
    {
        "slug": "project-6",
        "title": "Project 6",
        "thumbnail": "/assets/project6.jpg",
        "heroImage": "/assets/project6.jpg",
        "shortDescription": "Short description of the project.",
        "longDescription": "Another placeholder project for upcoming experiments in visual design, prototypes, or collaborations.",
        "link": "https://example.com"
    },
    {
        "slug": "project-7",
        "title": "Project 7",
        "thumbnail": "/assets/project7.jpg",
        "heroImage": "/assets/project7.jpg",
        "shortDescription": "Short description of the project.",
        "longDescription": "Another placeholder project for upcoming experiments in visual design, prototypes, or collaborations.",
        "link": "https://example.com"
    },
]
```

#### Files

All assets/files must go under the `wwwroot/assets` folder.

### Projects

To add projects to your Projects' "Art" section:
- Go to `wwwroot/data/art.json`
- Add a new entry following the template, similarly to how you'd do to projects

Example, if you want to add a project 7 after the project 6, the current layout ends in:

```
[
  {
    "slug": "drawing-1",
    "title": "Selected drawing",
    "thumbnail": "/assets/drawing1.jpg",
    "heroImage": "/assets/drawing1.jpg",
    "description": "Extended view of one of my drawings."
  }
]
```

### Deploying

#### Manual

##### 1. Run this in your project root:

`dotnet publish -c Release -o publish`

This puts the ready-to-serve site in publish/wwwroot.

##### 2. Take everything inside publish/wwwroot and push it to a gh-pages branch (not the repo root).

Make sure GitHub Pages is serving from gh-pages branch → / folder (you can set this in repo settings).

#### Automatic

I've included a workflow that does this for you so you don't have to rebuild everytime. All you have to do is make sure the contents of `.github/workflows` are in the main branch, but that's solved by making this branch the main one. If you want to keep the old work you had, you can follow these steps:

##### 1. Make sure you're up to date
`git fetch origin`

##### 2. Create the backup branch (old) from current main

First, switch to main:

`git checkout main`

Then create the new branch:

`git checkout -b old`

Push it if you want it on the remote:

`git push origin old`

##### 3. Replace main with the contents of source

Now go to the source branch:

`git checkout source`

And force main to point to whatever source currently is:

`git branch -f main`

##### 4. Push the new main to remote (force push required)

Because you're rewriting history, you need to force push:

`git push origin main --force`