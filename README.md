# QED

Q's Experimental Debugger

Integrating modern program analysis techniques inside a debugger. Please note the "E" in QED, this is very experimental, **do not use as a stable debugger**.
***

### Core Features
**[12/31/2015]** The biggest idea I want to explore first is modeling a binary as a graph, which is not a [new](http://mlsec.org/joern) idea but it is what I intend to do with the graph that I think will be interesting. The debugger will be based on [LLDB](http://lldb.llvm.org) because it is extremely modular, built as a series of components instead of a monsterish [monolithic](https://www.gnu.org/software/gdb/) code-base. To start I will attempt the route of [McSema](https://github.com/trailofbits/mcsema) and attempt to recover the Control Flow Graph using IDA as a place to start. I really dig the ideas behind [QIRA](http://qira.me/) as well, and may work on introducing QED as a timeless debugger, recording the entire state of execution. The biggest advantage is that this allows me to build a system that can run automated against a binary like the features of [MAYHEM](http://users.ece.cmu.edu/~sangkilc/papers/oakland12-cha.pdf) and **more importantly** as a teaching platform - which I am incredibly interested in. Finally I am convinced that [KLEE](http://klee.github.io) has features that should be integrated into a debugger, such as interactively marking a function as symbolic to then attempt to solve inputs for the path of execution. 

### Features in Development
> * Model Binary as a Graph
> * Extend LLDB with KLEE engine

### Interactive Graph Debugger

One of the biggest things I have been playing with is building a better frontend for a debugger, while tools like [Voltron](https://github.com/snare/voltron) are super helpful I want to solve CTF problems faster which requires more abstraction and quicker access to binary features. The result that I have come up with is the idea of an **Interactive Graph Debugger** where the graph represents both control flow and data flow (like [Joern](mlsec.org)) but the nodes are "clickable" UI-components that display state when enabled. 