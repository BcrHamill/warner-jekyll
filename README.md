# Warner-jekyll
Site for novelist Alan Warner

### Getting up and running

1. Install [Git](https://git-scm.com/)
2. Install [Ruby](https://www.ruby-lang.org/en/)
3. Install [Jekyll](http://jekyllrb.com/)
4. Install [Sass](http://sass-lang.com/install)

### Running the Site

* To preview the site in a browser:
```rake preview```

* To create a new page:
```rake page name="name.html"```

* To create a new post:
```rake post title="A Title" [date="2012-02-09"] [tags=[tag1,tag2]] [category="category"]```

* To compile sass during development:
```sass --watch assets/sass:assets/css```

# Deploying the Site

The server has been set up with a remote bare push repository and a ```post-receive``` hook that copies the site's files into ```/home/comcar1/alanwarner.net/_site```

The git repo lives at ```/home/comcar1/alanwarner.net/repo/site.git```.
Inside this folder the following ```post-receive``` file has been added inside the ```hooks``` directory:

```bash
#!/bin/sh
git --work-tree=/home/comcar1/alanwarner.net/ --git-dir=/home/comcar1/alanwarner.net/repo/site.git checkout -f
```

The dev site at ```dev.alanwarner.net``` has been provisioned in the same way.

To add deployment remotes do:

git remote add production ssh://comcar1@alanwarner.net/home/comcar1/alanwarner.net/repo/site.git
git remote add sandbox ssh://comcar1@alanwarner.net/home/comcar1/dev.alanwarner.net/repo/site.git

To deploy changes to the site run:

```git push production master```

or

```git push sandbox master```


