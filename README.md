# trouble_graphics
Graphics for trouble game

The files in the root (**/**) folder are **Inkscape svgs**, they have a lot of extra stuff thrown in for editing with Inkscape.
The files in the **/svg** folder are **plain svgs** for use in the actual web client (after additional processing). 

## Updating an inline svg
The process for creating an inline svg graphic is a bit complicated. If these steps aren't followed React will not compile the graphic.
* Make changes to original (root folder) in editor (Inkscape).
* Export a plain SVG to the **/svg** folder. 
* Run the plain SVG through [SVGOMG](https://jakearchibald.github.io/svgomg/) using these settings
    * Remove doctype
    * Remove XML instructions
    * Remove Metadata
    * Remove xmlns
    * Remove editor data 
    * Style to attributes
    * Remove unknowns and defaults
    * Remove unused namespaces
    * **Make sure Clean IDs is OFF** - otherwise the space id's will be removed.
* Copy the code into the React Component (See the Board file in the trouble_client) 
* Change kebab case attributes to camel case. Things like line-height need to be changed to lineHeight.
* Resolve additional React errors. Try to compile the client app and fix any additional errors.