# Ṣàgbékalẹ̀!

> **Àkíyèsí** Àkòrí tó kàn yìí lè ṣòro díẹ̀ láti kọ́ yanjú nígbà mìíràn. Máa kọ́ ọ nìṣó kí o sì parí rẹ̀; ìṣàgbékalẹ̀ jẹ́ apá kan tó ṣe pàtàkì nínú ìlànà ìgbéjáde ààyè ayélujára náà. Àkòrí yìí wà ní àárín àlàyé náà kí atọ́nisọ́nà rẹ bá lè ràn ọ́ lọ́wọ́ pẹ̀lú ìlànà gbígbé ààyè ayélujára rẹ sórí íńtánẹ́ẹ̀tì tó bá ṣòro díẹ̀ náà. Èyí túmọ̀ sí pé o ṣì lè parí àlàyé náà fúnra rẹ tí kò bá sí àkókò mọ́.

Títí di báyìí, ààyè ayélujára rẹ wà lórí kọ̀mpútà rẹ nìkan. Ní báyìí, o máa kọ́ bí o ṣe lè ṣàgbékalẹ̀ rẹ̀! Ṣíṣe àgbékalẹ̀ jẹ́ ìlànà ṣíṣe ìgbéjáde ètò rẹ sórí Íńtánẹ́ẹ̀tì kó lè ṣeéṣe fún àwọn èèyàn láti lọ wo ètò rẹ. :)

