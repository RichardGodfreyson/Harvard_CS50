# Lecture 0

## Git

- To create a git repository
  - create it first on GitHub
  - use ```git clone <url_link>``` to clone the repository into local

- To stage the file into a temporary stage before commiting
  - ```git add <filename>```
  - If alright, nothing will pop up
- To commit
  - ```git commit -m "<message>"```
  - the ```-m``` indicates message
  - insertions indicate number of lines

```bash
[master (root-commit) 5fd2a64] Added hello.html
 1 file changed, 10 insertions(+)
 create mode 100644 hello.html
```

- ```git status```
  - current status of the git repository
  - "Nothing to commit" means that the version is up to date
  
```bash
On branch master
Your branch is based on 'origin/master', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean
```

- ```git push``` stores the local repository in a remote server (in this case GitHub)
- ```git pull``` restores the online version of the repository
- Github webpage can edit the code
- Merge Conflicts
  - conflicts occur when local and remote changes are different
  - Git will try to solve that automatically
  - But if same lines are changed, merge conflicts occur
  - In the file, it will look something like the following
  - between ```<<<<``` and ```====``` are the local changes
  - between ```====``` and ```>>>>``` are the remote changes
  - The line of hexdigits are the conflicting commit hash number
  - to solve conflicts, change the lines that are not needed

![Merge Conflict](merge_conflict.PNG)

- ```git log``` show the history of commits
  - each commit is marked by a commit hash
- ```git reset``` reset version
  - ```git reset --hard <commit_hash>``` resets the repository to a specific commit
  - ```git reset --hard origin/master``` resets the repository to GitHub version
- ```git add``` puts files in a staging area
- ```git reflog``` shows the other commits that may have been reset

## HTML

```html
<!DOCTYPE html>
<html>

  <head>
    <title>My Webpage</title>
  </head>

  <body>Hello World!</body>

</html>
```

- ```<!DOCTYPE html>``` suggest html5
- ```<html>``` is a tag that indicates start
- ```</html>``` is a tag that indicates end
- head is usually metadata that is not really displayed
- title tag indicates the title
- heading tags
  - e.g. ```<h1>``` is the largest heading all the way to ```<h6>```
- lists
  - unordered list: ```<ul>```
  - list item: ```<li>```
  - ordered list: ```<ol>```
- images
  - ```<img src="path/to/image.jpg">```
  - no ending tags
  - ```src``` is an html attribute
  - this can also be a link
  - ```<img src="path/to/image.jpg" height="200" width="300">```
  - can change the dimensions of the image
  - can put dimensions as ```width="50%"```, which specifies the proportion in the page
- tables
  - table tag: ```<table>```
  - table row: ```<tr>```
  - table headers: ```<th>```
  - table data: ```<td>```
- form
  - for users to input data
  - form: ```<form>```
  - input: ```<input>``` no closing tags
  - e.g. ```<input type="text" placeholder="Full Name" name="name">```
  - button: ```<button>```
- divs and spans
  - divs: vertical boxes that label a part of the page
  - spans: used to group inline-elements in a document
  - no specific use but benefits styling

## CSS

- Styles the HTML

```html
<h1 style="color:blue;text-align:center;"> Welcome to my Website</h1>
```

- the style attribute changes the format
- colors expressed in words or RGB values. e.g. `#0c8e05`
- or can seperate style specifications in the `style` tag in the header

```html
<style>
  h1 {
    color: blue;
    text-align: center;
  }
</style>
```

- CSS can be in a separated file
- e.g. `<link rel="stylesheet" href="styles.css">`

- common CSS properties
  - color
  - text-align
  - background-color
  - width
  - height
  - margin: the space around the outside of the box
  - padding: the spacing around the inside the box
  - font
    - font-family
      - e.g. `Arial, sans-serif`
      - include multiple fonts in case users do not have the first font
    - font-size: height of the letters
    - font-weight: e.g. bold
  - border: the lines around a `<div>`
    - e.g. `border: 3px solid blue`
- id and classes
  - id: attribute that uniquely identifies a section in the webpage
  - class: attribute that can identify multiple elements
  
```html
<div id="top">
  <p>
    something <span class="name"> something </span> ahahaha
  </p>
</div>
```

```css
#top {
  font-size=24px
}

.name {
  font_weight: bold
}
```

- Conflicts in CSS descriptions: generally will default picking the more specific description / more local

## Deploying a Website

- Github Pages can deploy htmls
