# CSharp2Colorized

This is a command-line utility and a nuget package for colorizing C#.

You can run the command-line utility in a few ways:

```
echo "Console.WriteLine();" | csharp2colorized
csharp2colorized file1.cs file2.cs
csharp2colorized *.cs
```

You can call the library like this:

```csharp
using CSharp2Colorized;

var pre = CSharp2Colorized.Lines2Html(CSharp2Colorized.ColorizeCSharp(code));
Console.WriteLine($"<html><body>{pre}</body></html>");
``````

