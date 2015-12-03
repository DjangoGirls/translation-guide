# Publishing translations

Yay! If you're reading this, you might have just finished working on your translation. OMG, so awesome, congratulations! We know how much work it is.

Now it's time to explain our process of publishing new translations of the tutorial. It is far from perfect and we would love to automate this process in the future.

If you want to make it easier for us, you can follow the steps below to submit a pull request straight to the [repository](https://github.com/DjangoGirls/tutorial) for the Django Girls tutorial. If you are unsure about how to handle certain steps, just [open a Github issue](https://github.com/DjangoGirls/tutorial/issues/new) and we will take care of that for you.

In the following example we use Spanish (`es`) as new language; you will need to adjust the individual steps to the language you're publishing.

Here is an example PR for publishing a translation: https://github.com/DjangoGirls/tutorial/pull/273

Crowdin
-------

1. You need one or two persons to proofread and validate your translation. If no one on your team has proofreader status, please send an [email](mailto:translations@djangogirls.org) to the translations managers or [contact us](mailto:hello@djangogirls.org).
2. When your translation is 100% validated, contact the [translations managers](mailto:translations@djangogirls.org). They will send you a `.zip` file containing your translation and a `.xlsx` file that contains a list of all contributors to your language.

Move files to the tutorial
-------------

1. [Fork](https://help.github.com/articles/fork-a-repo/) Django Girls tutorial [repository](https://github.com/DjangoGirls/tutorial) and clone your repository from its master branch.
2. Create a new branch called `spanish` (`git checkout -b spanish`).
3. Unzip the file we sent to you. In the unzipped folder you will see one subfolder: `es`. Copy and place it into the root directory of the tutorial (next to `en`, `pl`, `uk`).
4. Edit `LANGS.md` (found in the root directory of the tutorial) by adding a link to your language to it. Here is an [example](https://github.com/DjangoGirls/tutorial/commit/569f10512bb5642661093dcbcc0ed7683d65cb38).
5. Commit this as a first version of your translation to the branch for your language.

Fix what Crowdin broke
-----------

1. You have to manually fix the `es/SUMMARY.md` file, [like here](https://github.com/DjangoGirls/tutorial/commit/b2fd8cd538db5107f9fb809282e0970f494a9314).
2. You will also have to fix the Gitter badges, [like here](https://github.com/DjangoGirls/tutorial/commit/82322d14b15a85aab36f379c747055d9d0219e52).
3. You also need to fix the list of links in the "What's next" chapter in the tutorial, [like here](https://github.com/DjangoGirls/tutorial/commit/9d47e214bb9e96b41f95be6c5010ff2138db4041).
4. If the translation was built on top of the version for gitbook 1.5.0 you will need to fix code formatting. Gitbook 2.x builder uses the same templating syntax as Django does so it tends to break on the parts of the code that haven't been escaped. You will have to check every `.md` files: remove one level of indentation and wrap the code blocks in code fencess \`\`\`. The `{% raw %}{% csrf_token %}{% endraw %}` should be wrapped in `{% raw %}{% raw %}{% endraw %}{% endraw %}` blocks.
5. You will have to add `/` at the beginning of every paths in `{% raw %}{% include %}{% endraw %}`, [like here](https://github.com/DjangoGirls/tutorial/commit/069f186d91d9787fff28227c60c89cd76d3bc92f). Files that need to be changed are: `installation/README.md`, `python_installation/README.md`, `django_installation/README.md`, `deploy/README.md` and `code_editor/README.md`.
6. Make yourself some tea, have some chocolate or just take a little time for yourself! You made an amazing job <3

Copy images
--------


1. You will need to copy all of the directories with images from the English version to the Spanish version. In your console, go to the directory containing the Django Girls tutorial and execute the following command:

```
find en -name "images"
```

This will list all of directories containing images that you need to copy. You can also copy and paste this:

```
LNG=es && cp -r en/css/images $LNG/css/images && cp -r en/django_admin/images $LNG/django_admin/images && cp -r en/django_forms/images $LNG/django_forms/images && cp -r en/django_start_project/images $LNG/django_start_project/images && cp -r en/django_templates/images $LNG/django_templates/images && cp -r en/django_urls/images $LNG/django_urls/images && cp -r en/django_views/images $LNG/django_views/images && cp -r en/extend_your_application/images $LNG/extend_your_application/images && cp -r en/how_the_internet_works/images $LNG/how_the_internet_works/images && cp -r en/html/images $LNG/html/images && cp -r en/images $LNG/images && cp -r en/python_introduction/images $LNG/python_introduction/images && cp -r en/deploy/images/ $LNG/deploy/images && cp -r en/python_installation/images/ $LNG/python_installation/images
```
The above command should cover all directories unless new ones got added since this guide was written. Make sure to check for new directories.

Add credits in es/README.md
-------

1. Open the `.xlsx` we sent you: it contains a list of all contributors to your language.
2. Add a nice thank-you note to your `es/README.md` file, similar to how it was done [here](https://github.com/DjangoGirls/tutorial/commit/4a12f8f554c842d8dc0a8484b768e4f2e7afec2e).

Test in Gitbook locally
------

1. Download the [Gitbook editor](https://www.gitbook.com/editor/).
2. Open the directory containing the tutorial with the Gitbook editor.
3. Go to the menu `Book > Preview Website`.
4. Click through the tutorial in the language you added and make sure everything looks alright. If you can't find your translation, check if you're in the good branch.

Submit a PR
-----------

Create a new pull request to our master branch and let others test your translation. ;)

Ta-da!
