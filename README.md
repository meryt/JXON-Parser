#JXON - JavaScript XML Object Notation
This JXON library provides the core functionality to create JSON objects from XML, preserving as
much of the original XML information as possible.

##Why JXON?
Why even need a JSON from XML converter?  While front-end development utilizes JavaScript and JSON for 
their language and data model, most of the web still uses XML as a means of communicating between systems.  JXON
helps bridge the gap between getting XML data and consuming it in JavaScript based systems.

##Features
This current version of the JXON parser is very limited, only converting XML to JSON format.  The JXON module contains
2 classes:
* JXONNode - A base object that all JSON object inherit from.
* Parser - The XML parser that converts XML to JXON.

##How to use
Using this JXON library is fairly straight forward.

You start by instantiating an instance of the JXON Parser.
	var parser = new JXON.Parser();

At that point, you have 3 parsing options:
* parser.parseNode - Converts an object implementing IXMLDOMElement interface into a JXONNode object.
	var jxon = parser.parseNode(someXMLElement);

* parser.parseXML - Converts any XML string into a JXONNode object, including all children nodes.
	var jxon = parser.parseXML(someXMLText);

* parser.parseXMLFile - Loads and converts any XML file into a JXONNode object.  parser.parseXMLFile can be either synchronous or asynchronous.
	var jxon = parser.parseXMLFile("http://some.xml.file")
	// or
	parser.parseXMLFile("http://some.xml.file", function(jxon)
	{
	});

##Dependencies
JXON currently has no external dependencies

##Browser Support
JXON currently supports IE8+ as well as all modern browsers.  Although it may also work in older versions of IE, it 
is not support and will never be supported.