![Awesome Exporter](https://modocodo.com/hosted/awesome-exporter/awesome-exporter-logo.jpg)

## Welcome

Awesome Exporter for Adobe InDesign is used by studios, creative teams and businesses worldwide to enhance and automate the JPG, PDF, PNG, EPS, INDD and IDML file preparation and export process. The plugin offers an intuitive user interface, powerful selection query syntax and flexible template naming syntax.

Select pages, spreads, layouts and sections using attributes, styles and data, then name and export folders and files for production artwork, asset libraries, websites and multilingual files quickly and easily.

[Available From Adobe Creative Cloud Marketplace](https://adobe.com/go/cc_plugins_discover_plugin?pluginId=201251)

<br />

![Awesome Exporter Home USer Interface](https://modocodo.com/hosted/awesome-exporter/awesome-exporter-ui-main-window-01.png)
*Awesome Exporter Home User Interface*

<br /><br />

## Key Features

#### Range Selection
* Select pages, spreads, sections, layouts and layers by name, colour, attribute, style, content, references and standard ranges.
* Export design variations or multiple languages from a single InDesign document source using variable content and variable layers.
* Create auto-queries to dynamically build exports based on attributes, content or sequences.
* Use collections to build unique groups of exports from a single InDesign document source.

#### Naming & Templates
* Name exports using template tags which reference content and attributes.
* Create flexible tags using conditional statements and if/then connections to surrounding tags.
* Refine and fine-tune folder names and file names using modifier functions.

#### Export Formatting
* Export JPG, PDF, PNG, EPS, INDD and IDML files.
* Standard InDesign settings are available for all file types.
* Export pages, spreads or combined files for all file types.
* Create multiple variations of resolutions, qualities and other key settings.
* Create custom packages for INDD and IDML files, fonts and links.
* Break single files into multiple uniquely named files.
* Retain the integrity and layout of your source documents.

#### Presets & Exports
* Store range queries, naming templates and format settings as shareable JSON files.
* Save preset files locally or remotely – ideal for sharing presets amongst teams.
* Attach presets to documents as sidecar files, linking them directly to your workflow.
* Quickly build custom batch exports.
* Create export reports.

#### Live UI Preview & Tag Builders
* Live previews show your folders and files before exporting.
* Tag builder interfaces help create range queries and filename templates from live tags and data.
* Easily select single files, multiple files or collections for export or batch export.


<br /><br />

## User Guide

### Contents
[1. Before You Begin](#1-before-you-begin)

[2. Range Selection](#2-range-selection)
* [2.1. Quick References](#21-quick-references)
* [2.2. Attribute References](#22-attribute-references)
* [2.3. Object References](#23-object-references)
* [2.4. Extender Symbols](#24-extender-symbols)
* [2.5. 'Layers' Tag](#25-layers-tag)
* [2.6. 'Range' Tag](#26-range-tag)
* [2.7. 'Filter' Tag](#27-filter-tag)
* [2.8. 'Flag' Tag](#28-flag-tag)
* [2.9. 'Arrange' Tag](#29-arrange-tag)
* [2.10. 'Sort' Tag](#210-sort-tag)
* [2.11. Conditional Tag Statements](#211-conditional-tag-statements)
* [2.12. Collections](#212-collections)
* [2.13. 'Collect' Tag](#213-collect-tag)
* [2.14. Inverse Tags](#213-collect-tag)

[3. Naming](#3-naming)
* [3.1. Attribute Tags](#31-attribute-tags)
* [3.3. Data Lookbacks](#32-data-lookbacks)
* [3.4. Conditional Statements](#33-conditional-statements)
* [3.5. Tag Labelling](#34-tag-labelling)
* [3.5. Tag Linking (Validity Checking)](#35-tag-linking-validity-checking)

[4. Modifiers](#4-modifiers)
* [4.1. Tag Targets](#41-tag-targets)
* [4.2. Function Examples](#42-function-examples)
* [4.3. Function Reference](#43-function-reference)
* [4.4. Indexed Template Tags](#44-indexed-template-tags)
* [4.5. Data Counting](#45-data-counting)
* [4.6. If Conditions](#46-if-conditions)

[5. Presets](#5-presets)
* [5.1 Preset Locations](#51-preset-locations)

[6. Real World Examples](#6-real-world-examples)

[7. Tips](#7-tips)

[8. Tag Reference](#8-tag-reference)

[9. Thank You](#9-thank-you)

<br />

### 1. Before You Begin

You can start using Awesome Exporter straight away without changing anything inside your documents. The range, template and modifier builder screens within the app will help with the creation of range queries and naming templates based on your live content.

![Awesome Exporter Range Builder UI](https://modocodo.com/hosted/awesome-exporter/awesome-exporter-ui-range-builder-window-01.png)
*Awesome Exporter Range Builder UI*

<br />

If you would like to follow the examples in this guide without adaptation, it is recommended to set up a test document which includes the following:

* A page with the colour label 'Red' and a page with the colour label 'Green'.
* A paragraph style named 'Title', applied to text on your page.
* A layer named 'EN' with content to represent English language data.
* A layer named 'FR' with content to represent French language data.
* A text frame named 'Code' somewhere on one or more pages, and the text frame contains the characters '123'.
* An image named 'Cover' somewhere on one of your documents pages which links to a file named (the examples use 'Cover Image.jpg').

<br />

If you are testing Awesome Exporter with your existing documents, just change the example tag references fit your document setup.

**Document Structure**

There's no one-size-fits-all solution to creating 'taggable' content in your files, and Awesome Exporter doesn't require you to change your documents structure or layout. The majority of the time, you can simply build tags from existing styled data, oe add named 'meta data' to the document (triple click to edit the name in InDesign). For some use-cases though, it is worth considering how you will structure your document from the start.

When Awesome Exporter builds syntax for a document, it 'tags' the first occurrence of data in named text frames, named objects, styled paragraphs and styled characters within spreads. When multiple items with the same name or style exist on a page, spread, section or layout, only the first instance is referenced by Awesome Exporter. This means some consideration needs to be applied to the placement of taggable elements in the document's layers panel. Tags are easy to use and the syntax becomes clear as you start to use the app.

![Awesome Exporter Example Page Structure](https://modocodo.com/hosted/awesome-exporter/awesome-exporter-ui-textframe-tag-in-page-slug-01.png)
*Awesome Exporter Example Page Structure*

<br />

### 2. Range Selection

Range queries are how you select the pages, spreads, sections, layouts and layers for export. The queries can be standard InDesign ranges, absolute page references, new query tags, or a mix of them all. This section of the guide will demonstrate how ranges are built and how the new query tags can be used.

As expected, Awesome Exporter supports InDesign's standard range query format:

*Examples:*

- **Select by Page Index**: ```+6``` selects page index 6, ```+10``` selects page index 10.

- **Select by Page Index Range**: ```+3-+6``` selects pages 3, 4, 5 and 6 by index.

- **Select by Layout**: ```A4``` selects all pages with the layout reference of 'A4' (references include layout and section prefixes).

- **Select by Section**: ```A4:One``` selects all pages in a section named 'One' from the 'A4' layout. Just the section name (in this example, ```One```) can also be used.

- **Select by Page Name**: ```A4:One:2``` selects page 2 from section ```One``` in layout ```A4```.

<br />

**New Tag Syntax**

Awesome Exporter's new tag syntax extends this standard InDesign range notation to allow selection by element attributes, item styles and document content. Tags can be combined, compared and use logic statements, allow for powerful range and naming queries – opening up new ways to select content and export exactly what you need from a document.

The tags available within a document vary depending on the document content, but an easy to browse reference of available tags can be found in the app's range builder screen and template builder screen.

Just like standard InDesign queries, range queries can be separated using commas. Each comma separated query will add it's results to the selection query. Multiple range queries can also be wrapped inside 'collections' to allow different range queries to be individually grouped [See: Range Collections](#range-query-collections) 

This section of the user guide will demonstrate tag types, query structure, and how to use range queries to access your document content.

<br />

#### 2.1. Quick References

Quick references allow for easy selection based on page visibility or numeric attributes.

| Tag | Description |
| - | - |
| ```[All]``` | Select all pages. |
| ```[Visible]``` | Select only visible pages. |
| ```[Hidden]``` | Select only hidden pages. |
| ```[Even]``` | Select even numbered pages. |
| ```[Odd]``` | Select odd numbered pages. |
| ```[Selected]``` | Select pages selected in the InDesign pages panel. |
| ```[NotSelected]``` | Select pages not selected in the InDesign pages panel. |
| ```[First]``` | Select the first page in the document. |
| ```[Last]``` | Select the last page in the document. |

*Examples:*

- **Select all pages in the document**: ```<[All]>```

- **Select hidden pages and spreads**: ```<[Hidden]>```

- **Select from the first page in the document, to page index 3**: ```<[First]>-+3```

- **Select from page index 2 to the last page in the document**: ```+2-<[Last]>```

- **Select all even pages, plus page 5**: ```<[Even]>,+5```

- **Select all odd pages, plus pages 4-6**: ```<[Odd]>,+4-+6```

<br />

#### 2.2. Attribute References

**Tag Structure**

Attribute tags are used to access attributes and content from the source document. They all follow the familiar format of ```Object```:```Attribute``` with the exception of custom content tags, which follow the format of: <```Host```:```Object```:```Name```:```Attribute```>

- ```Host``` can be ```Page```, ```Spread```, ```Section```, ```Layout``` or ```Document```
- ```Object``` can be ```Text```, ```Image```, ```Paragraph``` or ```Character```
- ```Name``` is the custom name applied to the object via the layers panel in InDesign
- ```Attribute``` is the data attribute you wish to access, such as ```Content```

Live attribute tags for your document can be found in the rang builder ui and the template builder ui.

**Tag Operators**

Range attribute tags use an operator to compare the data retrieved, to the data required. 

For example, ```<Page:Text:Code:Content|=|'123'>``` retrieves the page content from a text frame named 'Code', and checks to see if it matches the required value of '123'. When used as a query, all pages in the document which have a text frame named 'Code', and value of '123' are added to the range selection.

Awesome Exporter supports the following data comparison operators for range tags:

| Operator | Description | Text | Numeric |
| - | - | - | - |
| ```=``` | Equal to. | ✓ | ✓ |
| ```!=``` | Not equal to. | ✓ | ✓ |
| ```>``` | Greater than. | | ✓ |
| ```>=``` | Greater than or equal to. | | ✓ |
| ```<``` | Less than. | | ✓ |
| ```<=``` | Less than or equal to. | | ✓ |
| ```Includes``` | Does the tag include...? | ✓ | ✓ |
| ```!Includes``` | Does the tag not include...? | ✓ | ✓ |
| ```Starts``` | Does the value start with...? | ✓ | ✓ |
| ```!Starts``` | Does the value not start with...? | ✓ | ✓ |
| ```Ends``` | Does the value end with...? | ✓ | ✓ |
| ```!Ends``` | Does the value not end with...? | ✓ | ✓ |
| ```IsEven``` | Is the value an even number. |  | ✓ |
| ```IsOdd``` | Is the value an odd number. |  | ✓ |

<br />

*Examples:*

- Select pages containing a text frame named 'Code' with the value equal to '123': ```<Page:Text:Code:Content|=|'123'>```.

- Select pages containing a text frame named 'Code' which doesn't have the value of '123': ```<Page:Text:Code:Content|!=|'123'>```.

- Select pages containing an image named 'Cover' where the image filename is equal to 'Cover Image.jpg': ```<Page:Image:Cover:Filename|=|'Cover Image.jpg'>```.

- Select pages where the extension of an image frame named 'Cover' is a tiff file: ```<Page:Image:Cover:Extension|=|'tif'>```.

- Select pages where the extension of an image frame named 'Cover' is not a tiff file: ```<Page:Image:Cover:Extension|!=|'tif'>```

- Select page 3 in a document plus any pages which don't have the 'Red' colour label value: ```+3,<Page:Colour:Value|!=|'Red'>```.

- Select spread pages where the colour label is 'Red': ```<Spread:Colour:Value|=|'Red'>```.

- Select pages with a width greater than 200 units of the document's specified unit: ```<Page:Width:Value|>|'200'>```.

<br />

#### 2.3. Object References

Object tags are used to check the existence of items and data. For example, the ```Page:Colour``` attribute can be set to a wide range of colour label values, or 'None'.

To check if a colour label is set, without asking for a specific colour, the ```[Any]``` operator can be used: ```<Page:Colour|[Any]>```. This query will select pages where the colour is set to ***anything***.

Alternatively, ```<Page:Colour|[None]>``` will select pages which have ***no*** colour label set. 

To query the existence of an item on a page, spread, section or layout, you can use ```[Exists]``` or ```[Missing]``` with content object references. For example, ```<Page:Text:Code|[Exists]>``` will check if the text frame named 'Code' exists on the page. 

Awesome Exporter supports the following operators for object tags:

| Operator | Description |
| - | - |
| ```[Any]``` | Referenced data is set to anything. |
| ```[None]``` | Referenced data is set to 'None', '[None]' or similar. |  
| ```[Exists]``` | Referenced object instance exists. |
| ```[Missing]``` | Referenced object instance does not exist. |

<br />

*Examples:*

- Select all pages with any parent page applied: ```<Page:Parent|[Any]>```.

- Select all pages with no parent page applied: ```<Page:Parent|[None]>```.

- Select all pages with a text frame named 'Code'. Content is not important.: ```<Page:Text:Code|[Exists]>```

- Select all pages without a text frame named 'Code'. Content is not important.: ```<Page:Text:Code|[Missing]>```

<br />

#### 2.4. Extender Symbols

Special prefixes and suffixes can be added to page references and tags to extend range selection from the place specified by the reference or tag, forwards to backwards to a specific point in a document.

**Extender dashes** and **flags** can be applied to the left of a reference to extend backwards through the document, or to the right of a reference to extend forwards through the document.

| Symbol / Flag | Description |
| - | - |
| ```-``` | Select from reference to the start or end of the current section. | 
| ```--``` | Select from reference to the start of end of the current layout. |
| ```---``` | Select from reference to the start or end of the current document. |
| ```-[Spread]``` | Select from reference to the end of the current spread. |
| ```-[Section]``` | Select from reference to the end of the current section. |
| ```-[Layout]``` | Select from reference to the end of the current layout. |
| ```-[Document]``` | Select from reference to the start of the current document. |
| ```[Spread]-``` | Select from reference to the start of the current spread. |
| ```[Section]-``` | Select from reference to the start of the current section. |
| ```[Layout]-``` | Select from reference to the start of the current layout |
| ```[Document]-``` | Select from reference to the start of the current document. |

*Forward Examples:*

- Extend selection from page 2 forwards to the end of the current section: ```+2-```
- Extend selection from page 4 forwards to the end of the current layout: ```+4--```
- Extend selection from page 6 forwards to the end of the current document: ```+6---```
- Extend selection from page 8 forwards to the end of the spread: ```+8-[Spread]```

Range extenders also work reverse:

*Reverse Examples:*

- Extend selection from page 4 backwards to the start of the current section: ```-+4```
- Extend selection from page 8 backwards to the start of the current layout: ```--+8```
- Extend selection from page 12 backwards to the start of the current document: ```---+12```
- Extend from page 16 backwards to the start of the section: ```[Section]-+16```

<br />

#### 2.5. ```Layers``` Tag

The ```Layers:Constant``` and ```Layers:Variable``` tags select specific layers, allowing exports to have content variations such as multilingual copy, or multiple content versions from a single document.

'Constant' layers remain visible for all exports, and 'Variable' layers create export variations from the content listed in those layers.

Layer selections can be referenced by name and colour.

The following flags also allow selection by visibility and print-ability:

| Operator | Description |
| - | - |
| ```[Visible]``` | Use visible layers. |
| ```[Visible][Printable]``` | Use visible layers which are also printable. |
| ```[Visible][NotPrintable]``` | Use visible layers which are also not printable. | 
| ```[Hidden]``` | Use hidden layers. |
| ```[Hidden][Printable]``` | Use hidden layers which are also printable. |
| ```[Hidden][NotPrintable]``` | Use hidden layers which are also not printable. |
| ```[Printable]``` | Use printable layers. |
| ```[NotPrintable]``` | Use non-printable layers. |

Note: Layer order is always derived from the layer position in the source document and not the tag order within the range query.

*Examples*:

- A: Select all pages, specify the 'Background' layer to be used in all exports, and create two file variations based on the layers named 'EN' and 'FR':
<br />```<[All]>,<Layers:Constant:Name|=|'Background'>,<Layers:Variable:Name|=|'EN','FR'>```

- B: Select all pages, specify the layers coloured 'Red' to be used in all exports. No variable layers are used:
<br />```<[All]>,<Layers:Constant:Colour|=|'Red'>```

- C: Select all pages, specify layers coloured 'Green' to be used in all exports, and create two file variations based on the layers named 'EN' and 'FR':
<br />```<[All]>,<Layers:Constant:Colour|=|'Green'>,<Layers:Variable:Name|=|'EN','FR'>```

- D: Select all pages and create two file variations based on the layers named 'EN' and 'FR'. No constant layers are used:
<br />```<[All]>,<Layers:Variable:Name|=|'EN','FR'>```

<br />

#### 2.6. ```Range``` Tag

```Range``` tags allow standard range queries to be wrapped inside Awesome Exporter's tag syntax, allowing standard ranges to be used with conditional statements and operators logic. 

*Examples:*

- Select all pages other than page 3: ```<Range|!=|'+3'>```

- Select all pages other than pages 2 to 5 (inclusive): ```<Range|!=|'+2-+5'>```

- If the page has a parent page, select it. Otherwise, select page 3: ```<{Page:Parent|[None]}{Range|=|'+3'}>```

<br />

#### 2.7. ```Filter``` Tag

The ```Filter``` tag filters out certain results and errors from the query. ```Filter``` tags can be applied to the whole range query, or to each single collection.

- Single Usage: ```<Filter|'XXXXX'>```
- Multiple Single Usage: ```<Filter|'XXXXX','XXXXX'>```

<br />

| Filter Options | Description |
| - | - |
| ```DuplicatePages``` | Remove duplicate pages from results. |
| ```EmptyCollections``` | Remove empty collections from results. |
| ```EmptyResults``` | Remove from results. |
| ```EmptyPagesToTrim``` | Remove pages from results where there is no content on the page to the trim boundary. |
| ```EmptyPagesToSlug``` | Remove pages from results where there is no content on the page to the bleed boundary. |
| ```EmptyPagesToBleed``` | Remove pages from results where there is no content on the page to the slug boundary. |
| ```HiddenSpreads``` | Remove hidden spreads from results. |
| ```HiddenPages``` | Remove hidden pages from results. |
| ```HiddenItems``` | Remove any hidden item data from results. |
| ```InaccessibleLinks``` | Remove pages with inaccessible links from results. |
| ```MissingLinks``` | Remove pages with missing links from results. |
| ```NoVisibleItemsOnPage``` | Remove pages with no visible items from results. |
| ```OutOfDateLinks``` | Remove pages with out of date links from results. |
| ```ReferenceErrors``` | Ignore any query reference errors. |

<br />

#### 2.8. ```Flag``` Tag

The ```Flag``` tag can be used to force certain alerts to be highlighted in the export list, without filtering them out of the export. ```Flag``` tags can be used with the whole range query or per collection.  

**Examples:**

- Single Usage: ```<Flag|'XXXXX'>```
- Multiple Single Usage: ```<Flag|'XXXXX','XXXXX'>```

<br />

| Flag Option | Description |
| - | - |
| ```DuplicatePages``` | Flag duplicate pages in export preview. |
| ```EmptyCollections``` | Flag empty collections in export preview. |
| ```EmptyTags``` | Flag empty tags in export preview. |
| ```EmptyPages``` | Flag empty pages in export preview. |
| ```HiddenSpreads``` | Flag hidden spreads in export preview. |
| ```HiddenPages``` | Flag hidden pages in export preview. |
| ```IgnoredTemplateTags``` | Flag ignored template tags. |
| ```InaccessibleLinks``` | Flag inaccessible links. |
| ```MissingTemplateTags``` | Flag missing template tags. |
| ```MissingLinks``` | Flag missing links. |
| ```OutOfDateLinks``` | Flag out of date links.  |
| ```Alerts``` | Flag any alerts in export preview. |

<br />

#### 2.9. ```Arrange``` Tag

The ```Arrange``` tag is used to sort range results  ***before*** the results are named using the template. This allows range queries to be defined in any order, then sorted using one of the below keys. The ordered results will then be named and counted in this newly arranged order. ```Arrange``` tags can be used with the whole range query or per collection.  

**Examples:**

- Arrange by Index, Ascending: ```<Arrange|'Index'|'Ascending'>```
- Arrange by Colour, Ascending: ```<Arrange|'Colour'|'Ascending'>```
- Arrange by Height, Descending: ```<Arrange|'Height'|'Descending'>```
- Arrange by Parent Page, Descending: ```<Arrange|'Parent'|'Descending'>```

<br />

| Key  | Availability |
| - | - |
| ```Index``` | All Types |
| ```Reference``` | All Types |
| ```Parent``` | All Types |
| ```Colour``` | All Types |
| ```Layers``` | All Types |
| ```Width``` | All Types |
| ```Height``` | All Types |
| ```Format``` | All Types |
| ```Layout``` | All Types |
| ```Section``` | All Types |
| ```Notes``` | All Types |
| ```Alerts``` | All Types |

| Order  | Description |
| - | - |
| ```Ascending``` | All Types |
| ```Descending``` | All Types |

<br />

#### 2.10. ```Sort``` Tag

The ```<Sort>``` tag is used to sort query results ***after*** naming has occurred. ```Sort``` can be used with the whole range query or per collection.  

**Examples:**

- Sort by Index, Ascending: ```<Sort|'Index'|'Ascending'>```
- Sort by Resolution Ascending: ```<Sort|'Resolution'|'Ascending'>```
- Arrange by Layer Names, Descending: ```<Sort|'Layers'|'Descending'>```
- Arrange by Section Reference, Descending: ```<Sort|'Section'|'Descending'>```

<br />

| Key  | Availability |
| - | - |
| ```Index``` | All Types |
| ```Reference``` | All Types |
| ```Parent``` | All Types |
| ```Colour``` | All Types |
| ```Layers``` | All Types |
| ```Width``` | All Types |
| ```Height``` | All Types |
| ```Format``` | All Types |
| ```Layout``` | All Types |
| ```Section``` | All Types |
| ```Resolution``` | JPG |
| ```Quality``` | JPG |
| ```Colour Space``` | JPG |
| ```Encoding``` | JPG |
| ```Resolution``` | JPG & PNG |
| ```Quality``` | JPG & PNG |
| ```Colour Space``` | JPG & PNG |
| ```Preset``` | PDF |
| ```PostScript Level``` | EPS |
| ```Colour``` | EPS |
| ```Preview``` | EPS |
| ```Embed Fonts``` | EPS |
| ```Data Format``` | EPS |
| ```Notes``` | All Types |
| ```Alerts``` | All Types |

| Order  | Description |
| - | - |
| ```Ascending``` | All Types |
| ```Descending``` | All Types |

<br />

#### 2.11. Conditional Tag Statements

Conditional statements allow finer range selection by combining multiple queries into a single tag, and only using the results required based on the logic condition used.

Braces ```{``` ```}``` are used to wrap the individual queries inside the tag, and each tag can have as many conditional statements as required. All queries inside the tag will be evaluated, but the results returned will depend on the tags logic.

Conditional range tags can use the following logic:

- ***OR***: the first valid part of the tag is used.
- ***AND***: all conditions must match. The combined results are used.
- ***JOIN***: results from all of the valid parts of the tag are combined and used.

*Examples:*

- <u>**JOIN**</u> pages with a green colour label and parent page reference 'A'.
<br />```<{Page:Colour:Label|=|'Green'}Join{Page:Parent:Reference|=|'A'}>```

- Select pages with a green colour label <u>**AND**</u> parent page with reference 'A'.
<br />```<{Page:Colour:Label|=|'Green'}And{Page:Parent:Reference|=|'A'}>```

- Select pages with a green colour label <u>**OR**</u> parent page with reference 'A'.
<br />```<{Page:Colour:Label|=|'Green'}Or{Page:Parent:Reference|=|'A'}>```

- Select all spreads where text frame named 'Title' exists <u>**AND**</u> the spread has a width less than 200.
<br />```<{Spread:Text:Title|[Exists]}And{Spread:Width|<|'200'}>```

- Select all spreads where text frame named 'Title' exists <u>**OR**</u> the spread has a width greater than 200.
<br />```<{Spread:Text:Title|[Exists]}Or{Spread:Width|>|'200'}>```

The range builder UI provides a simple interface to build conditional statements for any attribute tag.

<br />

#### 2.12. Collections

Range collections allow multiple independent file lists to be built from a single range query, inside a single export preset. Collections are created by wrapping any range query with the ```(``` and ```)``` characters.

*Examples:*

- ```(+2) (+1,+3)``` would return an export collection containing page 2, and a separate export collection containing pages 1 and 3.

- Collections can contain both ranges and tags. The following builds a collection containing pages 1, 2 and 3, plus a collection containing pages with a parent named 'Square': ```(+1-+3) (<Page:Parent:Name|=|'Square'>)```

##### Collection Labels

Collections can be labelled with an alpha-numeric string wrapped inside the ```@``` label characters. Labels are always placed at the start of a collection. Collection labels can be accessed from the naming template by using the ```<Collection:Label>``` tag, and by modifier functions.

*Example:*

- Range: ```(@One@ +1-+3) (@Two@ <Page:Parent:Name|=|'Square'>)```
- Template: ```Collection: <Collection:Label> Index: <Export:Index>```

<br />

#### 2.13. ```Collect``` Tag

##### Attribute & Data

The ```Collect``` tag can be use to automatically build collections based on the document attributes or data. Collect tags work with any available attribute tag in the document.

*Examples:*

- ```<Collect|'Data'|'Page:Colour:Label'>``` build and name collections based on their colour label.
- ```<Collect|'Data'|'Page:Parent:Name'>``` build and name collections based on page parent names.
- ```<Collect|'Data'|'Page:Section:Name'>``` build and name collections using section names. 

##### Numeric Sequences

You can also build collections using numeric sequences.

*Examples:*

- ```<Collect|'Sequence'|'+1'|'3'>``` collects pages into collections of three, starting with page index 1.
- ```<Collect|'Sequence'|'+3'|'2'>``` collects pages into collections of two, starting with page index 3.

##### Adding To Auto-Collections

Additional tags and references can be used with ```Collect``` tags to allow other pages and layers to be added to the start or end of each created collection. In this example, page 2 of the document is added to the end of every collection created, then each collection is sorted by index which positions page 2 in numeric order within the collection.

A good use for this query is when one document contains different elements of the final required export. You could create a query to auto-build collections containing the core content, then add pages to the start and end of each collection. 

*Examples:*

- ```<Collect|'Sequence'|'+1'|'3'>,<Page:Number|=|'2'>,<Arrange|'Index'|'Ascending'>``` creates collections of three pages starting at page 1 and adds page 2 to the end of each collection. The collections are then sorted by index ascending.

- ```<Page:Index|=|'1-3'>,<Collect|'Data'|'Page:Colour:Label'>,<Page:Index|=|'8-10'>``` build and name collections based on their colour label, and add pages 1-3 to the start of all auto-created collections, and pages 8-10 to the end of all auto-created collections.

<br />

#### 2.14. Inverse Tags

Inverse tags are tags which remove from the export range, rather than add to it. Inverse tags are created by adding the tilde character ```~``` to the start and end of any regular range tag.

**Example:**

- ```<[All]>,<~Page:Index|=|'3'~>``` would add all pages to the export selection, then remove page 3.
- ```<[All]>,<~Page:Colour:Label|=|'Red'~>``` would add all pages to the export selection, then remove pages with a 'Red' colour label.

<br />

### 3. Naming

![Awesome Exporter Template Builder UI](https://modocodo.com/hosted/awesome-exporter/awesome-exporter-ui-template-builder-window-01.png)
*Awesome Exporter Template Builder UI*

File name and folder name templates are built using the same syntax as range query tags, with just a few subtle differences in tag structure. Naming template tags can refer to document content or attributes, allowing you to use attribute data, styled data and named data in filenames.

You can also use string literal tags, spacers tas, folder separators and standard text strings.

Object tags are not used with naming templates as they do not directly return data.

A full list of available tags for your document can be found in the template builder ui.

<br />

#### 3.1. Attribute Tags

The following template creates a file name using the document name, and a sequential export number. A spacer character ```<|>``` is used between the two tags: ```<Document:Name><|><Export:Index>```. The spacer character defaults to a space ```' '```, but this can be set using a modifier tag.

This example creates a folder named 'Web' and a file named using the document name, plus a sequential export number: ```Web</><Document:Name><|><Export:Index>```. The ```</>``` tag defines where the template splits tags used for folder names and tags used for file names.

The full list of range and template tags can be found towards the end of the guide. There are also some real-world examples of naming templates later in the guide.

<br />

#### 3.2. Data Lookbacks

When creating a document, data such as chapter titles or section headers likely won't appear on each page but you may want to access the data for every export. The template lookback symbol (```^```) and the range lookback symbol (```^^```) help by looking back up through the data used on previous pages, spreads, sections and layouts and allowing this data to be accessed when it is missing

- For example: ```<^Page:Text:Chapter:Content>``` uses the content of a text frame named 'Chapter' in each export, this text frame might only appear on certain pages, but each export will reference data from the most recent page occurrence.

<br />

#### 3.3. Conditional Statements

Similar to conditional range tags, conditional naming tags use curly braces ```{``` ```}``` to wrap multiple tag parts.

Conditional naming tags can use the following logic:

- ***Or***: where the first valid part of the tag is used.
- ***And***:  where all parts are used if all parts of the tag return valid data.
- ***Join***: where all valid parts of the tag are combined into one result. 

*Examples:*

- Use data from a **page** text frame named 'Code', ***OR*** use data from a **parent** page text frame named 'Code' as a fallback.
<br />```<{Page:Text:Code:Content}Or{Parent:Text:Code:Content}>```.

- Use data from a page text frame named 'Code', or use the string 'Missing' as a fallback.
<br />```<{Page:Text:Code:Content}Or{'Missing'}>```

- Use data from a spread text frame named 'Code', ***AND*** the page colour label. If either of these don't return data, nothing will be output.
<br />```{Spread:Text:Code:Content}And{Page:Colour:Label}>```

<br />

#### 3.4. Tag Labelling

Naming template tags can be labeled by wrapping a string in the ```@``` characters towards the start of the tag. It's helpful to name tags when you need to target them and their data with modifier functions.

*Example:* 

- ```<@NAME@Document:Name>```:

<br />

#### 3.5. Tag Linking (Validity Checking)

Naming tags can check the data validity of surrounding tags using the ```+``` and ```-``` symbols. You can use this functionality to 'chain' tags together and build flexible, conditional naming templates, where tags depend on data from other tags.

Tags can check validity to the left ```<+|>```, to the right ```<|+>``` and to both sides ```<+|+>```. 

**Syntax:**

- ```+``` allows a tag to be used if a surrounding tag contains valid data.
- ```-``` allows a tag to be used if a surrounding tag contains invalid data.

- The number of ```+``` and ```-``` symbols controls how far a tag 'looks backwards' or 'looks forwards'.

*Examples:*

- The spacer is only used if the tags to both the left and right contain valid data. If ```Document:Name``` or ```Page:Text:Code:Content``` don't return data, the spacer tag is ignored.
<br />```<Document:Name><+|+><Page:Text:Code:Content>```.

- The spacer is only used if the ```Page:Text:Code:Content``` tag (three positions backwards) contains valid data.
<br />```<Page:Text:Code:Content><|><Document:Name><+++|><'File'>```.

- Each tag checks the validity of the previous tag data.
<br />```<Document:Name><+|><+Page:Text:Part1:Content><+|><+Page:Text:Part2:Content><+|><+Page:Text:Part3:Content>```.

- Validity checkers can be mixed with other symbols such as conditional template tags and data lookback template tags:
<br />```<Document:Name><+|><+{Page:Text:Part1:Content}{Page:Text:Part2:Content}><|+><+Page:Text:Part3:Content>```


<br /><br />


### 4. Modifiers

![Awesome Exporter Range Builder UI](https://modocodo.com/hosted/awesome-exporter/awesome-exporter-ui-modifiers-builder-window-01.png)
*Awesome Exporter Range Builder UI*

Modifier functions allow naming tag data to be modified using a range of built-in functions. Queries can be run against any attribute tag, labelled tag, string, spacer or part in the naming template. This allows you to fine-tune folder names and file names after they have been built. 

Modifier functions can be applied to tags, labels, folders, files or the full export path. Each function replaces or changes its target data with the data returned from the function.

The naming modifier ui provides access to all available modifier functions. 

<br />

#### 4.1. Tag Targets

| Target  | Run Function Against... |
| - | - |
| ```Path``` | The full export path. |
| ```Folder``` | The folder part of the export path. |
| ```File``` | Just the file part of the full export path. |
| ```Tag``` | A specific tag used in the template. |
| ```Export``` | Each export (mainly used with 'Note' functions). |
| ```Strings``` | Text placed inside string tags. |
| ```Spacers``` | Spacer tags. |
| ```Text``` | Text which appears in the template (not inside tags). |
| ```@XXX@``` | A labelled tag. |

<br />

#### 4.2. Function Examples

**Using Functions**

- Convert the file name to uppercase ```<File|Uppercase>```.

- Convert the folder name to uppercase ```<Folder|Uppercase>```.

- Convert the entire file path to uppercase ```<Path|Uppercase>```.

- Convert a labelled tag to uppercase ```<@ABC@|Uppercase>```.

- Convert any occurrence of ```<Document:Name>``` tags to uppercase ```<Document:Name|Uppercase>```

Some modifier functions require parameters. For example, the ```FindReplace``` function takes three parameters; (1) an operator, (2) a string to find and (3) a replacement string.

**Example:**

- Replace '72' with 'Web' for all ```<JPG:Resolutions>``` tags: ```<JPG:Resolution|FindReplace|=|'72'|'Web'>```

- Replace '300' with 'Print' for all ```<JPG:Resolutions>``` tags: ```<JPG:Resolution|FindReplace|=|'300'|'Print'>```

- Replace '72' with 'Web' for all tags labelled 'ABC': ```<@ABC@|FindReplace|=|'72'|'Web'>```

<br />

Another modifier function, ```Split``` is useful when you need to extract specific parts of a tags data. In this example we assume the document name is 'Web Assets - June - Marketing', and we only want to use the first part of the document name.

First, add the ```<Document:Name>``` tag to the naming template, then use the ```Split``` function modifier to modify it:

- Template: ```<Document:Name>```
- Modifier: ```<Document:Name|Split|' - '|'1'>``` 

This would return 'Web Assets' from the document name. Changing the modifier argument from '1' to '2' would return 'June', and changing it to '3' would return 'Marketing'.

<br />

#### 4.3. Function Reference

| Function | Description | Parameters |
| - | - | - |
| ```Index``` | Create a running index of the specified source data. | 1: Incrementer. Valid options: 'Pages', 'Spreads', 'Sections', 'Layouts'<br />2: Scope. Valid Options: 'All', 'Range'<br />3: Breaker tag. Can be any valid object or attribute tag. |
| ```Count``` | A running count of the specified source data | 1: Incrementer. Valid options: 'Pages', 'Spreads', 'Sections', 'Layouts'<br />2: Scope. Valid Options: 'All', 'Range'<br />3: Breaker tag. Can be any valid object or attribute tag. |
| ```Total``` | A final total of the specified source data. | 1: Incrementer. Valid options: 'Pages', 'Spreads', 'Sections', 'Layouts'<br />2: Scope. Valid Options: 'All', 'Range'<br />3: Breaker tag. Can be any valid object or attribute tag. |
| ```Note``` | Add notes to the 'Note' column of the export preview. | 1: Attribute tag |
| ```FindReplace``` | Replace the source with the specified string. | 1: String to find<br />2: String to use as replacement |
| ```Replace``` | Replace a string with another string. | 1: String to use as replacement |
| ```Split``` | Split tag value by delimiter and return part of it. | 1: String delimiter<br />2: Split index to use |
| ```Pad``` | Pad the tag value using a specified amount of characters. | 1: String to use as padding<br />2: Length of padding |
| ```Insert``` | Insert data at a specified point. | 1: String to insert |
| ```Prefix``` | Add to the start of a tag value. | 1: String to use as prefix |
| ```Suffix``` | Add to the end of a tag value. | 1: String to use as suffix |
| ```Uppercase``` | Convert tag or label to upper case. | N/A |
| ```Lowercase``` | Convert tag or label to lower case. | N/A |
| ```Titlecase``` | Convert tag or label to title case. | N/A |
| ```Increase``` | Increase the numeric value of a tag. | 1: Numeric amount to increase by |
| ```Decrease``` | Decrease the numeric value of a tag. | 1: Numeric amount to decrease by |
| ```Add``` | Add to the numeric value of a tag. | 1: Numeric value to add |
| ```Subtract``` | Subtract from the numeric value of a tag. | 1: Numeric value to subtract |
| ```Multiply``` | Multiply the numeric value of a tag. | 1: Numeric value to multiply |
| ```Divide``` | Divide the numeric value of a tag. | 1: Numeric value to divide |
| ```Length``` | Get the length of the tags value. | N/A |
| ```Trim``` | Trim space characters from the source data. | N/A |
| ```ReduceSpaces``` | Reduce multiple spaces in the source data. | N/A |
| ```ReplaceInvalidCharacters``` | Replace any invalid character in the source data with a specified string. | 1: String to use as replacement |
| ```RemoveInvalidCharacters``` | Remove invalid characters in the source data. | N/A |
| ```ReplaceDiacriticCharacters``` | Replace any diacritic characters in the source data with a specified string. | 1: String to use as replacement |
| ```RemoveDiacriticCharacters``` | Remove diacritic characters in the source data. | N/A |
| ```ConvertDiacriticCharacters``` | Convert diacritic characters in the source data. | N/A |

<br />

#### 4.4. Indexed Template Tags

Naming tag index labels allow you to create dynamic labels for tags based on collection indexes and export indexes, allowing specific exports to be targeted individually with modifier functions.

To create an indexed label simply add the ```-#``` postfix to the end of any naming tag label. You can then refer to the tag by this label, by its collection index, or by its collection index and export index combined. 

*Example:*

Let's assume we have the following filename template: ```<@Tag-#@Document:Name>```. This index labelled tag label allows us to run the following modifiers against it:

- ```<@Tag-#@|Uppercase>```: uppercase the tag data labeled 'Tag-#': 

- ```<@Tag-1@|Uppercase>```: uppercase the tag data labeled 'Tag-#' in collection one only:

- ```<@Tag-1-3|@Uppercase>```: uppercase the tag data labeled 'Tag-#' for export 3 in collection 1

- ```<@Tag-2-8|@Uppercase>```: uppercase the tag data labelled 'Tag-#' for export 8 in collection 2: 

<br />

#### 4.5. Data Counting

Counters are used to return a numeric value based on the occurrence of objects, attributes or data in the document. This allows you to dynamically index, count and totalise tags based on live data.

In the following examples, we will assume the document has a text frame named 'Chapter' which will be used as the counters data source.

*Example:*

- Template: ```<@Chapter@>```
- Modifier: ```<@Chapter@|Index|'Pages'|'Range'|'Page:Text:Chapter:Content'>``` 

*How It Works:*

- The ```Index``` function creates an index counter and associates it with the tag labelled ```Chapter```. 

- The counter uses ```Page:Text:Chapter:Content``` as its data source.

- The counter scans over each ```Page``` in the document and increments each time the data in ```Page:Text:Chapter:Content``` does not change.

- The counter will reset to zero each time it encounters the source text frame named 'Chapter' which contains data different to the existing data.

- The value of the ```@Chapter@``` tag for each export will be the running index.

The tables below show the arguments which can used to build 'indexes', 'counts' and 'totals'.

Counter Types:
| Type | Description |
| - | - |
| Index | Build an running index of the source reference. |
| Count | A running total of the source reference. |
| Total | A total of the source reference. |

First Argument Options:
| Type | Description |
| - | - |
| Pages | Counter increases for each page. |
| Spreads | Counter increases for each spread. |

Second Argument Options:
| Type | Description |
| - | - |
| All | Counts start at the start of the document, even if not included in the range query. |
| Range | Counts start with the first page of the results returned from range query. |


<br />

#### 4.6. If Conditions

Modifier tags can be controlled further by adding an 'if condition'. This causes modifiers to run only when specific conditions are met.

*Example:*

- Convert the ```<Document:Name>``` tag to uppercase **only if the document file name is 'Brand Assets.indd'**: <br />```<Document:Name|Uppercase|If|'Document:File'|=|'Brand Assets.indd'>```

- In this example, we append the word 'Web' to the end of the template path, **only if the file being exported is a JPG with the resolution of '72'**:
<br />```<Path|Suffix|'Web'|If|'JPG:Resolution'|=|'72'>```


<br /><br />

### 5. Presets

![Awesome Exporter Range Builder UI](https://modocodo.com/hosted/awesome-exporter/awesome-exporter-ui-save-preset-window-01.png)
*Awesome Exporter Range Builder UI*

Awesome Exporter allows presets to be created, modified, moved, shared and deleted from within the application. Presets contain range, format, template and modifier configurations which can be saved either globally, against a specific document or to a custom location. All presets are stored in JSON format to allow easy editing and portability.

<br />

#### 5.1 Preset Locations

| Location | Description |
| - | - |
| Quick Exports | Default application exports. Useful for quick, sharable presets. |
| Document Sidecars | A JSON preset file with the same name as a document, in the same folder. Useful for document specific presets which are linked to the document content. |
| Custom Location | A local or server based JSON file. Useful for sharing presets within a team. |


<br /><br />

### 6. Real World Examples

**Example 01:**
<br />Create collections of files based on sections references. Export using the section prefix and and index.
- Range: ``` <Collect|Data|'Spread:Section:Reference'>```
- Template: ```<Spread:Section:Prefix><|><Export:Index>```

<br />

**Example 02:**
<br />Select all pages and use 'Base' and 'Overlay' as the constant layers. Red layers are used as variable content layers. Name the exports using the document name, collection label and variable layer name.
- Range: ```(@A@<[All]>,<Layers:Constant:Name|=|'Base','Overlay'>,<Layers:Variable:Colour|=|'Red'>)```
- Template: ```<Document:Name><|>Day<|><Collection:Label><|><Layers:Variable:Name>```

<br />

**Example 03:**
<br />Collect pages in two-page stepped sequence, from the first page in the document. Export using the document name and the index of the export.

- Range: ```<Collect|'Sequence'|'+1'|'2'>```
- Template: ```<Document:Name><+|><Export:Index>```

<br />

**Example 04 – JPG Specific:**
<br />Select all pages in the document. Create an spread index counter to count the data from a text frame labelled 'Name', the first occurrence of the text frame on a spread will be used. Name the exports using the document name and export type for the folder name and the document name, text frame data, counter  and JPG resolution for the file name.

- Range: ```<[All]>```
- Template: ```<Document:Name><|><Export:Type></><Document:Name><+|><^Page:Text:Name:Content><+|><@Number@><+|><JPG:Resolution>```
- Modifiers: ```<@Number@|Index|'Spreads'|'All'|'Spread:Text:Name:Content'>```

<br />

**Example 05:**
<br />Collect pages into collections using the data from a text frame labelled 'Name'. Name the exports using the first part of the document name and the text frame content.

- Range: ```<Collect|'Data'|'^Page:Text:Name:Content'>```
- Template: ```<@N1@Document:Name><+|><Page:Text:Name:Content>```
- Modifier: ```<@N1@|Split|' _ '|'1'>```

<br />

**Example 06:**
<br />Collect pages into collections by colour label. Name the exports using the second part of the document name and text frame labelled 'Name'. Replace any '&' characters with the word 'and'. Add a note to each item in the export list using the data from the text frame labelled 'Name'.

- Range: ```<Collect|'Data'|'^Page:Colour:Value'>```
- Template: ```<@N1@Document:Name><+|><Page:Text:Name:Content>```
- Modifier: ```<@N1@|Split|' _ '|'2'><Path|FindReplace|'&'|'and'><Export|Note|'Page:Text:Name:Content'>```

<br />

**Example 07:**
<br />Demonstration of indexes, counters and totalisers.

- Range: ```<[All]>```
- Template: ```Index: <*Index*>, Count: <*Count*>, Total: <*Total*>```
- Modifier: ```<*Index*|Index|'Pages'|'All'|Page:Colour:Label><*Count*|Count|'Pages'|'All'|Page:Colour:Label><*Total*|Total|'Pages'|'All'|Page:Colour:Label>",```

<br />

**Example 08:**
<br />Add all pages to a collection, then remove any with the colour label value of 'Gold' or 'Red'. Demonstrates the use of inverse tags.

- Range: ```<[All]>,<~Page:Colour:Value|=|'Gold','Red'~>```
- Template: ```<Document:Name><|><Export:Index>```

<br />

**Example 09:**
<br />Replace the default spacer character.

- Range: ```<[All]>```
- Template: ```<Document:Name><|><Export:Index>```
- Modifier: ```<Spacer|Replace|'-'>```

<br />

**Example 10:**
<br />Build collections of pages based on their colour label and add the first page and last page to the start and end of all created collections. Any tags placed to the left of a '''Collect''' tag will be added to the start of all auto-created collections, and any tags placed to the right will be added to the end of all auto-created collections.

- ```<[First]>,<Collect|'Data'|'Page:Colour:Label'>,<[Last]>``` 

<br /><br />

### 7. Tips

**User Interface Tips**

- To rename layers, shapes and text frames in InDesign, triple click on the item in the layers panel. These names can then be used as tags in the app.

- Hold 'Option'/'Alt' when clicking the 'Export...' button in the InDesign panel to work with only the currently active document.

- Hold 'Option'/'Alt' when clicking the 'Export' or 'Add To Batch' buttons in the app to only export or batch the currently selected file type.

- Hold 'Option'/'Alt' when clicking 'Save Preset...' to overwrite the active preset with the visible settings.

- Hold 'Option'/'Alt' when changing documents to switch documents without building the export list.

**Keyboard Shortcuts**

- 'Cmd+K': Open Settings
- 'Cmd+M': Manage Presets
- 'Cmd+B': Add To Batch
- 'Cmd+Shift+B': Manage Batch Exports
- 'Cmd+E': Export
- 'Cmd+S': Save Preset
- 'F5': Refresh Export List
- 'Cmd+1': View JPG Files
- 'Cmd+2': View PDF Files
- 'Cmd+3': View PNG Files
- 'Cmd+4': View EPS Files
- 'Cmd+5': View INDD Files
- 'Cmd+6': View IDML Files

*Note: Due to how InDesign receives key shortcuts, focus must be on the plugin for these shortcuts to be available.*

<br /><br />

### 8. Tag Reference

Below is a list of tags available for use in range queries and naming templates. Some tags can only be used in range queries and some only used in naming templates – the tick marks show where each tag can be used. 

Note: The range query builder window and naming template builder window can be used to see the live tags available for use in your document.

#### Range Selectors
| Reference | Description | Range | Template |
| - | - | - | - |
| ```[All]```	| All pages in the document. | ✓ | |
| ```[Visible]``` | Visible pages in the document. | ✓ | |
| ```[Hidden]``` | Hidden pages in the document. | ✓ | |
| ```[Even]``` | All even numbered pages. | ✓ | |
| ```[Odd]```	| All odd numbered pages. | ✓ | |
| ```[First]``` | First page in document. | ✓ | |
| ```[Last]``` | Last page in document. | ✓ | |
| ```[Selected]``` | Pages and spreads selected in the UI. | ✓ | |

#### Range Functions
| Reference | Description | Range | Template |
| - | - | - | - |
| ```Range``` | Select pages based on range query. | ✓ | |
| ```Collect``` | Create live collections from attributes and data. | ✓ | |
| ```Sequence``` | Collect a range sequence from the document. | ✓ | |
| ```Filter``` | Set range filters. | ✓ | |
| ```Flag``` | Set range flags. | ✓ | |
| ```Arrange``` | Arrange range query results. | ✓ | |
| ```Sort``` | Sort the export preview. | ✓ | |

#### ```System``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```System:Type``` | System type ID. | String | ✓ | ✓ |
| ```System:User``` | System user name. | String | ✓ | ✓ |

#### ```Host``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Host:UserID``` | Host application user ID. | String | ✓ | ✓ |
| ```Host:UserName``` | Host application user name. | String | ✓ | ✓ |
| ```Host:Company``` | Host application company name. | String | ✓ | ✓ |
| ```Host:App``` | Host application name. | String | ✓ | ✓ |
| ```Host:Version``` | Host application version. | String | ✓ | ✓ |
| ```Host:Name``` | Host name. | String | ✓ | ✓ |

#### ```App``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```App:Name``` | Application name. | String | ✓ | ✓ |
| ```App:Company``` | Application company name. | String | ✓ | ✓ |
| ```App:Version``` | Application version. | String | ✓ | ✓ |
| ```App:Host``` | Application host name. | String | ✓ | ✓ |
| ```App:Date``` | Application production date. | String | ✓ | ✓ |

#### ```Folder``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Document:Folder``` | Document folder path. | String | ✓ | ✓ |
| ```Document:File``` | Document file path. | String | ✓ | ✓ |
| ```Document:Name``` | Document name. | String | ✓ | ✓ |
| ```Document:Extension``` | Document extension. | String | ✓ | ✓ |
| ```Document:Created``` | Document creation date/time. | String | ✓ | ✓ |
| ```Document:Modified``` | Last modified date/time. | String | ✓ | ✓ |

#### ```Folder``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Folder:Name``` | Folder name. | String | ✓ | ✓ |
| ```Folder:Path``` | Folder path. | String | ✓ | ✓ |
| ```Folder:Created``` | Folder creation date/time. | String | ✓ | ✓ |
| ```Folder:Modified``` | Last modified date/time. | String | ✓ | ✓ |

#### ```File``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```File:Name``` | File name | String | ✓ | ✓ |
| ```File:Extension``` | File extension. | String | ✓ | ✓ |
| ```File:Created``` | File creation date/time. | String | ✓ | ✓ |
| ```File:Modified``` | File modified date/time. | String | ✓ | ✓ |

#### ```XMP``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```XMP:Author``` | Author name from XMP data | String | ✓ | ✓ |
| ```XMP:Description``` | Document description from XMP data. | String | ✓ | ✓ |
| ```XMP:CopyrightInfoURL``` | Copyright URL from XMP data. | String | ✓ | ✓ |
| ```XMP:CopyrightNotice``` | Copyright notice from XMP data. | String | ✓ | ✓ |
| ```XMP:DocumentTitle``` | Document title from XMP data. | String | ✓ | ✓ |
| ```XMP:Creator``` | Document creator from XMP data. | String | ✓ | ✓ |
| ```XMP:Keywords``` | Document keywords from XMP data. | String | ✓ | ✓ |
| ```XMP:ServerURL``` | Server URL from XMP data. | String | ✓ | ✓ |
| ```XMP:JobName``` | Job name from XMP data. | String | ✓ | ✓ |
| ```XMP:Format``` | Format from XMP data. | String | ✓ | ✓ |

#### ```Variables``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Variable:XXX``` | File name | String | ✓ | ✓ |

#### ```Content Containers``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Layouts:Count``` | Number of layouts in the document. | String | ✓ | ✓ |
| ```Sections:Count``` | Number of sections in the document. | String | ✓ | ✓ |
| ```Spreads:Count``` | Number of spreads in the document. | String | ✓ | ✓ |
| ```Pages:Count``` | Number of pages in the document. | String | ✓ | ✓ |

#### ```Layers``` References
| Reference | Description | Range | Template |
| - | - | - | - |
| ```Layers:Constant:Name``` | Specify constant layers by name.  | ✓ | ✓ |
| ```Layers:Constant:Colour``` | Specify constant layers by colour.  | ✓ | ✓ |
| ```Layers:Variable:Name``` | Specify variable layers by name. | ✓ | ✓ |
| ```Layers:Variable:Colour``` | Specify variable layers by colour. | ✓ | ✓ |

#### ```Preset``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Preset:Name``` | Preset name. | String | ✓ | ✓ |
| ```Preset:Description``` | Preset description. | String | ✓ | ✓ |
| ```Preset:Modified``` | Is the preset modified? | Y/N | ✓ | ✓ |
| ```Preset:Favourite``` | Is the preset a favourite? | Y/N | ✓ | ✓ |

#### ```Collections``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Collections:Index``` |  | Number | | ✓ |
| ```Collections:Count``` | Number of collections. | Number | | ✓ |
| ```Collections:Exports``` | Number of exports in all collections. | Number | | ✓ |

#### ```Collection``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Collection:Label``` | Current collection label. | Number | | ✓ |
| ```Collection:Index``` | Current collection number. | Number | | ✓ |
| ```Collection:Exports``` | Number of exports in the current collection. | Number | | ✓ |

#### ```Exports``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Exports:Count``` | Total number of exports | Number | | ✓ |

#### ```Export``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Export:Type``` | Current export type. | String | | ✓ |
| ```Export:Format``` | File format of the export. | String | | ✓ |
| ```Export:Extension``` | File extension of the export. | String | | ✓ |
| ```Export:Order``` | Position of the export in relation to all exports. | Number | | ✓ |
| ```Export:Index``` | Current export number. | Number | | ✓ |

#### ```Spread Attributes``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Spread:Pages``` | Number of pages in the spread. | ✓ | ✓ |
| ```Spread:Index``` | Current spread number. | ✓ | ✓ |

#### ```Page Attributes``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Page:Name``` | Page name. | String | ✓ | ✓ |
| ```Page:Number``` | Page number. | Number | ✓ | ✓ |
| ```Page:Reference``` | Page reference. | String | ✓ | ✓ |
| ```Page:Index``` | Page index. | Number | ✓ | ✓ |
| ```Page:Layout``` | Page layout. | String | ✓ | ✓ |
| ```Page:Bookmark:Name``` | Bookmark name. | String | ✓ | ✓ |
| ```Page:Parent:Reference``` | Parent page reference, (combination of prefix and name). | String | ✓ | ✓ |
| ```Page:Parent:Prefix``` | Parent page prefix. | String | ✓ | ✓ |
| ```Page:Parent:Name``` | Parent page name. | String | ✓ | ✓ |
| ```Page:Colour:Value``` | RGB colour value of the page. | String | ✓ | ✓ |
| ```Page:Colour:Type``` | Returns 'UI' if the colour is a colour label or 'User' if the colour has been set to a custom RGB value. | String | ✓ | ✓ |
| ```Page:Layout:Name``` | Parent page reference, (combination of prefix and name). | String | ✓ | ✓ |
| ```Page:Section:Name``` | Parent page reference, (combination of prefix and name). | String | ✓ | ✓ |
| ```Page:Section:Prefix``` | Parent page prefix. | String | ✓ | ✓ |
| ```Page:Section:Marker``` | Parent page name. | String | ✓ | ✓ |
| ```Page:Width:Value``` | Numeric page width value. | Number | ✓ | ✓ |
| ```Page:Width:Unit``` | Page width unit (i.e. px or mm). | String | ✓ | ✓ |
| ```Page:Height:Value``` | Numeric page height value. | Number | ✓ | ✓ |
| ```Page:Height:Unit``` | Page height unit (i.e. px or mm). | String | ✓ | ✓ |

#### ```Date``` References
| Reference | Description | Range | Template |
| - | - | - | - |
| ```Date:Weekday``` | Number | Name of the day. | ✓ | ✓ |
| ```Date:Day``` | Number | Numeric day of the month. | ✓ | ✓ |
| ```Date:Month``` | Number | Numeric month number. | ✓ | ✓ |
| ```Date:Year``` | Number | Numeric year. | ✓ | ✓ |

#### ```Time``` References
| Reference | Description | Range | Template |
| - | - | - | - |
| ```Time:Millisecond``` | Number | Current millisecond. | ✓ | ✓ |
| ```Time:Second``` | Number | Current second. | ✓ | ✓ |
| ```Time:Minute``` | Number | Current minute. | ✓ | ✓ |
| ```Time:Hour``` | Number | Current hour. | ✓ | ✓ |

#### ```Text``` References (Text Frames)
| Reference | Description | Data| Range | Template |
| - | - | - | - | - |
| ```Document:Text:XXX:Content```<br />```Layout:Text:XXX:Content```<br />```Section:Text:XXX:Content```<br />```Spread:Text:XXX:Content```<br />```Page:Text:XXX:Content```<br />```Canvas:Text:XXX:Content``` | Named text frame text. | String | ✓ | ✓ |

#### ```Image``` References (Image Objects)
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Document:Image:XXX:Name```<br />```Layout:Image:XXX:Name```><br />```Section:Image:XXX:Name```<br />```Spread:Image:XXX:Name```<br />```Page:Image:XXX:Name```<br />```Canvas:Image:XXX:Name``` | Named image file name. | String | ✓ | ✓ |

#### ```Paragraph``` References (Text Frames)
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Document:Paragraph:XXX:Content```<br />```Layout:Paragraph:XXX:Content```<br />```Section:Paragraph:XXX:Content```<br />```Spread:Paragraph:XXX:Content```<br />```Page:Paragraph:XXX:Content```<br />```Canvas:Paragraph:XXX:Content``` | Styled paragraph text. | String | ✓ | ✓ |

#### ```Character``` References (Text Frames)
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Document:Character:XXX:Content```<br />```Layout:Character:XXX:Content```<br />```Section:Character:XXX:Content```<br />```Spread:Character:XXX:Content```<br />```Page:Character:XXX:Content```<br />```Canvas:Character:XXX:Content``` | Styled character text. | String | ✓ | ✓ |

#### ```JPG``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```JPG:Format``` | | String |  | ✓ |
| ```JPG:Resolution``` | JPG resolution setting. | Number |  | ✓ |
| ```JPG:Quality``` | JPG quality setting. | Number |  | ✓ |
| ```JPG:ColourSpace``` | JPG colour space setting. | String |  | ✓ |
| ```JPG:Encoding``` | JPG encoding setting. | String |  | ✓ |
| ```JPG:AntiAlias``` | JPG anti alias setting. | Y/N |  | ✓ |
| ```JPG:UseDocumentBleed``` | JPG document bleed setting. | Y/N |  | ✓ |

#### ```PDF``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```PDF:Format``` | | String |  | ✓ |
| ```PDF:CombineFiles``` | | Y/N |  | ✓ |
| ```PDF:Preset``` | PDF preset name. | String |  | ✓ |

#### ```PNG``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```PNG:Format``` | | String |  | ✓ |
| ```PNG:Resolution``` | PNG resolution setting. | String |  | ✓ |
| ```PNG:Quality``` | PNG quality setting. | Number |  | ✓ |
| ```PNG:ColourSpace``` | PNG colour space setting. | String |  | ✓ |
| ```PNG:AntiAlias``` | PNG anti alias setting. | Y/N |  | ✓ |
| ```PNG:UseDocumentBleed``` | PNG document bleed setting. | Y/N |  | ✓ |
| ```PNG:TransparentBackground``` | PNG transparent background setting. | Y/N |  | ✓ |
| ```PNG:SimulateOverprint``` | PNG simulate overprint setting. | Y/N |  | ✓ |

#### ```EPS``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```EPS:Format``` | | String |  | ✓ |
| ```EPS:PostScriptLevel``` | EPS PostScript level setting. | String  |  | ✓ |
| ```EPS:Colour``` | EPS colour setting. | String |  | ✓ |
| ```EPS:Preview``` | EPS preview setting. | Y/N |  | ✓ |
| ```EPS:EmbedFonts``` | EPS embed fonts setting. | Y/N |  | ✓ |
| ```EPS:DataFormat``` | EPS data format setting. | Y/N |  | ✓ |

#### ```INDD``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```INDD:Format``` | | String |  | ✓ |
| ```INDD:CombineFiles``` | | Y/N |  | ✓ |
| ```INDD:Package``` | | Y/N |  | ✓ |
| ```INDD:PackageLinks``` | | Y/N |  | ✓ |
| ```INDD:PackageFonts``` | | Y/N |  | ✓ |
| ```INDD:PackageCreateIDML``` | | Y/N |  | ✓ |
| ```INDD:PackageCreatePDF``` | | Y/N |  | ✓ |
| ```INDD:PackagePDFPreset``` | | String |  | ✓ |
| ```INDD:PackageCreateReport``` | | Y/N |  | ✓ |
| ```INDD:PackageCreateFolder``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveDocumentSlug``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemovePageColours``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveLayerColours``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveHiddenSpreads``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveHiddenItems``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveUnusedParents``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveEmptyLayers``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveUnusedStyles``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveUnusedPages``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveUnusedItems``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveUnusedSwatches``` | | Y/N |  | ✓ |
| ```INDD:CleanupRemoveUnusedGuides``` | | Y/N |  | ✓ |

#### ```IDML``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```IDML:Format``` | | String |  | ✓ |
| ```IDML:CombineFiles``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveDocumentSlug``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemovePageColours``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveLayerColours``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveHiddenSpreads``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveHiddenItems``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveUnusedParents``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveEmptyLayers``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveUnusedStyles``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveUnusedPages``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveUnusedItems``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveUnusedSwatches``` | | Y/N |  | ✓ |
| ```IDML:CleanupRemoveUnusedGuides``` | | Y/N |  | ✓ |

#### ```Preset``` References
| Reference | Description | Data | Range | Template |
| - | - | - | - | - |
| ```Preset:Name``` | Preset name. | String | ✓ | ✓ |
| ```Preset:Source``` | Preset location name. | String | ✓ | ✓ |
| ```Preset:Description``` | Preset description. | String | ✓ | ✓ |
| ```Preset:Author``` | Preset author. | String | ✓ | ✓ |
| ```Preset:Created``` | Creation date. | String | ✓ | ✓ |
| ```Preset:Modified``` | Modification date. | String | ✓ | ✓ |

#### Spacers
*Spacers can be defined by each preset and changed in the modifier UI*
| Reference | Description | Range | Template |
| - | - | - | - |
| ```\|``` | Spacer. |  | ✓ |

#### Folder & File Separators
| Reference | Description | Range | Template |
| - | - | - | - |
| ```</>``` | Folder path separator. |  | ✓ |

#### String Wrapper
*String tags allow strings to be wrapped inside a tag making them editable my modifier queries.*
| Reference | Description | Range | Template |
| - | - | - | - |
| ```''``` | String tag. |  | ✓ |


<br /><br />

### 9. Thank You

Thank you for using Awesome Exporter.

This software is being actively developed and if you're using the extension, I'd love to hear your feedback, suggestions or bug reports. If you need help with anything, or if something isn't working as expected, please get in touch via [hello@modocodo.com](mailto:hello@modocodo.com?subject=Awesome%20Exporter%20Feedback) and I'll do my best to help. Thank you too to everyone who has been in touch and shared how the plugin has integrated into their workflow and helped their businesses.

© 2024 [Modocodo](https://modocodo.com)<br />[hello@modocodo.com](mailto:hello@modocodo.com?subject=Awesome%20Exporter)

*Last updated: February 2025.*

Stay Awesome.