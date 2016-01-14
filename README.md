![behaim logo](logo.png)

# Behaim

Behaim uses Java reflection to explore an domain model up to a configurable recursion depth. The resulting meta data
can then be used by pluggable visitors. 

As a proof of concept, Behaim currently comes with a builder visitor that allows for the creation of randomly populated 
object graphs which may be useful for performance tests.

# Features
- Multi-threaded graph exploration
- Re-use of meta data about an already explored object graph
- Extensible with custom visitors. Already comes with a visitor to create a randomly populated object graph.

# Requirements
- Java 5 or above
- Maven 2.2.1 or above

# Builder Usage

## Default configuration
```
Foo foo = Builder.make(Foo.class);
Collection<Foo> foos = Builder.make(Foo.class, 100);
```

## Custom configuration
```
Config config = new Config(...);
Foo foo = Builder.make(Foo.class, config);
Collection<Foo> foos = Builder.make(Foo.class, config, 100);
```

## Repeated builds
When you need to repeatedly create objects with the same configuration, use the instance make method.
```
Builder builder = new Builder(Foo.class);
Collection<Foo> foos1 = builder.make(100);
Collection<Foo> foos2 = builder.make(50);
```

# FAQ

What does Behaim mean?
Martin Behaim (1459 – 1507) was a German cosmographer, astronomer, geographer and explorer. His [Erdapfel](https://en.wikipedia.org/wiki/Erdapfel) 
from 1492 is considered to be the oldest surviving terrestrial globe.
