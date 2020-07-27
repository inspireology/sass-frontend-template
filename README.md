This is my custome SASS file structure. It is designed to scale with complexity but to be less complicated than BEM..
The initial layout is 6 files. 

# Base Structure

- **base.scss**:
    The fundamental style definitions of the page
    fonts, colors, constants, background images. 

- **elements.scss**:
    The styling of page elements such as buttons

- **library.scss**:
    Custome written mixins for the project styling.

- **layout.scss**:
    Layouts for the individual pages. 
    This is the only place responsive rules should be defined. This makes it a certainty as to where responsive behavior is coming from.

- **vendor.scss**:
    Custom SASS libraries (such as css reset rules) that are included from other authors. Nothing here should be written by you.

- **main.scss**:
    The entry point where the various files are included. There shouldn't be any need to put anything in this file. 

## Include Order in main.scss
Each file in main.scss should be included in this following order: 

- vendor.scss
- library.scss
- base.scss
- elements.scss
- layout.scss

The purpose of this layout is for before you start writing base.scss all of the libararies and custom written mixins are available for the code you will write.

Once base.scss has defined the custom colors, fonts, constants etc page elements can be defined. Once elements are defined, the layout can constructed from a combination of the elements

## Organizing Rules Within the Files
In base.css it makes sense to divide the stylesheet up in to sections that are responsible for separate things. I would divine base.css up in to parts with headings:

- fonts
- constants
- sizes
- colors

# Project Scaling
As your project grows, it might become quite messy to have files with so much code if the project is really big. 

At this point, the the file can be made in to a folder with each section heading becoming its own file as needed. The elements.scss file would become its own directory:

- elements
    * _index.scss (optional)
    * _headers.scss
    * _buttons.scss
    * _footers.scss

The individual files can be included in main.scss.

## Dependencies Inside of Folders
There should never be dependencies between the individual files inside of a folder. The optional _index.scss file should contain any dependencies. The index.scss file should then be included in main.scss. 

# Build
sass --watch simple/:css/
sass --watch complex/:css/

