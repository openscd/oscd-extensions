# oscd-extensions

Here we are collecting extension namespaces to IEC 61850-6 used within the OpenSCD ecosystem.

If you have identified a need for an extension namespace that in your opinion is of use for the OpenSCD ecosystem and not for your individual project feel free to open a PR with a XSD file defining the namespace.

> Please make sure to check existing namespaces before proposing a new one. We generally want to avoid multiple namespaces for the same purpose. If an existing namespace is somewhat but not fully serving your purpose, please request a change to this one first.

> Please be aware that adding a new namespace here is something which is likely to require considerable debate and discussion and take some time. Once agreed, concerns around extendability, maintenance and backwards compatibility will be important. The review process is something we take seriously and we may request changes along the way.

## Verifying a file with a schema

To use a schema for validating an SCL file in a text editor, add a schema reference to it.
For instance if the schema is in the same folder as the SCL file, add a schema reference as follows to the SCL element by adding a namespaced attribute.
For example with the SLD schema:

```xml
<SCL ... xsi:schemaLocation="https://openscd.org/SCL/SSD/SLD/v0 ssd-sld-v0.xsd" ...>
```

You will also need to ensure the `xsi` schema is defined on the document element:

```xml
<SCL ... xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" ...>
```

On an SCL document element this could look like:

```xml
<SCL xmlns="http://www.iec.ch/61850/2003/SCL" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	version="2007" revision="B" release="4" xmlns:eosld="https://openscd.org/SCL/SSD/SLD/v0"
	xsi:schemaLocation="https://openscd.org/SCL/SSD/SLD/v0 ssd-sld-v0.xsd">
```

This is known to work with the XML Tools extension in VS Code.
