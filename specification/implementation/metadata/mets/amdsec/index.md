### 5.3.4.	Use of the METS administrative metadata section (element amdSec)
The purpose of the METS administrative metadata section is to embed or refer to files containing administrative metadata about the IP content objects. CSIP is only using referencing of files containing administrative metadata. 

The administrative metadata section contains four sections technical metadata (element techMD)>, rights metadata (element rightsMD), source metadata (element sourceMD) and digital provenance metadata (element digiprovMD). The techMD element records technical metadata about content files, rightsMD records intellectual property rights information, sourceMD records descriptive, technical or rights information about an analog source document used to generate the digital library object, and digiprovMD records digital preservation information, such as information about the digital library object's life-cycle and history.

The CSIP only describes use of preservation metadata and rights metadata. The other sections can be used in a local implementation.

The CSIP (and METS) categorises preservation metadata as administrative metadata, specifically Digital Provenance metadata (following the avaiable guidelines), hence all preservation metadata should be referenced from a digiprovMD element within the amdSec.

The METS amdSec element must include references to all relevant metadata located in the folder “metadata/preservation”. This means also that the root level `METS.xml` file must refer only to the root level preservation metadata and the representation `METS.xml` file must refer only to the representation level preservation metadata.

The METS amdSec element must include references to all relevant metadata which should be locat
ed in the “metadata/preservation” folder. This means also that the root level `METS.xml` file must refer only to the root level preservation metadata and the representation `METS.xml` file must refer only to the representation level preservation metadata.

The placement of PREMIS metadata for preservation in this section follows the PREMIS EC guidelines: <http://www.loc.gov/standards/premis/guidelines2017-premismets.pdf>

The specific requirements for the amdSec element, its sub-elements and attributes are presented in the following table.
