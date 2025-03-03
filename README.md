#Two-panel Slate Template

Welcome to the Two-panel Slate Template. A template based on the [Official Dracula Slate Template](https://github.com/dracula/slate).
Use this template to create a static site for documentation such as:

* User Guides
* Information Sites
* API Reference Documentation


The following list shows the sections on this site:

* [Getting Started](#getting-started)
* [Adding a New Page to the Static Site](#adding-a-new-page-to-the-static-site)
* [API Reference Documentation Example](#api-reference-documentation-example)


# Getting Started
Slate is an open source tool to create static sites for documentation. To use Slate, you need to know Markdown Syntax to create the static sites documentation files. 
To know more about Markdown Syntax in this template, see the [Basic Syntax](#basic-syntax) section.

To work with this Slate template, you need the following requirements:

* Docker Desktop


## Configuring Slate in your computer
You must first install the Slate Docker image on your computer before workin on your documentation. 
To install the Slate Docker image on your computer follow these steps:

<aside class="notice"> You have to do this procedure once. 
</aside>

1. Install Docker Desktop on your computer.
2. Open a terminal window on your computer.
3. Locate your terminal in the folder of your static site.
4. Run the following command to pull the most recent image of Slate. It might take some minutes depending on your internet bandwidth:
</br>`docker pull slatedocs/slate`

<aside class="success"> After following the preceding steps, you have successfully installed the Slate Docker image on your computer.
</aside>

You can create a local environment for your static sites to help you view them before deploying your changes to the live version. 
To create a local environment for a static site, follow these steps:

1. Open a terminal window on your computer.
2. Locate your terminal in the folder of your static site.
3. Create the docker container for your local environment, use the following command:
</br>`docker run --name your-site-slate-preview -p 4567:4567 --volume="$(pwd)/source:/srv/slate/source" slatedocs/slate serve`
4. See your static site in the address http://localhost:4567/ .

<aside class="success"> After following the preceding steps, you have successfully created the Docker container for your static site.
</aside>

## Understanding Slate Files
Your project Slate folder contains various files for the functionality of the static site. Each file controls a different aspect of the static site, the following list shows the Slate files and their description:

* **Source folder:** Contains the files to edit. The files are divided into the following folders: 
* **Fonts:** Contains the Web Open Font Format files (WOFF2) to the text font of the static site.
* **Images:** Contains the images used in the static site, such as the favicon and sample images. 
* **Includes:** Contains the markdown files with the information displayed in the static site. Files in this folder can be one of the following types: 
* **.md files:**  Files that contain only text.
* **.md.erb files:** Files that contain text and images. 
* **Javascripts:** Contains the JavaScript files to give the static site its dynamic search and appearance. 
* **Layouts:** Contains the .erb files that fix the layout appearance of the static site.
* **Stylesheets:** Contains the CSS files to change the appearance of the static site.
* **Index.html.md.erb:** Is the main file of the static site. Defines the structure of the documentation. 


## Basic Syntax
Use Markdown to add information to the pages of your site.

### Lists
Lists can be:

* Numbered: For instructions or procedures.
* Unnumbered: For lists in general.

This is how to add lists.

#### numbered
this is how it looks in your code:

```
1.  Item 1
2.  Item 2
3.  Item 3
```

This is how it looks on your static site:

1.  Item 1
2.  Item 2
3.  Item 3

#### unnumbered
this is how it looks in your code:

```
* Another item
* Another item
```

This is how it looks on your static site:

* Another item
* Another item

### Code Blocks
Code blocks appear after the instructions where you added them. Specify the code language at the beginning of the block.

This is a JavaScript code block:

```javascript
function copyToClipboard(container) {
  const el = document.createElement('textarea');
  el.value = container.textContent.replace(/\n$/, '');
  document.body.appendChild(el);
  el.select();
  document.execCommand('copy');
  document.body.removeChild(el);
}

function setupCodeCopy() {
  $('pre.highlight').prepend('<div class="copy-clipboard"><svg xmlns="http://www.w3.org/2000/svg"></div>');
  $('.copy-clipboard').on('click', function() {
    copyToClipboard(this.parentNode.children[1]);
  });
}
```

This is a CSS code block:

```css
// BACKGROUND COLORS
////////////////////
$nav-bg: #2E3336 !default;
$examples-bg: #2E3336 !default;
$code-bg: #1E2224 !default;
$code-annotation-bg: #191D1F !default;
$nav-subitem-bg: #1E2224 !default;
$nav-active-bg: #0F75D4 !default;
$nav-active-parent-bg: #1E2224 !default; // parent links of the current section
$lang-select-border: #000 !default;
$lang-select-bg: #6d7375 !default;
$lang-select-active-bg: $examples-bg !default; // feel free to change this to blue or something
$lang-select-pressed-bg: #111 !default; // color of language tab bg when mouse is pressed
$main-bg: #F3F7F9 !default;
$aside-notice-bg: #8fbcd4 !default;
$aside-warning-bg: #c97a7e !default;
$aside-success-bg: #6ac174 !default;
$search-notice-bg: #c97a7e !default;
```

### API Words
You can add a design to the verbs of API endpoints with the class `verb-endpoint-word` , as in the following example:

this is how it looks in your code:

```html
<a class="get-enpoint-word" href="link-to-your-endpoint"> GET </a> /PROJECTS/{PROJECT}
<a class="post-enpoint-word" href="link-to-your-endpoint"> POST </a> /PROJECTS/{PROJECT}
<a class="put-enpoint-word" href="link-to-your-endpoint"> PUT </a> /PROJECTS/{PROJECT}
<a class="delete-enpoint-word" href="link-to-your-endpoint"> DELETE </a> /PROJECTS/{PROJECT}
```

This is how it looks on your static site:

<a class="get-endpoint-word" href="link-to-your-endpoint">GET</a> /PROJECTS/{PROJECT}

<a class="post-endpoint-word" href="link-to-your-endpoint">POST</a> /PROJECTS/{PROJECT}

<a class="put-endpoint-word" href="link-to-your-endpoint">PUT</a> /PROJECTS/{PROJECT}

<a class="delete-endpoint-word" href="link-to-your-endpoint"> DELETE </a> /PROJECTS/{PROJECT}

### Notes
This template has three notice notes, this is their syntax:

```html
<aside class="success"> This is a success note. </aside>
<aside class="notice"> This is an information note. </aside>
<aside class="warning"> This is a warning note. </aside>
```
And this is how they look in your static site:

<aside class="success"> This is a success note. </aside>
<aside class="notice"> This is an information note. </aside>
<aside class="warning"> This is a warning note. </aside>


For further information about Markdown Syntax, see the [Markdown Org. Basic Syntax Guide](https://www.markdownguide.org/basic-syntax/).

# Adding a New Page to the Static Site
To add a new information section, follow these steps:

1. Open the **`includes`** folder of your static site folder.
2. Create a new file for your information section:
</br>a. Create a **`.md file`** for an only text section.
</br>b. Create a **`.md.erb`** for a text and images section. 
3. Open the file in your favorite File Editor Program.
4. Edit the file with the information you need to upload, follow the Markdown Syntax.
5. Save your changes.
6. Open the **`index.html.md.erb`** file
7. In the includes section of the file, add the name of your file as in the example below:

    ```html
    includes:
      - overview.md.erb
      - the-name-of-your-file.md
    ```

8. Save the changes to the file.


<aside class="success"> After following the preceding steps, you have successfully added a section to your static site.
</aside>




