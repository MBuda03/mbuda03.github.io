---
layout: post
title: Lets Learn Umbraco 3 - Document Types
tags: [Umbraco]
categories: ['Umbraco', 'LetsLearnSeries']
---

Unlike other Content Management Systems, the way Umbraco works is, you don't
create a page and you are done. You need to create a Document Type.

## Document Types

We can think Document Types as a data container in Umbraco in which we can add
data fields / attributes to it. The only limit to extending document types is
your imagination. Or if you want to, you can think document type as a content list
for a page that has to contain.
An example of a Document Type with it's data fields can be the following homepage,
with the following data fields and their respective types.

- Homepage
    - Page title -> Text
    - Sub Heading -> Text
    - Body Text -> Rich Text Body


Remember that different kind of pages need different document types and create a
new Doc Type:
    - if you think you do
    - for every design template


If you want to read more about Document Types you can use
[this link](https://our.umbraco.org/documentation/tutorials/creating-basic-site/Document-Types)

### Creating a Document Type
Let's create the Home Page of our website. In order to do this, go to;

- Settings -> Document Types -> Click on the '...' and select Document Type
    - We will cover other two options later.
- Give your Document Type a name that suits, I've gone with "Home Page"
- Now go to "Content" section on the left menu and create a new content with
a name of your choosing, I've gone with "Welcome"


### Tabs and Properties
The main reason Umbraco tabs exist to organise properties. Even though at the
time of creating the homepage content which we named as "Welcome" without any
tabs, Umbraco automatically added several tabs and properties such as:

- Name
- Id
- Created By
- Created
- Last Edited
- Document Type
- Publish At
- Unpublish At
- Template
- Link to document

If we want to store and manage any other property besides these, we have to
manually enter those tabs and properties to the page. In order to add any tab to
our page, we follow the following route:

Settings -> Document Type -> Home Page -> Add New Tab -> Give any name you want

After entering the name, you will see a right bar appearing which we can enter
another name to it, which will be visible to our content editors in our content
section. Now let's create a rich text editor for our page.

At the same sidebar which we entered the tabs name, click on "Add Editor" and find
"Rich Text Editor". Add it, hit save and submit it.

Now, check the Welcome content we created in the content section, you will see
a new section appearing.

### Datatypes

When we are adding a property to a document type, we need to define a Datatype
for each of the property we are adding. A datatype determines the type of control
displayed to our content editor. Therefore it is very important to choose the
proper datatype.

Most common default datatypes:
- Checkbox list
- Date Picker
- Dropdown
- Label
- etc...

### Master Document Type

It allows to use inheritance between document types. By using Master Document Types
to inherit the properties of another Document Type rather than recreating the properties
every time.
