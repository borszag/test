<pre class="Agda"><a id="9" class="Keyword">module</a> <a id="16" href="README.html" class="Module">README</a> <a id="23" class="Keyword">where</a>
</pre># The Agda smallib library, version 0.0-dev
This library implements a type theory which is described in the
Appendix of the HoTT book. It also contains some properties derived
from the rules of this theory.

This project is meant to be a practice for the author but as a
secondary goal it would be nice to create a small library which is
less intimidating than the standard one.

This version was tested using Agda 2.6.1.

## High-level overview of contents
The top-level module L is not implemented (yet), it's sole purpose
is to prepend all of the module names with something to avoid
possible name clashes with the standard library.

The structure of the library is the following:
- Base
   The derivation rules of the implemented type theory and some
   useful properties which can be derived from these. To make a
   clear distinction between these every type has a Core and a
   Properties submodule. In some cases the latter might be empty.

- Data
  - Bool
     A specialized form of the Coproduct type. It implements if as
     an elimination rule. The following operations are defined on
     them: not, ∧, ∨, xor.

## Some useful modules
- To use several things at once
<pre class="Agda"><a id="1222" class="Keyword">import</a> <a id="1229" href="L.Base.html" class="Module">L.Base</a>      <a id="1241" class="Comment">-- Type theory with it&#39;s properties.</a>
<a id="1278" class="Keyword">import</a> <a id="1285" href="L.Base.Core.html" class="Module">L.Base.Core</a> <a id="1297" class="Comment">-- Derivation rules.</a>
</pre>
- To use only one base type
<pre class="Agda"><a id="1359" class="Keyword">import</a> <a id="1366" href="L.Base.Sigma.html" class="Module">L.Base.Sigma</a>     <a id="1383" class="Comment">-- Products (universe polymorphic).</a>
<a id="1419" class="Keyword">import</a> <a id="1426" href="L.Base.Coproduct.html" class="Module">L.Base.Coproduct</a> <a id="1443" class="Comment">-- Disjoint sums (universe polymorphic).</a>
<a id="1484" class="Keyword">import</a> <a id="1491" href="L.Base.Empty.html" class="Module">L.Base.Empty</a>     <a id="1508" class="Comment">-- Empty type.</a>
<a id="1523" class="Keyword">import</a> <a id="1530" href="L.Base.Unit.html" class="Module">L.Base.Unit</a>      <a id="1547" class="Comment">-- Unit type.</a>
<a id="1561" class="Keyword">import</a> <a id="1568" href="L.Base.Nat.html" class="Module">L.Base.Nat</a>       <a id="1585" class="Comment">-- Natural numbers.</a>
<a id="1605" class="Keyword">import</a> <a id="1612" href="L.Base.Id.html" class="Module">L.Base.Id</a>        <a id="1629" class="Comment">-- Propositional equality (universe poly.).</a>
</pre>
- Some datatypes
<pre class="Agda"><a id="1703" class="Keyword">import</a> <a id="1710" href="L.Data.Bool.html" class="Module">L.Data.Bool</a> <a id="1722" class="Comment">-- Booleans.</a>
</pre>
## Notes
- L.Base exports L.Coproduct.Core._+_ as _⊎_ to avoid multiple
  definitions of _+_, as L.Base.Nat declares it as well.
