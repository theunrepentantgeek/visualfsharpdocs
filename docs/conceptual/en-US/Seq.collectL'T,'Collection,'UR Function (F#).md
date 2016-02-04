# Seq.collect<'T,'Collection,'U> Function (F#)

Applies the given function to each element of the sequence and concatenates all the results.

**Namespace/Module Path:** Microsoft.FSharp.Collections.Seq

**Assembly:** FSharp.Core (in FSharp.Core.dll)


## CAPS_SYNTAX_MD



```


// Signature:
Seq.collect : ('T -> 'Collection) -> seq<'T> -> seq<'U> (requires 'Collection :> seq<'U>)

// Usage:
Seq.collect mapping source


```



#### CAPS_PARAMETERS_MD
*mapping*
Type: **'T -&gt; 'Collection**


A function to transform elements of the input sequence into the sequences that are concatenated.


*source*
Type: [seq](http://msdn.microsoft.com/en-us/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)**&lt;'T&gt;**


The input sequence.



**exceptions tag is not supported!!!!**
**The result sequence.**
## CAPS_REMARKS_MD
The sequence is evaluated lazily. Therefore, effects are delayed until it is enumerated.

This function is named **Collect** in compiled assemblies. If you are accessing the function from a language other than F#, or through reflection, use this name.

**The following code demonstrates the use of Seq.collect.**


```



    let addNegations seq1 =
       Seq.collect (fun x -> seq { yield x; yield -x }) seq1
       |> Seq.sort
    addNegations [ 1 .. 4 ] |> Seq.iter (fun elem -> printf "%d " elem)
    printfn ""
    addNegations [| 0; -4; 2; -12 |] |> Seq.iter (fun elem -> printf "%d " elem)


```



**Output**
**-4 -3 -2 -1 1 2 3 4**
**-12 -4 -2 0 0 2 4 12**
## Platforms
Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 2.0, 4.0, Portable




## See Also
[Collections.Seq Module &#40;F&#35;&#41;](Collections.Seq+Module+%28F%23%29.md)

[Microsoft.FSharp.Collections Namespace &#40;F&#35;&#41;](Microsoft.FSharp.Collections+Namespace+%28F%23%29.md)
