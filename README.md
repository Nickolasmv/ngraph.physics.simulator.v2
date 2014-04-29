# Physics for ngraph

This is a physics module for [ngraph](https://github.com/anvaka/ngraph). Its primary focus is to serve force based graph layout, thus it manages a naïve system of bodies and springs. 

Simulator calculates forces acting on each body and then deduces their position via Newton's law. There are three major forces in the system:

1. Spring force keeps connected nodes together via [Hooke's law](http://en.wikipedia.org/wiki/Hooke's_law)
2. Each body repels each other via [Coulomb's law](http://en.wikipedia.org/wiki/Coulomb's_law)
3. To guarantee we get to "stable" layout system has kind of a drag force which slows entire simulation down.

Body forces are calculated in `n*lg(n)` time with help of Barnes-Hut algorithm implemented in [quadtree module](https://github.com/anvaka/ngraph.quadtreebh). [Euler method](http://en.wikipedia.org/wiki/Euler_method) is then used to solve ordinary differential equation of Newton's law and get position of bodies.

[![build status](https://secure.travis-ci.org/anvaka/ngraph.physics.simulator.png)](http://travis-ci.org/anvaka/ngraph.physics.simulator)

# install

With [npm](https://npmjs.org) do:

```
npm install ngraph.physics.simulator
```

# license

MIT
