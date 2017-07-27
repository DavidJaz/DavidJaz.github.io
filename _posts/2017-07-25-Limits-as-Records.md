---
published: false
---
## Record and Union Types in Elm as Limits and Colimits

[Elm](http://elm-lang.org/) is a pleasant little functional language for making web apps. Here, I want to explain how [record types](http://elm-lang.org/docs/records#record-types) in Elm are like limits, and [union types](https://guide.elm-lang.org/types/union_types.html) are like colimits -- at least in some cases. My hope is more that this will build intuition for limits and colimits than the other way around.

A record type is a way of packaging a bunch of data together. 

