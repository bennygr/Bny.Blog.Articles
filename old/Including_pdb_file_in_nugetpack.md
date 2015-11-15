<!--
Title:"Debugging nuget packages using pdb files",
Date:"2014-05-22T16:01+0200",
Tags:"C#,.NET",
PreviewLength:"300",
-->

The usual way to debug a nuget package is to publish the symbols of the package to a symbol server.
If you don't want to host your own server but rather want to use a network share to publish your nuget packages you can add your debug symbols into the package by adding them to the `files` section of your nuspec file.

```xml
<?xml version="1.0"?>
<package >
  <metadata>
    <id>$id$</id>
    <version>$version$</version>
    <title>$title$</title>
    <authors>Your name</authors>
    <owners>$author$</owners>
    <requireLicenseAcceptance>false</requireLicenseAcceptance>
    <copyright>2014</copyright>
    <description>Some useful description</description>
  </metadata>
  
    <files>
		<file src="bin\$Configuration$\*.pdb" target="lib\net20" />    
	</files>  
</package>

```

Does anyone know how to define the target dynamically based on the target framework used by the project (something like target="lib\$framework$")?



