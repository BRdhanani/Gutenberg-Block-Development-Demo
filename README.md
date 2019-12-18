# Gutenberg Block Development Demo

This code helps you in the development of custom gutenberg blocks from scratch. I am using ES6 and JSX in my code so you need to install npm. If you are using ES5 then you don't need to install npm. I ap prefering ES6 concept because it is simple as compare to ES5 and it gives you freedom to write both javascript and html code at the same time using the concept of JSX. If you want create gutenberg block using ES6 then simply follow below steps for creating your first beautiful gutenberg block.

If you are using any default theme of wordpress like twentynineteen then there will be one file named package.json but if you are using any custom theme then you need to generate package.json first. 

**package.json** is a file which is mainly used to store the metadata associated with your project. It is also used to store the list of dependency packages. If you want to add any package in your project then you need to create package.json file. 

## Create package.json file
To create package.json file, first of all move to your theme's root directory and run following command.
```
npm init
```
After running above command it will prompt some question. Answer all the questions and that's it . You have successfully generated your packge.json file. You can see it inside your theme's root directory.

## Install NPM
 Move to your theme's root direcoty and run following command. 
```
npm install
```
After running this command you can see one folder named node_modules added inside your theme's root directory which contains all the required packages and modules.

## Create build and src folder
After installation completed, create one folder named **src** inside your theme's root directory and add your js file inside it.
**Note** : It is required to name your js file as index.js as react starts rendering all the components from index.js file.

Add one another folder named **build** inside your theme's root directory. </br>
**Note** : Don't add any files now inside build folder as it will automatically add minified version of your index.js file when run npm build command.

## Edit your package.json file 
Now, open your package.json file and add following line inside scripts array.
```
"build:scripts": "wp-scripts build"
```
This will simply starts building your script when you fires ``` npm run build:scripts ```   command and adds minified version of your index.js file inside build folder which you created previously.

## Create Required Files
Now, our real work starts. Create following files
- index.php
- index.js

**index.php**
You can create this file wnywhere you want and include it in your theme's functions.php file. In index.php file you need to create one function in which you need to register your script first using ``` wp_register_script ``` function and add one another function named ``` register_block_type ``` which contains your namespace as a first parameter and array of scripts as a second parameter.

**index.js**
In js file you can write code for all the custom blocks you want to add inside default function named registerBlockType. you also need to import some packges from wordpress before you start writing any codes.

## Run NPM
After you have write your code for your first custom gutenberg block then you need to run command for running your script using following command.
``` npm start-build ```
After running this command your scripts will start building and you can see message like ``` wp-scripts start ``` as shown in screenshot below.

![Desktop screenshot](https://user-images.githubusercontent.com/46484569/70032658-e572a500-15d3-11ea-9f0e-5e5c57f52c0b.png)

Now, open your posts section and click on add block in left top and search for your custom block. add some content inside it and save it. after saving your post view post and you can see your first custom block there.
