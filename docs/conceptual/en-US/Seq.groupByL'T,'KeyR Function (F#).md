# Seq.groupBy<'T,'Key> Function (F#)

Applies a key-generating function to each element of a sequence and yields a sequence of unique keys and a sequence of all elements that have each key.

**Namespace/Module Path:** Microsoft.FSharp.Collections.Seq

**Assembly:** FSharp.Core (in FSharp.Core.dll)


## CAPS_SYNTAX_MD



```


// Signature:
Seq.groupBy : ('T -> 'Key) -> seq<'T> -> seq<'Key * seq<'T>> (requires equality)

// Usage:
Seq.groupBy projection source


```



#### CAPS_PARAMETERS_MD
*projection*
Type: **'T -&gt; 'Key**


A function that transforms an element of the sequence into a comparable key.


*source*
Type: [seq](http://msdn.microsoft.com/en-us/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)**&lt;'T&gt;**


The input sequence.



**A sequence of tuples where each tuple contains the unique key and a sequence of all the elements that match the key.**
## CAPS_REMARKS_MD
This function returns a sequence that traverses the whole initial sequence as soon as that sequence is iterated. As a result this function should not be used with large or infinite sequences. The function makes no assumption on the ordering of the original sequence.

This function is named **GroupBy** in compiled assemblies. If you are accessing the function from a language other than F#, or through reflection, use this name.

**The following example demonstrates the use of Seq.groupBy to group the odd and even numbers in a sequence into two separate sequences.**


```



    let sequence = seq { 1 .. 100 }
    let printSeq seq1 = Seq.iter (printf "%A ") seq1; printfn ""
    let sequences3 = Seq.groupBy (fun index ->
        if (index % 2 = 0) then 0 else 1) sequence
    sequences3 |> printSeq


```



**(1, seq [1; 3; 5; 7; ...]) (0, seq [2; 4; 6; 8; ...])**
## Platforms
Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 2.0, 4.0, Portable




## See Also
[Collections.Seq Module &#40;F&#35;&#41;](Collections.Seq+Module+%28F%23%29.md)

[Microsoft.FSharp.Collections Namespace &#40;F&#35;&#41;](Microsoft.FSharp.Collections+Namespace+%28F%23%29.md)
