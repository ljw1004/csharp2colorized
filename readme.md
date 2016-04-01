# CSharp2Colorized

This is a command-line utility and a nuget package for colorizing C#. It's goal is to give good colorization even for incomplete code snippets, e.g. just expressions or statements. Also to colorize what presumably are typenames even when the typename hasn't been defined. Here's how it stacks up:

```csharp
B b = new B(); ((A)b).P = 1;
```

|-----------|-------------|
| Markdown | <pre>B b = new B(); ((A)b).P = 1;</pre> |
| csharp2colorized | <pre><span style="color:#2b91af">B</span> b = <span style="color:#0000ff">new</span> <span style="color:#2b91af">B</span>(); ((<span style="color:#2b91af">A</span>)b).P = 1;</pre> |
| Visual Studio | <pre>B b = <span style="color:#0000ff">new</span> B(); ((A)b).P = 1;</pre> |


You can run the command-line utility in a few ways:

```
echo "Console.WriteLine();" | csharp2colorized
csharp2colorized file1.cs file2.cs file3.vb
csharp2colorized *.cs
csharp2colorized -vb *.*
csharp2colorized tests.md > results.html
```

You can call the library like this:

```csharp
using CSharp2Colorized;

var pre = CSharp2Colorized.Lines2Html(CSharp2Colorized.ColorizeCSharp(code));
Console.WriteLine($"<html><body>{pre}</body></html>");
```

Development notes: if you're developing on this project, the 