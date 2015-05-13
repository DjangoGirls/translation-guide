# Publishing translations

Yay! If you're reading this, you might have just finished working on your translation. OMG, so awesome, congratulations! We know how much work it is.

Now it's time to explain our process of publishing new translations of the tutorial. It is far from perfect and we would love to automate this process in the future.

If you want to make it easier for us, you can follow the steps below to submit a pull request straight to the [repository](https://github.com/DjangoGirls/tutorial) for the Django Girls tutorial. If you are unsure how to handle certain steps, just [open a Github issue](https://github.com/DjangoGirls/tutorial/issues/new) and we will take care of that for you.

In the following example we use Spanish (`es`) as the new language; you will need to adjust the steps to the language you're publishing.

Here is an example PR for publishing a translation: https://github.com/DjangoGirls/tutorial/pull/273

Crowdin
-------

1. Go to the [Crowdin settings](https://crowdin.com/project/django-girls-tutorial/settings#translations) page.
2. Click on the `Build project` button. If you don't have permissions to do that part, please email us at [hello@djangogirls.org](mailto:hello@djangogirls.org).
3. After the build is done, click on the `Download` button next to the language you want to publish.

Move files to the tutorial
-------------

1. Clone our tutorial from its master branch.
2. Create a new branch called `spanish` (`git checkout -b spanish`).
3. Unzip the file you downloaded from Crowdin. In the unzipped folder you will see two subfolders: `es` and `_book`. Copy the folder named `es` and place it into the root directory of the tutorial (next to `en`, `pl`, `uk`).
4. Edit LANGS.md (found in the root directory of the tutorial) and add a link to the language version to it. Here is an [example](https://github.com/DjangoGirls/tutorial/commit/569f10512bb5642661093dcbcc0ed7683d65cb38).
5. Commit this as a first version of your translation to the branch for your language.

Fix what Crowdin broke
-----------

1. You have to manually fix the `es/SUMMARY.md` file, [like here](https://github.com/DjangoGirls/tutorial/commit/b2fd8cd538db5107f9fb809282e0970f494a9314).
2. You will also have to fix the Gitter badges, [like here](https://github.com/DjangoGirls/tutorial/commit/82322d14b15a85aab36f379c747055d9d0219e52).
3. You also need to fix the list of links in the "What's next" chapter in the tutorial, [like here](https://github.com/DjangoGirls/tutorial/commit/9d47e214bb9e96b41f95be6c5010ff2138db4041).

Copy images
--------


1. You will need to copy all of the directories with images from the English version to the Spanish version. In your console, go to the directory containing the Django Girls tutorial and execute the following command:

```
find en -name "images"
```

This will list all of directories containing images that you need to copy. You can also copy and paste this:

```
LNG=es && cp -r en/css/images $LNG/css/images && cp -r en/django_admin/images $LNG/django_admin/images && cp -r en/django_forms/images $LNG/django_forms/images && cp -r en/django_start_project/images $LNG/django_start_project/images && cp -r en/django_templates/images $LNG/django_templates/images && cp -r en/django_urls/images $LNG/django_urls/images && cp -r en/django_views/images $LNG/django_views/images && cp -r en/domain/images $LNG/domain/images && cp -r en/extend_your_application/images $LNG/extend_your_application/images && cp -r en/how_the_internet_works/images $LNG/how_the_internet_works/images && cp -r en/html/images $LNG/html/images && cp -r en/images $LNG/images && cp -r en/python_introduction/images $LNG/python_introduction/images
```
The above command should cover all of the directories, unless we added some new ones to the tutorial. Make sure to check that.

Add credits in es/README.md
-------

1. Go to the ["Reports" tab](https://crowdin.com/project/django-girls-tutorial/settings#reports-details) in the Crowdin project settings. If you don't have permissions to do that, email us at [hello@djangogirls.org](mailto:hello@djangogirls.org) (sorry again, if that's the case).
2. Choose `Custom report` from the left.
3. Show the report for `Words translated`, report language `Spanish`. Then click on `Generate`. You will get a list of all contributors to your language, sorted by how much each has contributed. Yay!
4. Add a nice thank you to your `es/README.md` file, similar how it was done [here](https://github.com/DjangoGirls/tutorial/commit/4a12f8f554c842d8dc0a8484b768e4f2e7afec2e).

Test in Gitbook locally
------

1. Download the [Gitbook editor](https://github.com/GitbookIO/editor).
2. Open the directory containing the tutorial with the Gitbook editor.
3. Go to the menu `Book > Preview Website`.
4. Click through the tutorial in the language you added and make sure everything looks alright.

Submit a PR
-----------

Create a new pull request to our master branch and let others test your translation. ;)

Ta-da!
