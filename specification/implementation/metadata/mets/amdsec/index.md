### 5.3.4.	Use of the METS administrative metadata section (element amdSec)
The purpose of the METS administrative data section is to embed or refer to files containing administrative metadata about the IP content objects. CSIP is only using referencing of files containing administrative metadata. The CSIP (and METS) categorises preservation metadata as administrative metadata, specifically Digital Provenance metadata (following the avaiable guidelines), hence all preservation metadata should be referenced from a digiprovMD element within the amdSec.

The administrative metadata section also contains information regarding rights statements. Regardless of which standard that is used for registering the rights metadata all the rights metadata should be reference from a rightsMD element within the amdSec. Standards that can be used includes the collaborative work from RIGHTSTATMENTS.ORG <http://rightsstatements.org> , Europena right statements <https://pro.europeana.eu/page/available-rights-statements> , the METS Rights Schema <https://github.com/mets/METS-Rights-Schema> created and maintaned by the METS Board, the rights part of PREMIS <http://www.loc.gov/standards/premis/> as well as own local rights statements in use.</p>
                    <dl xmlns="http://www.w3.org/1999/xhtml">
The METS amdSec element must include references to all relevant metadata which should be located in the folder “metadata/preservation”. This means also that the root level `METS.xml`
file must refer only to the root level preservation metadata and the representation `METS.xml` file must refer only to the representation level preservation metadata.

Decision regarding placement of PREMIS metadata for preservation in this section is following the guide lines available from PREMIS EC <http://www.loc.gov/standards/premis/guidelines2017-premismets.pdf>.

The specific requirements for the amdSec element, its sub-elements and attributes are presented in the
following table.
