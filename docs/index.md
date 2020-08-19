--- 
title: "A Test Bookdown Book"
author: "Philippe Grosjean & Guyliann Engels"
date: "2020-08-19"
site: bookdown::bookdown_site
output:
  bookdown::gitbook:
    info: yes
    includes:
      in_header: header.html
      after_body: footer.html
documentclass: book
bibliography: [book.bib, packages.bib]
biblio-style: apalike
link-citations: yes
github-repo: phgrosjean/bookdown-test
url: 'http\://phgrosjean.sciviews.org/bookdown-test/'
description: "Template for a learndown-enhanced bookdown document."
cover-image: "images/front-cover.png"
---

# Preamble {-}

<!-- Compile the bibliography from different sources -->



<!-- Diagnose the user login status, example in English and in French -->

Information about connected user build be {learndown} automatically:


::: {.info}

::: {#diagnostic-en}

*Please wait, diagnostic in course...*

<script>
function clearStorageEn() {
  if (window.localStorage) {
    localStorage.clear();
  }
  var msg = 'Local personal data deleted!' + '\nThe page will be reloaded...' + '\n\n(if this is an error, close the page and relaunch it from within Moodle).';
  if (window.self !== window.parent) {
    parent.alert(msg);
  } else {
    window.alert(msg);
  }
  window.location.href=window.location.href;
}

function diagnoseSystemEn() {
  var container = document.getElementById('diagnostic-en');
  if (container === null) {
    return;
  }
  var content = '';

  if (!window.localStorage) {
    content = content + "<p>You are:</p>\n<ul>";
    content = content + "\n<li>Anonymous on this site (local storage unavailable).</li>";
    content = content + "\n<li>The content <b>is not</b> contextualized for a particular course.</li>";
    content = content + "\n<li>Results for various exercises <b>will not be recorded</b>.</li>";
    content = content + "\n</ul>";
    content = content + "\n<p>If you are <i>not</i> a student that takes a course linking with this pedagogical material, this is OK, you can continue your journey... <b>Welcome!</b></p>";
    content = content + "\n<p>On the other hand, if your cursus requires you to be properly recorded here, then close this page and restart it from your institution elearning platform (Moodle, ...). If your data are still incorrect, contact your teachers.</p>";

  } else {
    // Explore the content of the storage
    // Students are recognized by iemail (institutional email, or Wordpress email)
    // but possibly, their login could be used too
    var login = localStorage.getItem('login');
    if (login === null) {
      login = '';
    }
    var email = localStorage.getItem('email');
    if (email === null) {
      email = '';
    }
    var iemail = localStorage.getItem('iemail');
    if (iemail === null) {
      iemail = '';
    }
    // Compare both emails, if they are different, display both of them
    if (email != iemail && iemail != '') {
      email = email + '</u> (institutional email: <u>' + iemail + ')';
    }

    // Construct an identification string
    content = content + "<p><b>Content on these pages is contextual. </b>Please, check the following data are correct:</p>\n<ul>";

    var registered = false;
    if (email == '' && login == '') {
      // Not registered
      content = content + "\n<li><u>You are anonymous on this site.</u> <b>Your progress in the exercises will not be recorded.</b></li>";

    } else {
      // Registered user
      registered = true;
      if (login != '') {
        content = content + "\n<li>Login&nbsp;: <u>" + login + "</u></li>";
      }
      if (email != '') {
        content = content + "\n<li>Email&nbsp;: <u>" + email + "</u></li>";
      }
      content = content + "\n<b>Your progress in the exercises will be recorded under that identity.</b>";
    }

    // institution and icourse possibly change the content. So, must be checked!
    var context = false;
    var institution = localStorage.getItem('institution');
    if (institution == null || institution == '') {
      institution = 'undefined';
    } else {
      context = true;
    }
    var icourse = localStorage.getItem('icourse');
    if (icourse == null || icourse == '') {
      icourse = 'undefined';
    } else {
      context = true;
      var ictitle = localStorage.getItem('ictitle');
      if (ictitle != null && ictitle != '') {
        icourse = ictitle + ' (' + icourse + ')';
      }
    }
    content = content + "\n<li>Course&nbsp;: <u>" + icourse + "</u></li>";
    content = content + "\n<li>Institution&nbsp;: <u>" + institution + "</u></li>";
    content = content + "\n</ul>";
    if (context) {
      content = content + "<p><b>Content will be adapted to this particular context. </b>Check that these data are correct, or close this page and reopen it from your institutional elearning platform (Moodle, ...). If your data are still incorrect, contact your teachers.</p>";
    } else {// No context
      content = content + "<p><b>Without a particular course context, you will see a general content. </b>If this is OK... Welcome! Otherwise close this page and restart it from your institutional elearning platform (Moodle, ...). If your data are still incorrect, contact your teachers.</p>";
    }

    // If registered user and/or special context, offer to reset it
    if (registered || context) {
      content = content + "\n<p>If you prefer to visit this site anonymously and record no activity in the exercises, you can delete your personal informations by clicking on the button bellow.</p>";
      content = content + '<button onclick="clearStorageEn()">Delete my personal data</button>';
    }
    // Those variables are possibly defined, but they are not tested here (yet)
    //var displayname = localStorage.getItem('displayname');
    //var firstname = localStorage.getItem('firstname');
    //var lastname = localStorage.getItem('lastname');
    //var ifirstname = localStorage.getItem('ifirstname');
    //var ilastname = localStorage.getItem('ilastname');
    //var iid = localStorage.getItem('iid');
    //var iurl = localStorage.getItem('iurl');
    //var iref = localStorage.getItem('iref');
  }

  container.innerHTML = content;
}
diagnoseSystemEn();
</script>
<noscript><b>The system diagnostic cannot be run because Javascript is not enabled, but it is mandatory for thei site! All the interactive and contextual content will be unusable. Please, do activate Javascript...</b></noscript>

:::
:::



The same one in French\ :


::: {.info}

::: {#diagnostic-fr}

*Patientez s'il-vous-plait, diagnostic en cours...*

<script>
function clearStorageFr() {
  if (window.localStorage) {
    localStorage.clear();
  }
  var msg = 'Informations personnelles locales effacees !' + '\nLa page va etre rechargee...' + "\n\n(s'il s'agit d'une fausse manoeuvre, fermer la page et relancez-la depuis Moodle).";
  if (window.self !== window.parent) {
    parent.alert(msg);
  } else {
    window.alert(msg);
  }
  window.location.href=window.location.href;
}

function diagnoseSystemFr() {
  var container = document.getElementById('diagnostic-fr');
  if (container === null) {
    return;
  }
  var content = '';

  if (!window.localStorage) {
    content = content + "<p>Vous &ecirc;tes&nbsp;:</p>\n<ul>";
    content = content + "\n<li>Anonyme sur ce site (stockage local indisponible).</li>";
    content = content + "\n<li>Le contenu <b>n'est pas</b> contextualis&eacute; par rapport &agrave; un cours en particulier.</li>";
    content = content + "\n<li>Le r&eacute;sultat de certains exercices <b>ne sera pas enregistr&eacute;</b>.</li>";
    content = content + "\n</ul>";
    content = content + "\n<p>Si vous n'&ecirc;tes <i>pas</i> un &eacute;tudiant qui suit un cours li&eacute; &agrave; ce mat&eacute;riel p&eacute;dagogique, c'est normal, vous pouvez continuer votre visite... <b>Bienvenue&nbsp;!</b></p>";
    content = content + "\n<p>En revanche, si votre cours n&eacute;cessite que vous soyez d&ucirc;ment enregistr&eacute;, alors fermez cette page et relancer-l&agrave; depuis le syst&egrave;me d'apprentissage en ligne de votre Universit&eacute; (Moodle, ...). Si les donn&eacute;es sont toujours incorrectes, contactez vos enseignants.</p>";

  } else {
    // Explore the content of the storage
    // Students are recognized by iemail (institutional email, or Wordpress email)
    // but possibly, their login could be used too
    var login = localStorage.getItem('login');
    if (login === null) {
      login = '';
    }
    var email = localStorage.getItem('email');
    if (email === null) {
      email = '';
    }
    var iemail = localStorage.getItem('iemail');
    if (iemail === null) {
      iemail = '';
    }
    // Compare both emails, if they are different, display both of them
    if (email != iemail && iemail != '') {
      email = email + '</u> (email institutionnel : <u>' + iemail + ')';
    }

    // Construct an identification string
    content = content + "<p><b>Le contenu de ce cours est contextuel.</b> V&eacute;rifiez les informations suivantes, s'il-vous-plait&nbsp;:</p>\n<ul>";

    var registered = false;
    if (email == '' && login == '') {
      // Not registered
      content = content + "\n<li><u>Vous &ecirc;tes anonyme sur ce site.</u> <b>Votre progression dans les exercices ne sera pas enregistr&eacute;e.</b></li>";

    } else {
      // Registered user
      registered = true;
      if (login != '') {
        content = content + "\n<li>Login&nbsp;: <u>" + login + "</u></li>";
      }
      if (email != '') {
        content = content + "\n<li>Email&nbsp;: <u>" + email + "</u></li>";
      }
      content = content + "\n<b>Votre progression dans les exercices sera enregistr&eacute;e sous cette identit&eacute;.</b>";
    }

    // institution and icourse possibly change the content. So, must be checked!
    var context = false;
    var institution = localStorage.getItem('institution');
    if (institution == null || institution == '') {
      institution = 'ind&eacute;termin&eacute;e';
    } else {
      context = true;
    }
    var icourse = localStorage.getItem('icourse');
    if (icourse == null || icourse == '') {
      icourse = 'ind&eacute;termin&eacute;';
    } else {
      context = true;
      var ictitle = localStorage.getItem('ictitle');
      if (ictitle != null && ictitle != '') {
        icourse = ictitle + ' (' + icourse + ')';
      }
    }
    content = content + "\n<li>Cours&nbsp;: <u>" + icourse + "</u></li>";
    content = content + "\n<li>Institution&nbsp;: <u>" + institution + "</u></li>";
    content = content + "\n</ul>";
    if (context) {
      content = content + "<p><b>Le contenu sera adapt&eacute; en fonction de ce contexte.</b> V&eacute;rifiez qu'il est correct, sinon fermez cette page et relancer-l&agrave; depuis le syst&egrave;me d'apprentissage en ligne de votre Universit&eacute; (Moodle, ...). Si les donn&eacute;es sont toujours incorrectes, contactez vos enseignants.</p>";
    } else {// No context
      content = content + "<p><b>N'&eacute;tant dans aucun contexte de cours particulier, vous n'aurez acc&egrave;s qu'&agrave un contenu g&eacute;n&eacute;raliste.</b> Si c'est ce que vous souhaitez... Bienvenue&nbsp;! Sinon, fermez cette page et relancer-l&agrave; depuis le syst&egrave;me d'apprentissage en ligne de votre Universit&eacute; (Moodle, ...). Si les donn&eacute;es sont toujours incorrectes, contactez vos enseignants.</p>";
    }

    // If registered user and/or special context, offer to reset it
    if (registered || context) {
      content = content + "\n<p>Pour explorer ces pages de mani&egrave;re anonyme et n'enregistrer aucune activit&eacute;, vous pouvez &eacute;liminez vos informations personnelles en cliquant sur le bouton juste ci-dessous.</p>";
      content = content + '<button onclick="clearStorageFr()">Effacer mes donn&eacute;es personnelles</button>';
    }
    // Those variables are possibly defined, but they are not tested here (yet)
    //var displayname = localStorage.getItem('displayname');
    //var firstname = localStorage.getItem('firstname');
    //var lastname = localStorage.getItem('lastname');
    //var ifirstname = localStorage.getItem('ifirstname');
    //var ilastname = localStorage.getItem('ilastname');
    //var iid = localStorage.getItem('iid');
    //var iurl = localStorage.getItem('iurl');
    //var iref = localStorage.getItem('iref');
  }

  container.innerHTML = content;
}
diagnoseSystemFr();
</script>
<noscript><b>Le diagnostic ne peut se terminer car Javascript ne fonctionne pas, or il est indispensable pour ce site ! Tout le contenu interactif et contextuel sera inutilisable. Veuillez activer Javascript, s'il-vous-plait...</b></noscript>

:::
:::



This is just a demo of the various possibilities of our {learndown}-extended bookdown format. It is intended to be used with the SciViews Box 2020.

![](images/front-cover.png)

----

_The content of this book is distributed under a [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.fr) license._

----

##### System information {-}


```{.r .hidden-code}
sessioninfo::session_info()
```

```
# ─ Session info ───────────────────────────────────────────────────────────────
#  setting  value                       
#  version  R version 3.6.3 (2020-02-29)
#  os       macOS Catalina 10.15.5      
#  system   x86_64, darwin15.6.0        
#  ui       X11                         
#  language (EN)                        
#  collate  en_US.UTF-8                 
#  ctype    en_US.UTF-8                 
#  tz       Europe/Brussels             
#  date     2020-08-19                  
# 
# ─ Packages ───────────────────────────────────────────────────────────────────
#  package     * version    date       lib source                            
#  assertthat    0.2.1      2019-03-21 [1] CRAN (R 3.6.0)                    
#  bookdown      0.18       2020-03-05 [1] CRAN (R 3.6.0)                    
#  cli           2.0.2      2020-02-28 [1] CRAN (R 3.6.0)                    
#  crayon        1.3.4.9000 2020-04-29 [1] Github (r-lib/crayon@dcf6d44)     
#  digest        0.6.25     2020-02-23 [1] CRAN (R 3.6.0)                    
#  evaluate      0.14       2019-05-28 [1] CRAN (R 3.6.0)                    
#  fansi         0.4.1      2020-01-08 [1] CRAN (R 3.6.0)                    
#  glue          1.4.0      2020-04-03 [1] CRAN (R 3.6.2)                    
#  htmltools     0.4.0.9003 2020-04-29 [1] Github (rstudio/htmltools@984b39c)
#  knitr         1.28       2020-02-06 [1] CRAN (R 3.6.0)                    
#  learndown     1.0.0      2020-08-18 [1] local                             
#  magick        2.4.0      2020-06-23 [1] CRAN (R 3.6.2)                    
#  magrittr      1.5        2014-11-22 [1] CRAN (R 3.6.0)                    
#  Rcpp          1.0.4.6    2020-04-09 [1] CRAN (R 3.6.2)                    
#  rlang         0.4.5      2020-03-01 [1] CRAN (R 3.6.0)                    
#  rmarkdown     2.1        2020-01-20 [1] CRAN (R 3.6.0)                    
#  sessioninfo   1.1.1      2018-11-05 [1] CRAN (R 3.6.0)                    
#  stringi       1.4.6      2020-02-17 [1] CRAN (R 3.6.0)                    
#  stringr       1.4.0      2019-02-10 [1] CRAN (R 3.6.0)                    
#  webshot       0.5.2      2019-11-22 [1] CRAN (R 3.6.0)                    
#  withr         2.2.0      2020-04-20 [1] CRAN (R 3.6.2)                    
#  xfun          0.13       2020-04-13 [1] CRAN (R 3.6.2)                    
#  yaml          2.2.1      2020-02-01 [1] CRAN (R 3.6.0)                    
# 
# [1] /Library/Frameworks/R.framework/Versions/3.6/Resources/library
```
