cookiecutter-django
====================

[![Build Status](https://magnum.travis-ci.com/Fueled/cookiecutter-django.svg?token=ZbPpaKxeSEJQvwCqUqaJ&branch=master)](https://magnum.travis-ci.com/Fueled/cookiecutter-django)

Project template for django based projects, optimized for making REST API with deployment on Heroku and EC2 instances.

## Features

- Latest stable Django 1.7+
- PostresSQL 9.3.
- Support for UUID models (django 1.8 has it by default).
- [Procfile] for deploying to Heroku.
- Ansible script for quick deployment to EC2/Ubuntu.
- Settings management via [django-configurations], reads settings from `.env` if present.
- Django Rest Framework 3.0+.
- `django_sites` instead of `django.contrib.sites`
- Use [mkdocs] for project documentation.
- Use [py.test] as testing framework.
- `travis.yml` for running isolated tests and deployments to dev/qa/prod environment on Heroku from git branches.
- Only tested and stable third-party libraries are added.
- Grunt build for compass and livereload.

[mkdocs]: http://www.mkdocs.org/
[12factor]: http://12factor.net
[py.test]: http://pytest.org/
[Procfile]: https://devcenter.heroku.com/articles/procfile
[django-configurations]: https://github.com/jezdez/django-configurations

## Getting Started

Following are system level dependecies, and must be present on your machine before you run cookiecutter command. Primarily for `pre_gen_project.sh` to complete successfully.

- **postgres** - can be installed with `brew install postgres`
- **sass** - can be installed with `gem install sass`
- **graphviz** - can be installed with `brew install graphviz`
- **fabric** - can be installed with `sudo pip install fabric`

You should able to install these fairly easily if your developement machine is other than a Mac OS X.

You need to have `cookiecutter` installed in order to scafold a new project from this template. If you have `pip` installed, you simply do this by running:

    pip install --upgrade cookiecutter

After the installation is successful, you can create a new django project by simply running:

    cookiecutter https://github.com/Fueled/cookiecutter-django.git

It will ask you to some questions, after which it will create a new project in your current working directory. It will also create a virtualenv in the folder `venv` inside the project, and install all the python dependencies inside it.

Once the cookiecutter script finishes, you'll have:

1. A postgres database created, with name same as `repo_name` you provided.
2. Installed all the npm packages required
3. Installed all the python dependencies in virtualenv
4. Local settings added to `.env` file (untracked)
5. Initialized a git repo and created the first commit.

Now the only thing you'll need to do is:

1. `cd` into the new `repo_name` folder just created.
2. Activate virtualenv `source venv/bin/activate`[1]. If you plan to use virtualenvwrapper, you can install the project requirements via `pip install -r requirements/development.txt`
3. Run `fab serve`

__Summarizing__:

```
brew install postgres
gem install sass
brew install graphviz
sudo pip install fabric cookiecutter
cookiecutter https://github.com/Fueled/cookiecutter-django.git
cd <repo_name>
source venv/bin/activate
fab serve
```

Don't forget to carefully look at the generated README. Awesome, right?

You can also explore the [wiki] section for details on advance setups and usuages.

--------

Built with ♥ at [Fueled](http://fueled.com)
