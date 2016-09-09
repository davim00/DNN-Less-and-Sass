# DNN-Less-and-Sass
A small project to convert the DNN css stylesheets to Less and Sass. The [DNN Platform](https://github.com/dnnsoftware/Dnn.Platform) (formerly DotNetNuke Community Edition) is the most-used open source Microsoft .NET content management system in the world. This project is aimed at theme developers who are used to working with the css preprocessors Less and Sass and would like to be able to edit and merge the DNN default css files into their own css using these preprocessors.

## What are the Benefits?
Theme (skin) development in DNN is unlike many other CMS's in that the developer has to deal with the way the DNN admin system works. Instead of providing a seperate front-end (the UI) and back-end (administration), all administration tasks and page editing are done in the front-end. This is great for actually using the system, because in order to change something you literally browse to what needs to be changed, click an icon right on the page, and edit without leaving the website. For theme development, however, it becomes a challenge, because in order to properly render admin elements and styles, default css has to be loaded with all the pages on the site. This means that theme developers need to often override a lot of these default styles in their skin.css file in order for their theme to properly render on the site. By organizing the default css files into Less and Sass, theme developers used to working with these languages can easily make the necessary overrides using variables, mixins, etc. and subsequently compile the changes into their skin.css file.

## The Gameplan
* Organize [default.css](https://github.com/dnnsoftware/Dnn.Platform/blob/development/Website/Resources/Shared/stylesheets/dnndefault/8.0.0/default.css) into logical sections, such as typography, layout, tables, tabs, etc.
* Create logical variables for repeated property values present in default.css
* Identify properties and classes that would work as mixins
* Create skin.less with imports that order the logical sections, following the order of the original default.css file
* Create variables.less to hold all variables
* Create mixins.less along with typography.less, layout.less, tables,less, tabs.less, etc.
* When all Less files compile, the resulting skin.css file should be functionally identical to the original default.css file
* Repeat the process, creating Sass files instead of Less files. Sass files should compile into skin.css, which should be functionally identical to defaul.css

## History
### 8.0.4a (Alpha Release)
* Uses default.css from [DNN Platform 8.0.4](https://github.com/dnnsoftware/Dnn.Platform/releases/tag/v8.0.4)
