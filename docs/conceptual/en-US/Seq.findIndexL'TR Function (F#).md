# Seq.findIndex<'T> Function (F#)

Returns the index of the first element for which the given function returns **true**.

**Namespace/Module Path**: Microsoft.FSharp.Collections.Seq

**Assembly**: FSharp.Core (in FSharp.Core.dll)


## CAPS_SYNTAX_MD



```


// Signature:
Seq.findIndex : ('T -> bool) -> seq<'T> -> int

// Usage:
Seq.findIndex predicate source


```



#### CAPS_PARAMETERS_MD
*predicate*
Type: **'T -&gt;**[bool](http://msdn.microsoft.com/en-us/library/89c0cf9c-49ce-4207-a3be-555851a67dd5)


A function to test whether the index of a particular element should be returned.


*source*
Type: [seq](http://msdn.microsoft.com/en-us/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)**&lt;'T&gt;**


The input sequence.



**exceptions tag is not supported!!!!**
**The index of the first element for which the given function returns true.**
## CAPS_REMARKS_MD
This function is named **FindIndex** in compiled assemblies. If you are accessing the function from a language other than F#, or through reflection, use this name.

**The following code example shows how to use Seq.findIndex.**


```



    let seqA = [| 2 .. 100 |]
    let delta = 1.0e-10
    let isPerfectSquare (x:int) =
        let y = sqrt (float x)
        abs(y - round y) < delta
    let isPerfectCube (x:int) =
        let y = System.Math.Pow(float x, 1.0/3.0)
        abs(y - round y) < delta
    let element = Seq.find (fun elem -> isPerfectSquare elem && isPerfectCube elem) seqA
    let index = Seq.findIndex (fun elem -> isPerfectSquare elem && isPerfectCube elem) seqA
    printfn "The first element that is both a square and a cube is %d and its index is %d." element index


```



**Output**
**The first element that is both a square and a cube is 64 and its index is 62.**
## Platforms
Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 2.0, 4.0, Portable




## See Also
[Collections.Seq Module &#40;F&#35;&#41;](Collections.Seq+Module+%28F%23%29.md)

[Microsoft.FSharp.Collections Namespace &#40;F&#35;&#41;](Microsoft.FSharp.Collections+Namespace+%28F%23%29.md)
