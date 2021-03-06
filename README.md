[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) ![GitHub repo size](https://img.shields.io/github/repo-size/testoxide/sepa-iso2K22-BulkGen) ![platform](https://img.shields.io/badge/platform-win--32%20%7C%20win--64-lightgrey)
<!--![GitHub release (latest by date)](https://img.shields.io/github/v/release/testoxide/vbsx-Validator)-->

# sepa-iso2K22-BulkGen
1) Tested for supporting PAIN.008.001.001 and PAIN.008.001.002 (version 1&2)
2) The XML is generated based on core ISO2022 XML specification and does not support or include any 'Bank' or 'Financial Institution' specific rules or customization.
3) Please note that the App does not consider or support any 'Bank' or 'Financial Institution' or such 'Entity' specific rules or customization. Since organizational rules vary.
4) However the app is quite scalable and any such specific rules or customization can be easily built on top of the existing codebase (on-demand) since it already provides a ground framework.
5) Feel free to submit such business rule specification as requirement or enhancement on the project issue tracker.

**Note: PAIN008, PAIN001, PACS003 and PACS008 Generation is complete (ModeGenOnly). Other two modes are pending i.e. ModeValOnly and ModeValAndGen.**

### Download

Please do not download from source code section as it may not be stable.

Instead use any latest stable release version, available for download from _[Releases](https://github.com/testoxide/sepa-iso2K22-BulkGen/releases)_ section

### How To run

Simply double-click the main script file named 'VBSX_Main.vbs' to launch the utility. This will launch the command line interface.
Please note that you might get UAC prompt if UAC is enabled on your windows.

**Note :** _Drag and Drop may work with UAC disabled._
<!--
_Refer [Wiki](https://github.com/testoxide/vbsx-Validator/wiki) for usage tips, screenshots and [video demo](https://github.com/testoxide/vbsx-Validator/wiki/Video-Demo-&-Overview)_
-->

### Prerequisites

Win 7 / 8 / Server.

User provided 'seed' or 'template' file for each specific file type (pain008, pacs003) to be produced.

MSXML6 Official Download [here](https://www.microsoft.com/en-us/download/details.aspx?id=3988)

Require admin privileges / script execution privileges (elevated UAC prompt) on your windows system.


### Technical Notes (Design)


* The Parser has been designed _'not to resolve externals'_. It does not evaluate or resolve the 'schemaLocation' or other attributes specified in DocumentRoot for locating schemas. The reason is that most of the time schemaLocation is not always valid or resolvable as XML travels system to system. _Hence this design avoids non-schema related errors_.

* The parser _validates strictly against the supplied XSD_ (schema definition) only without auto-resolving schemaLocation or other nameSpace attributes from the XML document. This provides robust validation against supplied XSD. Also the validation parser inherently validates all XML for well-formedness / structural.

* The validation _parser needs Namespace (targetNamespace)_ which is currently _extracted from the supplied XSD_. Please make sure that 'targetNamespace' declaration if any, in your XSD is correct. The _targetNamespace decalaration is not mandatory_ and hence XSD without targetNamespace are also validated properly.


<!--* Please refer ['Further Reading'](https://github.com/testoxide/vbsx-Validator/wiki/Additional-Notes) section of Wiki for more information if required.-->


### Built With

* [VBScript](https://docs.microsoft.com/en-us/dotnet/visual-basic/language-reference/)
* [WScript](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc738350(v=ws.10)) 
* [MSXML6](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/ms763742(v%3dvs.85))


### Known Issues / Bugs

Please refer the [Issue list](https://github.com/testoxide/sepa-iso2K22-BulkGen/issues).

Feel free to contribte by logging any new defects, issues or enhancement requests

### Authors

* **Tushar Sharma**


### License

This is licensed under the Apache-2.0 License - see the [LICENSE.md](https://github.com/testoxide/sepa-iso2K22-BulkGen/blob/master/LICENSE) file for details