Gẹ́gẹ́ bí o ṣe kẹ́kọ̀ọ́, ààyè ayélujára kan ní láti wà lórí server kan. Ọ̀pọ̀lọpọ̀ àwọn olùpèsè server ló wà lórí íńtánẹ́ẹ̀tì, a máa lo [PythonAnywhere](https://www.pythonanywhere.com/). PythonAnywhere wà lọ́fẹ̀ẹ́ fún àwọn ètò kékèké tí kò ní àwọn àlejò púpọ̀, nítorí náà yóò tó fún ọ ní báyìí.

Ìpèsè ìta mìíràn tí a ó máa lò ni [GitHub](https://www.github.com), èyí tó jẹ́ ìpèsè kan fún pípèsè kóòdù. Àwọn mìíràn wà níbẹ̀, ṣùgbọ́n ó fẹ́rẹ̀ẹ́ jẹ́ gbogbo àwọn onímọ̀ nípa kóòdù ló ní account GitHub kan ní àkókò tá a wà yìí, ìwọ náà yíò ní báyìí!

Àwọn ààyè mẹ́ta wọ̀nyí yíò ṣe pàtàkì sí ẹ. Kọ̀mpútà tìẹ yíò jẹ́ ààyè tí o ti máa ṣe ìgbéjáde àti ṣíṣe àyẹ̀wò. Nígbà tí inú rẹ bá dùn pẹ̀lú àwọn ìyípadà náà, ìwọ yíò fi ẹ̀dà ètò rẹ kan sórí GitHub. Ààyè ayélujára rẹ yíò wà lórí PythonAnywhere, ìwọ yíò máa ṣe ìmúdójúìwọ̀n rẹ̀ nípasẹ̀ gbígba ẹ̀dà tuntun kan ti kóòdù rẹ láti GitHub.

# Git

> **Àkíyèsí** Tí o bá ti yanjú àwọn ìgbésẹ̀ ìṣàgbékalẹ̀ náà tẹ́lẹ̀, kò sídìí láti tún ṣe èyí mọ́ – o lè fò lọ sí abala tó kàn náà kí o sì bẹ̀rẹ̀ ṣíṣẹ̀dá repository Git rẹ.

{% include "/deploy/install_git.md" %}

## Bíbẹ̀rẹ̀ repository Git wa

Git máa n ṣàmójútó àwọn ìyípadà sí àpapọ̀ àwọn fáìlì pàtó kan nínú ohun tí a n pè ní repository kóòdù kan (tàbí "repo" ní kúkúrú). Jẹ́ ká bẹ̀rẹ̀ ẹyọkan fún iṣẹ́ wa. Ṣí console rẹ kalẹ̀ kí o sì ṣe àwọn àṣẹ wọ̀nyí, nínú àkójọpọ̀ fáìlì `djangogirls` náà:

> **Àkíyèsí** Ṣàyẹ̀wò àkójọpọ̀ fáìlì rẹ tó n ṣiṣẹ́ lọ́wọ́lọ́wọ́ pẹ̀lú àṣẹ `pwd` (Mac OS X/Linux) tàbí `cd` (Windows) ṣáájú bíbẹ̀rẹ̀ repository náà. Ó yẹ kí o wà nínú fódà `djangogirls` náà.

{% filename %}command-line{% endfilename %}

    $ git init
    Initialized empty Git repository in ~/djangogirls/.git/
    $ git config --global user.name "Your Name"
    $ git config --global user.email you@example.com
    

Bíbẹ̀rẹ̀ repository Git náà jẹ́ nnkan kan tí a nílò láti ṣe lẹ́ẹ̀kan ṣoṣo péré lórí iṣẹ́ kan (àti pé ìwọ kò ní láti tún tẹ orúkọ aṣàmúlò àti ímeèlì náà mọ́).

Git yíò ṣàmójútó àwọn ìyípadà sí gbogbo àwọn fáìlì àti fódà tó wà nínú àkójọpọ̀ fáìlì yìí, ṣùgbọ́n àwọn fáìlì kan wà tí a fẹ́ kí ó fojú fò. A máa ṣe èyí nípasẹ̀ ṣíṣẹ̀dá fáìlì kan tí a n pè ní `.gitignore` sínú àkójọpọ̀ fáìlì ìpìlẹ̀ náà. Ṣí olóòtú rẹ kalẹ̀ kí o sì ṣẹ̀dá fáìlì tuntun kan pẹ̀lú àwọn àkóónú tó tẹ̀le yìí:

{% filename %}.gitignore{% endfilename %}

    *.pyc
    *~
    __pycache__
    myvenv
    db.sqlite3
    /static
    .DS_Store
    

Tọ́jú rẹ̀ gẹ́gẹ́ bí `.gitignore` sínú fódà "djangogirls" náà.

> **Àkíyèsí** Àmì tó-ín (dot) tó wà ní ìbẹ̀rẹ̀ orúkọ fáìlì náà ṣe pàtàkì! Tí o bá n kojú ìṣòro kankan pẹ̀lú ṣíṣẹ̀dá rẹ̀ (fún àpẹẹrẹ, MacOS kò nífẹ̀ẹ́ kí o ṣẹ̀dá àwọn fáìlì tó bẹ̀rẹ̀ pẹ̀lú àmì tó-ín kan nípasẹ̀ Finder náà), nígbà náà lo ẹ̀yà "Save As" tó wà nínú olóòtú rẹ, ó máa yanjú ìṣòro náà. Ri dájú pé ìwọ kò ṣàfikún `.txt`, `.py`, tàbí èyíkéyìí àfikún mìíràn sí orúkọ fáìlì náà -- Git yíò lè dá fáìlì náà mọ̀ tí orúkọ náà bá jẹ́ `.gitignore` nìkan.
> 
> **Àkíyèsí** Ọ̀kan lára àwọn fáìlì tí o dárúkọ pàtó nínú fáìlì `.gitignore` rẹ jẹ́ `db.sqlite3`. Fáìlì yẹn jẹ́ àkójọpọ̀ dátà ti orí kọ̀mpútà rẹ, níbi tí gbogbo àwọn aṣàmúlò àti àwọn àròkọ rẹ gba títọ́jú sí. A ó tẹ̀lé ìlànà kíkọ kóòdù ayélujára, tó túmọ̀sí pé a ó lo àkójọpọ̀ dátà ọ̀tọ̀ọ̀tọ̀ fún ààyè ṣíṣe àyẹ̀wò lórí kọ̀mpútà rẹ àti ààyè ayélujára rẹ tó n ṣiṣẹ́ lórí PythonAnywhere. Àkójọpọ̀ dátà PythonAnywhere náà lè jẹ́ SQLite, bíi ẹ̀rọ ìgbéjáde rẹ, ṣùgbọ́n ìwọ yíò sábà máa lo ọ̀kan tí a n pè ní MySQL èyí tó lè kojú àwọn àlejò ààyè púpọ̀ ju SQLite lọ. Èyí tó wù kó jẹ́, nípasẹ̀ fífojú fo àkójọpọ̀ dátà SQLite rẹ fún ẹ̀dà GitHub náà, ó túmọ̀ sí pé gbogbo àwọn àròkọ àti alábòójútó tí o ti ṣẹ̀dá látẹ̀yìnwá máa wà lórí kọ̀mpútà rẹ nìkan, àti pé ìwọ yíò ní láti ṣẹ̀dá àwọn tuntun lásìkò iṣẹ́. Ó yẹ kí o ronú nípa àkójọpọ̀ dátà tó wà lórí kọ̀mpútà rẹ gẹ́gẹ́ bí ibi ìṣeré tó dára kan níbi tí o ti lè ṣàyẹ̀wò oríṣiríṣi nǹkan láìbẹ̀rù pé o máa yọ àwọn àròkọ gidi rẹ kúrò lórí blog rẹ.

Ó jẹ́ èrò tó dára kan láti lo àṣẹ `git status` kan ṣáájú `git add` tàbí nígbàkígbà tí o bá rí pé o tí ń ṣiyèméjì nípa ohun tó ti yípadà. Èyí yíò ṣe ìrànlọ́wọ́ láti ṣèdíwọ́ fún èyíkéyìí ìyàlẹ́nu láti ṣẹlẹ̀, gẹ́gẹ́ bíi ṣíṣe àfikún tàbí commit àwọn fáìlì tí kò yẹ. Àṣẹ `git status` náà yíò dá ìròyìn padà nípa àwọn fáìlì ti kò ní àmójútó/tí a ṣàtúnṣe/tí a gbé kalẹ̀, ipò ẹ̀ka náà, àti bẹ́ẹ̀ bẹ́ẹ̀ lọ. Ó yẹ kí àbájáde náà jọ èyí tó tẹ̀le yìí:

{% filename %}command-line{% endfilename %}

    $ git status
    On branch master
    
    Initial commit
    
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
    
            .gitignore
            blog/
            manage.py
            mysite/
            requirements.txt
    
    nothing added to commit but untracked files present (use "git add" to track)
    

Ní ìparí, a máa tọ́jú àwọn ìyípadà wa. Lọ sí console rẹ kí o ṣe àwọn àṣẹ wọ̀nyí:

{% filename %}command-line{% endfilename %}

    $ git add --all .
    $ git commit -m "My Django Girls app, first commit"
     [...]
     13 files changed, 200 insertions(+)
     create mode 100644 .gitignore
     [...]
     create mode 100644 mysite/wsgi.py
    

## Títi kóòdù rẹ sí GitHub

Lọ sí [GitHub.com](https://www.github.com) kí o sì forúkọ sílẹ̀ fún account aṣàmúlò ọ̀fẹ́ tuntun kan. (Tí o bá ti ṣe ìyẹn tẹ́lẹ̀ nínú ìmúrasílẹ̀ àpérò náà, ó dára!) Ri dájú láti rántí ọ̀rọ̀ aṣínà rẹ (ṣàfikún rẹ̀ sínú alákòóso ọ̀rọ̀ aṣínà rẹ, tí o bá lo ọ̀kan).

Lẹ́yìn náà, ṣẹ̀dá repository tuntun kan, pẹ̀lú orúkọ "my-first-blog". Fi àpótí adarí yíyàn "initialize with a README" náà sílẹ̀ láì yàn, fi àṣàyàn .gitignore náà sílẹ̀ ní òfìfo (a ti ṣe ìyẹn fúnra wa) àti pé fi License náà sílẹ̀ gẹ́gẹ́ bí None.

![](images/new_github_repo.png)

> **Àkíyèsí** Orúkọ `my-first-blog` náà ṣe pàtàkì – o lè yan nǹkan mìíràn, ṣùgbọ́n yóò máa wáyé ní ọ̀pọ̀ ìgbà nínú àwọn ìtọ́sọ́nà tó wà nísàlẹ̀, ìwọ yíò sì ní láti máa rọ́pò rẹ̀ nígbà kọ̀ọ̀kan. It's probably easier to stick with the name `my-first-blog`.

On the next screen, you'll be shown your repo's clone URL, which you will use in some of the commands that follow:

![](images/github_get_repo_url_screenshot.png)

Ní báyìí, a nílò láti ṣe ìsopọ̀ repository Git tó wà lórí kọ̀mpútà rẹ pẹ̀lú èyí tó wà lórí GitHub.

Tẹ èyí tó tẹ̀le yìí sínú console rẹ (rọ́pò `<your-github-username>` pẹ̀lú orúkọ aṣàmúlò tí o tẹ̀ nígbà tí o ṣẹ̀dá account GitHub rẹ, ṣùgbọ́n láìsí àwọn àkámọ́ onígun náà -- ó yẹ kí URL náà dọ́gba pẹ̀lú URL ìfijọ tí o ṣẹ̀ṣẹ̀ rí):

{% filename %}command-line{% endfilename %}

    $ git remote add origin https://github.com/<your-github-username>/my-first-blog.git
    $ git push -u origin master
    

Nígbà tí o bá ti kóòdù rẹ sí GitHub, ìwọ yíò rí ìbéèrè fún orúkọ aṣàmúlò àti ọ̀rọ̀ aṣínà GitHub rẹ (bóyá nínú fèrèsé ìlà ìpàṣẹ náà tàbí nínú fèrèsé aṣẹ́yọsókè kan), àti pé lẹ́yìn títẹ àwọn ohun-ẹ̀rí, ó yẹ kí o rí nnkan kan báyìí:

{% filename %}command-line{% endfilename %}

    Counting objects: 6, done.
    Writing objects: 100% (6/6), 200 bytes | 0 bytes/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To https://github.com/ola/my-first-blog.git
    
     * [new branch]      master -> master
    Branch master set up to track remote branch master from origin.
    

<!--TODO: maybe do ssh keys installs in install party, and point ppl who dont have it to an extension -->

Kóòdù rẹ ti wà lórí GitHub ní báyìí. Lọ síbẹ̀ kí o ṣàyẹ̀wò rẹ̀! Ìwọ yíò ri pé ó wà ní ibi tó dáa – [Django](https://github.com/django/django), [Django Girls Tutorial](https://github.com/DjangoGirls/tutorial) náà, àti ọ̀pọ̀lọpọ̀ àwọn iṣẹ́ ńláńlá mìíràn tó jẹ́ ètò orísun gbangba máa n pèsè kóòdù wọn sórí GitHub. :)

# Setting up our blog on PythonAnywhere

## Forúkọ sílẹ̀ fún account PythonAnywhere kan

> **Àkíyèsí** Ó ṣeéṣe kí o ti ṣẹ̀dá account PythonAnywhere kan tẹ́lẹ̀ lásìkò àwọn ìgbésẹ̀ ìṣàgbékalẹ̀ náà – tó bá rí bẹ́ẹ̀, kò sídìí láti tún ṣe é mọ́.

{% include "/deploy/signup_pythonanywhere.md" %}

## Configuring our site on PythonAnywhere

Go back to the main [PythonAnywhere Dashboard](https://www.pythonanywhere.com/) by clicking on the logo, and choose the option to start a "Bash" console – that's the PythonAnywhere version of a command line, just like the one on your computer.

![Abala 'New Console' náà lórí atọ́kùn ayélujára PythonAnywhere, pẹ̀lú bọ́tìnnì kan fún 'bash'](images/pythonanywhere_bash_console.png)

> **Note** PythonAnywhere is based on Linux, so if you're on Windows, the console will look a little different from the one on your computer.

Deploying a web app on PythonAnywhere involves pulling down your code from GitHub, and then configuring PythonAnywhere to recognise it and start serving it as a web application. There are manual ways of doing it, but PythonAnywhere provides a helper tool that will do it all for you. Let's install it first:

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ pip3.6 install --user pythonanywhere
    

That should print out some things like `Collecting pythonanywhere`, and eventually end with a line saying `Successfully installed (...) pythonanywhere- (...)`.

Now we run the helper to automatically configure our app from GitHub. Type the following into the console on PythonAnywhere (don't forget to use your GitHub username in place of `<your-github-username>`, so that the URL matches the clone URL from GitHub):

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ pa_autoconfigure_django.py https://github.com/<your-github-username>/my-first-blog.git
    

As you watch that running, you'll be able to see what it's doing:

- Downloading your code from GitHub
- Creating a virtualenv on PythonAnywhere, just like the one on your own computer
- Updating your settings file with some deployment settings
- Setting up a database on PythonAnywhere using the `manage.py migrate` command
- Setting up your static files (we'll learn about these later)
- And configuring PythonAnywhere to serve your web app via its API

On PythonAnywhere all those steps are automated, but they're the same steps you would have to go through with any other server provider.

The main thing to notice right now is that your database on PythonAnywhere is actually totally separate from your database on your own computer, so it can have different posts and admin accounts. As a result, just as we did on your own computer, we need to initialize the admin account with `createsuperuser`. PythonAnywhere has automatically activated your virtualenv for you, so all you need to do is run:

{% filename %}PythonAnywhere command-line{% endfilename %}

    (ola.pythonanywhere.com) $ python manage.py createsuperuser
    

Type in the details for your admin user. Best to use the same ones as you're using on your own computer to avoid any confusion, unless you want to make the password on PythonAnywhere more secure.

Now, if you like, you can also take a look at your code on PythonAnywhere using `ls`:

{% filename %}PythonAnywhere command-line{% endfilename %}

    (ola.pythonanywhere.com) $ ls
    blog  db.sqlite3  manage.py  mysite requirements.txt static
    (ola.pythonanywhere.com) $ ls blog/
    __init__.py  __pycache__  admin.py  apps.py  migrations  models.py
    tests.py  views.py
    

You can also go to the "Files" page and navigate around using PythonAnywhere's built-in file browser. (From the Console page, you can get to other PythonAnywhere pages from the menu button in the upper right corner. Once you're on one of the pages, there are links to the other ones near the top.)

## You are now live!

Your site should now be live on the public Internet! Click through to the PythonAnywhere "Web" page to get a link to it. You can share this with anyone you want :)

> **Note** This is a beginners' tutorial, and in deploying this site we've taken a few shortcuts which aren't ideal from a security point of view. If and when you decide to build on this project, or start a new project, you should review the [Django deployment checklist](https://docs.djangoproject.com/en/2.0/howto/deployment/checklist/) for some tips on securing your site.

## Debugging tips

If you see an error while running the `pa_autoconfigure_django.py` script, here are a few common causes:

- Forgetting to create your PythonAnywhere API token.
- Making a mistake in your GitHub URL
- If you see an error saying *"Could not find your settings.py"*, it's probably because you didn't manage to add all your files to Git, and/or you didn't push them up to GitHub successfully. Have another look at the Git section above

If you see an error when you try to visit your site, the first place to look for some debugging info is in your **error log**. You'll find a link to this on the PythonAnywhere ["Web" page](https://www.pythonanywhere.com/web_app_setup/). See if there are any error messages in there; the most recent ones are at the bottom.

There are also some [general debugging tips on the PythonAnywhere help site](http://help.pythonanywhere.com/pages/DebuggingImportError).

And remember, your coach is here to help!

# Ṣàyẹ̀wò ààyè rẹ!

The default page for your site should say "It worked!", just like it does on your local computer. Try adding `/admin/` to the end of the URL, and you'll be taken to the admin site. Log in with the username and password, and you'll see you can add new Posts on the server -- remember, the posts from your local test database were not sent to your live blog.

Once you have a few posts created, you can go back to your local setup (not PythonAnywhere). From here you should work on your local setup to make changes. This is a common workflow in web development – make changes locally, push those changes to GitHub, and pull your changes down to your live Web server. This allows you to work and experiment without breaking your live Web site. Pretty cool, huh?

Give yourself a *HUGE* pat on the back! Server deployments are one of the trickiest parts of web development and it often takes people several days before they get them working. But you've got your site live, on the real Internet!