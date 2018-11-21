---
title: Use of the METS root element
---
### 5.3.1.	Use of the METS root element (element mets)
The purpose of the METS root element is to describe the container for the information being stored and/or transmitted. The implementation of the root element for a METS document conformant with CSIP uses attributes from the METS specification and attributes added for the purposes of the CSIP.

In addition to the attributes the METS root element mets MUST define all relevant namespaces and locations of XML schemas using the `@xmlns` and `@xsi:schemaLocation` attributes. 

In case XML schemas have been included into the package (i.e. placed into the `schemas` folder) it is recommended to link to the schemas using the relative path of the schema file (i.e. `schemas/mets.xsd`). 

The specific requirements for the root element and its attributes are described in the following table .

{% comment %} PAGE TEMPLATING : DO NOT DELETE THIS OR THE FOLLOWING LINE {% endcomment %}
{% include_relative requirements.md %}

Full example of the METS root element:

{% comment %} PAGE TEMPLATING : DO NOT DELETE THIS OR THE FOLLOWING LINE {% endcomment %}
{% include_relative examples.md %}
