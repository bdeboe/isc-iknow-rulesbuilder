# iKnow Rules Builder Demo App

This demo application can be used to demonstrate how you can leverage classic iKnow matching to build composite "rules" that represent particular patterns to be extracted from natural language text. Dictionary items can be assembled into sequences of which some elements may be optional and others aren't, and take into account the negation context of matched elements. 

The application also includes code to "parse" the paragraph structure of texts with various numbering patterns, which might be usable for other scenarios, independent of the rules building functionalities. The paragraph numbering detection allows for several typical OCR issues ("_11._" rather than "_ii._"). See the code in Demo.RulesBuilder.Paragraph:ParseString() for more details.


### Installation notes
* Import associated code
* Create a REST handler web application by invoking Demo.RulesBuilder.Utils:CreateRestWebApp() in your namespace of choice
* Access the application through http://localhost:_port_/csp/_namespace_/RulesBuilder.csp?_123_ where _123_ is the ID of the domain managed by Demo.RulesBuilder.ParagraphDomain, which you can access from its %GetDomainId() method.


### Other notes
* Note that Demo.RulesBuilder.ParagraphDomain is configured to allow updating the dictionaries through the GUI and the <matching> element therein will not drop any GUI-supplied entries when rebuilding the domain. 


### TODO
* possibly source nicer dictionary building infrastructure from https://github.com/bdeboe/isc-iknow-dictbuilder
* possibly let the dictionary GUI manage the dictionary elements straight in the domain definition XML, to simplify exporting and avoid confusion of what's defined in the domain and what's just in the XML
