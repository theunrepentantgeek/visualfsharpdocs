# ExtraTopLevelOperators.eprintfn<'T> Function (F#)

Print to **stderr** using the given format, and add a newline.

**Namespace/Module Path**: Microsoft.FSharp.Core.ExtraTopLevelOperators

**Assembly**: FSharp.Core (in FSharp.Core.dll)


## CAPS_SYNTAX_MD



```


// Signature:
eprintfn : TextWriterFormat<'T> -> 'T

// Usage:
eprintfn format


```



#### CAPS_PARAMETERS_MD
*format*
Type: [TextWriterFormat](http://msdn.microsoft.com/en-us/library/2080c4a5-7bdd-4a01-8e01-10b498af92de)**&lt;'T&gt;**




## CAPS_REMARKS_MD
This function is named **PrintFormatLineToError** in compiled assemblies. If you are accessing the function from a language other than F#, or through reflection, use this name.

**The following code example illustrates the use of eprintfn.**


```



    let maxValue = 10
    let function1 x =
       if (x > maxValue) then
           eprintfn "Error: the input %d exceeds the maximum value, %d." x maxValue
       else
           printfn "Success!"
    function1 1
    function1 11


```



**Output**
**Success!**
**Error: the input 11 exceeds the maximum value 10.**
## Platforms
Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 2.0, 4.0




## See Also
[Core.ExtraTopLevelOperators Module &#40;F&#35;&#41;](Core.ExtraTopLevelOperators+Module+%28F%23%29.md)

[Microsoft.FSharp.Core Namespace &#40;F&#35;&#41;](Microsoft.FSharp.Core+Namespace+%28F%23%29.md)
