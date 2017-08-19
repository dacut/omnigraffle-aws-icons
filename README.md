# OmniGraffle stencil library for AWS Simple Icons
This is a version of the [AWS Simple Icons](https://aws.amazon.com/architecture/icons/) library for OmniGraffle users (like me).

Most OmniGraffle users will just want to download the ZIP bundle containing all of the icons:
https://ionosphere.io/dist/omnigraffle-aws-icons.zip

# Editing the icons
The stencils were imported from the Visio version of the icons, then hand-edited to make the layout more usable. (For some reason, OmniGraffle likes to spread them out randomly when importing.)

## Guidelines for importing a new library
1. Import the Visio 2013 .vssx file.
2. Set the canvas grid to 4 divisions per inch and enable snap to grid.
3. Create guidelines (horizontal and vertical) starting at 3/4" from the origin, then every 1 1/4" thereafter: 3/4", 2", 3 1/4", 4 1/2", 5 3/4", 7", 8 1/4", 9 1/2", ...
4. Disable snap to grid.
5. Select all, then ungroup.
6. Align each icon's centerpoints on the gridlines, then put the label underneath.
  * Sometimes an icon will have a blank placeholder behind it. Delete it if present.
  * Vertically align the labels in a row.
7. Create a visual/usability balance between the following constraints (which sometimes conflict):
  * Service icons should be on the leftmost column.
  * Resource icons should not use the first column.
  * Services without resource icons should be grouped in a single row at the bottom.
  * Alphabetize services and resources.
  * Put more commonly used services first.

## Commiting changes
We don't use OmniGraffle's native format since it creates unusable diffs. Instead, we extract the raw XML from the OmniGraffle stencil and commit that instead.

Fortunately, this is easy: OmniGraffle's stencil format is just a directory named *stencil_name*.gstencil containing a gzipped XML file named data.plist (which, as you might guess, is in Apple's plist format). The `xml-to-stencil` and `stencil-to-xml` tools convert between them.
