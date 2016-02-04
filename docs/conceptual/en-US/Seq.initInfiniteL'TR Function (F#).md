# Seq.initInfinite<'T> Function (F#)

Generates a new sequence which, when iterated, will return successive elements by calling the given function.

**Namespace/Module Path:** Microsoft.FSharp.Collections.Seq

**Assembly:** FSharp.Core (in FSharp.Core.dll)


## CAPS_SYNTAX_MD



```


// Signature:
Seq.initInfinite : (int -> 'T) -> seq<'T>

// Usage:
Seq.initInfinite initializer


```



#### CAPS_PARAMETERS_MD
*initializer*
Type: [int](http://msdn.microsoft.com/en-us/library/025d5455-3622-4ea5-9573-3ecbd4ee1375)**-&gt; 'T**


A function that generates an item in the sequence from a given index.



**The result sequence.**
## CAPS_REMARKS_MD
The results of calling the function will not be saved, that is the function will be reapplied as necessary to regenerate the elements. The function is passed the index of the item being generated.

Iteration can continue up to **Int32.MaxValue**.

This function is named **InitializeInfinite** in compiled assemblies. If you are accessing the function from a language other than F#, or through reflection, use this name.


## Thread Safety
The returned sequence may be passed between threads safely. However, individual **IEnumerator** values generated from the returned sequence should not be accessed concurrently.

**The following example shows the use of Seq.initInfinite to create a sequence 1/n^2, with alternating signs.**


```



let seqInfinite = Seq.initInfinite (fun index ->
    let n = float( index + 1 )
    1.0 / (n * n * (if ((index + 1) % 2 = 0) then 1.0 else -1.0)))
printfn "%A" seqInfinite


```



**seq [-1.0; 0.25; -0.1111111111; 0.0625; ...]**
## Platforms
Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 2.0, 4.0, Portable




## See Also
[Collections.Seq Module &#40;F&#35;&#41;](Collections.Seq+Module+%28F%23%29.md)

[Microsoft.FSharp.Collections Namespace &#40;F&#35;&#41;](Microsoft.FSharp.Collections+Namespace+%28F%23%29.md)
