******************
Creating Frontends
******************

Local Cosmos offers you the possibility to create your own Frontend.

Structure of a Frontend
=======================
Your frontend needs to have the following directory structure:

::

    └── www
        ├── localcosmos
        ├── online_content
        │   └── templates
        ├── fact_sheets
        │   └── templates
        ├── locales
        │   └── LANGUAGE_CODE
        │       └── plain.js
        ├── webapp
        ├── android
        ├── ios
        └── settings.json


www folder
----------
The :code:`www` folder will later represent your Apache Cordova www folder, containing all files of your (web)app.


localcosmos folder
------------------
The localcosmos folder is the folder where the Local Cosmos App Kit will put all generated contents in.
Do not put anything into this folder by yourself, unless you are developing using test content.
During the build phase of your App on Local Cosmos, this folder will be deleted, recreated andu auto-populated

online_content folder
---------------------
If the user creates Online Content in the app Kit, he has to select a template for his content.
You supply those templates in the :code:`online_content` folder of your frontend.
Read `How to write Online Content and Fact Sheet templates`_ for more information on how to write templates.

fact_sheets folder
------------------
If the user creates Online Content in the app Kit, he has to select a template for his content.
You supply those templates in the :code:`fact_sheets` folder of your frontend.
Read `How to write Online Content and Fact Sheet templates`_ for more information on how to write templates.


locales folder
--------------
Contains translations of your apps texts. For each language, a folder using its LANGUAGE_CODE is required. Example:

::

    locales
    ├── de
    │   └── plain.js
    └── en
        └── plain.js

You only have to supply translations for button texts and such. The translations for the user-generated content like identification keys are made
within the App Kit, and are placed in the locale directories automatically during build.

webapp folder
-------------
Holds specific files only for the webapp version of your app.

android folder
--------------
Holds specific files ony for the android version of your app.

ios folder
----------
Holds specific files only for the ios version of your app.

settings.json
-------------

The settings file of your app. The settings.json file has two functions:
    1. it defines which content the user can upload for the Frontend component on the Local Cosmos App Kit
    2. During build, these settings are merged with settings provided by the Local Cosmos App Kit and then made available to your app at www/settings.json

**Example settings.json file**

.. code-block:: 

    {
        "frontend" : "FRONTEND_NAME",
        "version" : "0.1",
        "online_content" : {
            "verbose_template_names" : {
                "page/free_page.html" : {
                    "de" : "Freie Seite",
                    "en" : "Free Page"
                },
                "feature/news.html" : {
                    "de" : "News Eintrag",
                    "en" : "News entry"
                }
            },
            "max_flag_levels" : 2,
            "flags" : {
                "main_navigation" : {
                    "template_name" : "flag/main_navigation.html",
                    "name" : "Main Navigation"
                }
            }
        },
        "user_content" : {
            "images" : {
                "app_background" : {
                    "restrictions" : {
                        "file_type" : ["jpg","jpeg","png"],
                        "ratio" : "10:16"
                    },
                    "help_text" : "Ratio: 10:16. Will be displayed using the app or webapp on a smarthpone in portrait mode.",
                    "required" : false
                },
                "app_launcher_icon" : {
                    "restrictions" : {
                        "file_type" : ["svg"],
                        "ratio" : "1:1"
                    },
                    "help_text" : "Has to be an .SVG vector graphic AND the ratio must be 1:1. Will be displayed on your phones home screen to launch your app",
                    "required" : true
                },
                "app_pc_background" : {
                    "restrictions" : {
                        "file_type" : ["jpg","jpeg","png"],
                        "ratio" : "2:1"
                    },
                    "help_text" : "Will be displayed in the webapp using a pc",
                    "required" : false
                },
                "logo" : {
                    "restrictions" : {
                        "file_type" : ["svg"]
                    },
                    "help_text" : "Will be displayed on the apps main page",
                    "required" : true
                }
            },
            "texts" : {
                "about_app" : {
                    "required" : false,
                    "help_text" : "Describe your app"
                },
                "app_sources" : {
                    "required" : false,
                    "help_text" : "Sources you used to build this app."
                }
            }
        },
        "android" : {
            "launcher_icon" : {
                "type" : "user_content",
                "image_identifier" : "app_launcher_icon"
            },
            "splashscreen" : {
                "type" : "user_content",
                "image_identifier" : "app_splashscreen"
            }
        },
        "ios" : {
            "launcher_icon" : {
                "type" : "user_content",
                "image_identifier" : "app_launcher_icon"
            },
            "splashscreen" : {
                "type" : "user_content",
                "image_identifier" : "app_splashscreen"
            }
        }
    }

