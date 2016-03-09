# JavaAppXMLFiles

Java Application that processes XML Files and produces output as html, MySQL and PHP file scripts.

XML Parsing

In this project, I write a Java application that processes XML files containing information about data input forms. The Java application takes as command line input an XML file name/URL and produces as output the following four files:
An HTML file that contains code to display the data input form on a browser. The HTML code must include Javascript to perform some basic validation such as data type checking for text box input.
An Oracle SQL or MySQL script file that contains create table statements to create relational table(s) that can accept data submitted from the data input form.
A Java servlet or PhP source file containing code to process data submitted by the user using the data input form. The program should simply insert the data into the database table(s).
A Java servlet or PhP source file that contains code to display contents of the database in tabular form.

Data Input Forms

A data input form consists of one or more form elements that is capable of accepting input from a user. I have considered 7 types of form elements: textbox, submit, reset, check box, radio buttons, select list, and multiple select list. Each of these form elements except for submit and reset has a datatype (integer, decimal, or string) associated with it. If a datatype is not provided, string would be assumed as the default data type.
If a data input form contains at least one multiselect form element or a check box group of two or more check boxes, one or more of the remaining (single valued) form elements must be classified as key elements. This is to facilitate creating a separate relational table for storing the multiple select values.

The data input form is described in XML.

XML Schema for Data Input Forms

Every data input form must have a title element which must have a caption sub-element. The id attribute of the root element is ignored.
Following the title element, the data input form may have one or more form elements which can be one of 7 form element types described earlier.
Any number of break elements may be present between form elements or between the different options in a check box group or radio button group.
The textbox element must have at least the name, caption, and maxlength sub-elements; the size sub-element is optional.
The checkboxes element must contain a name, caption, and checkboxgroup sub-elements. Within the checkboxgroup element, we may have one or more checkbox element each with a value and caption sub-element. The checkbox element may have an optional attribute called status whose value is always "checked".
The radio button element is similar to checkboxes.
The select element has a name, caption, and options sub-elements. The options element has one or more option sub-elements, each of which has a value and caption sub-element.
The multiselect element is similar to the select element except that it has an additional sub-element, size, which indicates the size of the select window.
Semantic Checks

XML parser program should check for semantic errors such as form element without a name or caption, more than one form element having the same name, data type mis-match, etc. and report these. No output is generated in this case.
