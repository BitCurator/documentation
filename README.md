# BitCurator Environment Documentation

Welcome to the BitCurator Environment Documentation source repository. This repository holds the markdown formatted content pages, image assets, and configuration files used by the [mkdocs](https://mkdocs.readthedocs.io) static site generator software. The generated website is accessible at: [https://bitcurator.github.io/documentation/](https://bitcurator.github.io/documentation/) . The generated `html` pages are located in the [gh-pages branch](https://github.com/BitCurator/documentation/tree/gh-pages)


## Contributions

This site uses [mkdocs](https://mkdocs.readthedocs.io). New pages may be added by creating new [markdown](https://www.mkdocs.org/user-guide/writing-your-docs/#writing-with-markdown) files`.md` in the [docs](./docs) folder and/or section sub-folders. 

Pages in sub-folders will be grouped alongside the rest of the folder content.


## Static Site generation

The generated site is hosted in Github Pages following the [deploying-your-docs - mkdocs](https://www.mkdocs.org/user-guide/deploying-your-docs/) documentation. To regenerated and deploy the site, [install mkdocs](https://www.mkdocs.org/user-guide/installation/) locally:

Pull updates from this repository:  
`$ git pull origin main `

Generate and deploy site:  
`$ mkdocs gh-deploy`