settings.online_content
^^^^^^^^^^^^^^^^^^^^^^^

settings.user_content
^^^^^^^^^^^^^^^^^^^^^

You can make your frontend configurable, so the app creator can choose a background, logo etc.

.. list-table::
   :widths: 50 50
   :header-rows: 1

   * - setting
     - description
   * - user_content.images
     - | Define the images which the app creator can upload using the App Kit. 
       | For example "background_image"
   * - user_content.texts
     - | Define the texts the app creator can create using the App Kit.
       | For example "about_app".
       | Do not add legal notice as this is automatically added by the App Kit as a requirement.



settings.android
^^^^^^^^^^^^^^^^

To successfully build an android app, several assets are required.

.. list-table::
   :widths: 50 50
   :header-rows: 1



   * - setting
     - description
   * - android.launcher_icon
     - The icon shown on the phone screen
   * - android.launcher_icon.type
     - | Currently, only "user_content" is supported.
       | This indicates, that the app creator has to upload the image using the Local Cosmos App Kit
   * - android.launcher_icon.image_identifier
     - A unique identifier for this image.
   * - android.splashscreen
     - The image shown during app start
   * - android.splashscreen.type
     - | Currently, only "user_content" is supported.
       | This indicates, that the app creator has to upload the image using the Local Cosmos App Kit
   * - android.splashscreen.image_identifier
     - A unique identifier for this image.



settings.ios
^^^^^^^^^^^^
see settings.android

Building a frontend with vue.js
===============================

Create a vue.js project
-----------------------
First we will create a folder which contains both the vue.js app and the apache cordova app.

.. code-block::

    mkdir lcfrontend
    cd lcfrontend

We will first create the vue.js app. Later, we will build it, and then move the build output to apache cordova.

.. code-block::

    npm init vue@latest

:code:`npm init` will ask you for several options. In this tutorial, we named the frontend: :code:`myfrontend-vue`, and this will be the vue.js project name.
You can choose whatever options you wish, but make sure to **add the vue.js router**. The command will create a new folder with the name of your project,
in this case :code:`myfrontend-vue`.

Next, run the following commands.

.. code-block::

    cd myfrontend-vue
    npm install
    npm run dev

Take a look at the default vue3 app in your browser to make sure everything has worked so far.


Turn the vue.js app into a Cordova app
--------------------------------------

Create the Cordova project
^^^^^^^^^^^^^^^^^^^^^^^^^^

First, install apache Cordova inside your :code:`lcfrontend` folder, not inside your :code:`myfrontend-vue` folder.

.. code-block::

    cd lcfrontend
    npm install cordova

of install cordova globally using

.. code-block::

    npm install -g cordova

In this tutorial, we assume Cordova is installed locally in :code:`lcfrontend`. If you choose to install it globally, you can use the
:code:`cordova` command directly and drop the :code:`node_modules/cordova/bin/` prefix for all commands.

Now, we will create a blank Cordova app. We use the name of the frontend, :code:`myfrontend`, for the cordova app:

.. code-block:: 

    cordova create myfrontend org.localcosmos.myfrontend MyFrontend

Cd into myfrontend, add the browser platform as well as the device plugin and run the cordova app.

.. code-block::

    cd myfrontend
    ../node_modules/cordova/bin/cordova platform add browser
    ../node_modules/cordova/bin/cordova plugin add cordova-plugin-device
    ../node_modules/cordova/bin/cordova build browser
    ../node_modules/cordova/bin/cordova run browser

Check your browser to make sure your blank Cordova app is working. You will see a green blinking **device is ready** area next to the Cordova logo.
This means, your app successfully listened to Cordovas :code:`deviceready` event. We will have to make our vue.js app listen to this event.


