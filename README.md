# CodeWriter

[![NuGet Status](http://img.shields.io/nuget/v/CodeWriter.svg?style=flat)](https://www.nuget.org/packages/CodeWriter/)
[![Build status](https://ci.appveyor.com/api/projects/status/r1ofr28tpxqb30f9?svg=true)](https://ci.appveyor.com/project/veblush/codewriter)
[![Coverage Status](https://coveralls.io/repos/github/SaladLab/CodeWriter/badge.svg?branch=master)](https://coveralls.io/github/SaladLab/CodeWriter?branch=master)
[![Coverity Status](https://scan.coverity.com/projects/8379/badge.svg?flat=1)](https://scan.coverity.com/projects/saladlab-codewriter)

CodeWriter is a small helper class for generating code concisely. It helps writing
neat code which generates code dynamically.

Following code generates C# code on the fly:
```csharp
var w = new CodeWriter.CodeWriter(CodeWriterSettings.CSharpDefault);
using (w.B("class Test"))
{
    using (w.B("public static int Sum(int a, int b)"))
    {
        w._("var r = a + b;",
            "return r;");
    }
}
Console.Write(w.ToString());
```

Output:
```csharp
class Test
{
    public static int Sum(int a, int b)
    {
        var r = a + b;
        return r;
    }
}
```

## Where can I get it?

```
PM> Install-Package CodeWriter
```
