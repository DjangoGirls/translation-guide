# When the Translation is Ready

Time to explain our process of publishing a new translation of the tutorial. It is far from ideal and we would love to automate it in a future. 

We use Spanish (`es`) as an example, but of course you need to adjust it to the language you're publishing.

Here is an example PR for publishing translation: https://github.com/DjangoGirls/tutorial/pull/273


Crowdin
-------

1. Go [here](https://crowdin.com/project/django-girls-tutorial/settings#translations)
2. Click on `Build project` button
3. After the build is done, click on `Download` button next to the language you want to publish.

Move files to tutorial
-------------

1. Pull our tutorial from master
2. Create a new branch called `spanish`
3. Unzip file you downloaded from Crowdin. In the folder you will see two folders: es and _book. Copy folder es and place it in root directory of tutorial (next to en, pl, uk).
4. Edit LANGS.md (in root directory of a tutorial) and add there a link to the language version. Example.
5. Commit this as a first version to a branch

Fix what Crowdin broke
-----------

1. You have to manually fix the es/SUMMARY.md file, [like that](https://github.com/DjangoGirls/tutorial/commit/b2fd8cd538db5107f9fb809282e0970f494a9314).
2. You have to fix the Gitter badges, [like that](https://github.com/DjangoGirls/tutorial/commit/82322d14b15a85aab36f379c747055d9d0219e52).
3. You have to fix a list of links in the What's next tutorial, [like that](https://github.com/DjangoGirls/tutorial/commit/9d47e214bb9e96b41f95be6c5010ff2138db4041).

Copy images
--------


1. You need to copy all of the directories with images from English version to Spanish version. Go to tutorial directory in command line and execute this command:
find en -name "images"
This will list you all of the images directories you need to copy. You can also copy and paste this:

```
find en -name "images"
```

This will list you all of the `images` directories you need to copy. You can also copy and paste this:

```
LNG=es && cp -r en/css/images $LNG/css/images && cp -r en/django_admin/images $LNG/django_admin/images && cp -r en/django_forms/images $LNG/django_forms/images && cp -r en/django_start_project/images $LNG/django_start_project/images && cp -r en/django_templates/images $LNG/django_templates/images && cp -r en/django_urls/images $LNG/django_urls/images && cp -r en/django_views/images $LNG/django_views/images && cp -r en/domain/images $LNG/domain/images && cp -r en/extend_your_application/images $LNG/extend_your_application/images && cp -r en/how_the_internet_works/images $LNG/how_the_internet_works/images && cp -r en/html/images $LNG/html/images && cp -r en/images $LNG/images && cp -r en/python_introduction/images $LNG/python_introduction/images
```
Above command should cover all of the directories, unless we add some new ones to the tutorial.

Add credits in es/README.md
-------

1. Go to [Crowdin project settings, tab "Reports"](https://crowdin.com/project/django-girls-tutorial/settings#reports-details).
2. Choose `Custom report` from the left.
3. Show report for `Words translated`, report language `Spanish`. Then click `Generate`. There you have a list of contributors to the given language, sorted by how much they contributed. Yay!
4. Add a nice thank you in es/README.md file, [like that](https://github.com/DjangoGirls/tutorial/commit/4a12f8f554c842d8dc0a8484b768e4f2e7afec2e)

Test in Gitbook locally
------

1. Download [Gitbook editor](https://github.com/GitbookIO/editor)
2. Open tutorial directory in the Gitbook editor
3. Go to menu Book -> Preview Website.
4. Click through the tutorial in new language and make sure it looks ok.

Submit a PR
-----------

Create a new Pull Request to master and let others test it ;)

Ta-da! 