Copy cordova js over to your vue.js app
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
To turn your vue.js app into a Cordova app, copy the following to your vue.js app.

.. code-block ::

    cd lcfrontend
    cp myfrontend/platforms/browser/www/cordova.js myfrontend-vue/public
    cp myfrontend/platforms/browser/www/cordova_plugins.js myfrontend-vue/public
    cp -r myfrontend/platforms/browser/www/plugins myfrontend-vue/public
    cp -r myfrontend/platforms/browser/www/cordova-js-src js myfrontend-vue/public

You now have copied the files cordova creates during build over to your vue.js app.
These files will not be part of the frontend you upload to the Local Cosmos App kit later, but are required for development.

An alternative approach is to configure Vite to build directly into cordovas www folder and then use Cordovas commands to preview your app.

Update index.html
^^^^^^^^^^^^^^^^^
Update the file :code:`myfrontend-vue/index.html` by adding :code:`cordova.js`.

**myfrontend-vue/index.html:**

.. code-block::

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8" />
        <link rel="icon" href="/favicon.ico" />

        <meta http-equiv="Content-Security-Policy" content="default-src 'self' data: https://ssl.gstatic.com 'unsafe-eval'; style-src 'self' 'unsafe-inline'; media-src *; img-src 'self' data: content:;">
        <meta name="format-detection" content="telephone=no">
        <meta name="msapplication-tap-highlight" content="no">
        <meta name="viewport" content="initial-scale=1, width=device-width, viewport-fit=cover">

        <title>Vite App</title>
    </head>
    <body>
        <div id="app"></div>
        <script type="module" src="/src/main.js"></script>
        <script src="cordova.js"></script>
    </body>
    </html>


Listen to deviceready
^^^^^^^^^^^^^^^^^^^^^
We want our vue.js app to load after cordovas :code:`deviceready` event has been emitted.
This is a requirement for cordova apps to work properly.
Replace the content of :code:`myfrontend-vue/src/main.js` with the following content.

**myfrontend-vue/src/main.js:**

.. code-block:: 

    import { createApp } from 'vue'
    import App from './App.vue'
    import router from './router'

    import './assets/main.css'

    function onDeviceReady(event){

        console.log('Running cordova-' + cordova.platformId + '@' + cordova.version);

        const app = createApp(App)

        app.use(router)

        app.mount('#app')
    }

    document.addEventListener('deviceready', onDeviceReady, false);

To test if everythin worked, start your vite development server with

.. code-block:: 

    npm run dev

The vue.js default app should load, and you should find the following in the console output:

.. code-block:: 

    Running cordova-browser@6.0.0


Comply with the Local Cosmos frontend structure
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Up to now, we simply used the default vue.js app. We will have to alter the project structure to make it work with Local Cosmos.
Remember that Local Cosmos is not restricted to vue.js.
You can write frontends for Local Cosmos with any framework you want, or without using a framework at all.

First, we will creat eall necessary folders:

.. code-block:: 

    cd lcfrontend/myfrontend-vue
    cd public
    mkdir localcosmos
    mkdir online_content
    mkdir fact_sheets
    mkdir webapp
    mkdir android
    mkdir ios

Next, create the file :code:`settings.json` in :code:`myfrontend-vue/public`` and put the following into it.

.. code-block:: 

    {
        "frontend" : "MyFrontend",
        "version" : "0.1"
    }


Replace :code:`MyFrontend` with the name of your frontend.


Copy development data
^^^^^^^^^^^^^^^^^^^^^
Without data or content, you obviously cannot create a frontend. Download the localcosmos development data and put it into :code:`public/localcosmos`.


Configure vite to build for Cordova
-----------------------------------
First, we move cordovas default www folder to not lose it when vite builds.

.. code-block:: 

    cd lcfrontend/myfrontend
    mv www www_default


Next, we configure Vite to build directly into cordovas www folder.

Open `vite.config.js` and add the following to your config:

.. code-block:: 

    build : {
        outDir : '../myfrontend/www'
    } 


How to write Online Content and Fact Sheet templates
====================================================

APIs
====