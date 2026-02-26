# Portfolio

## Index
1. [Projects](#projects)
2. [Art](#art)
3. [Deploying](#one-time-only)
4. [Workflow](#automatic)

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

#### One time only

You only have to do this one time (unless you massively change the project). (Editing `json`s doesn't count as changing the project).

##### 1. Run this inside of the Project folder:

`dotnet publish -c Release -o publish`

This puts the ready-to-serve site in `publish/wwwroot`.

##### 2. Take everything inside publish/wwwroot and push it ALONE (ON ITS OWN) to a NEW branch (not the repo root).

##### 3. Make that branch the main one and move this one to source

`git checkout main`

`git checkout -b source`

`git push origin source`

Then, whatever name of your branch:

`git checkout yourbranch`

`git branch -f main`

Because you're rewriting history, you need to force push:

`git push origin main --force`

#### Automatic

After doing the first deployment, you can directly edit the `json` files on the main branch without needing to redeploy. The workflow I've included does it for you.

BTW: Your old work is on a branch called `old` in case you need it for anything. 


