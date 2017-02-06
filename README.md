# physics-module-ammonext
Physics module for Whitestorm.js [Beta]

![physics module](http://i.imgur.com/ZdMhDwb.png)

# Modules list

## `new PHYSICS.WorldModule()`

```javascript
const app = new WHS.App([
  // ...
  new PHYSICS.WorldModule({
    gravity: new THREE.Vector3(0, -10, 0)
  })
]);

app.start();
```

## `new PHYSICS.BoxModule()`

```javascript
const box = new WHS.Box({
  geometry: {
    width: 2,
    height: 2,
    depth: 4
  },
  
  modules: [
    new PHYSICS.BoxModule({
      mass: 10
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

box.addTo(app);
```

![](http://i.imgur.com/v7hzbeS.png)

## `new PHYSICS.SphereModule()`
```javascript
const sphere = new WHS.Box({
  geometry: {
    radius: 3
  },
  
  modules: [
    new PHYSICS.SphereModule({
      mass: 10
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

sphere.addTo(app);
```

![](http://i.imgur.com/GgqDeuX.png)
## `new PHYSICS.PlaneModule()`
```javascript
const plane = new WHS.Plane({
  geometry: {
    width: 100,
    height: 100
  },
  
  modules: [
    new PHYSICS.PlaneModule({
      mass: 5
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

plane.addTo(app);
```

## `new PHYSICS.CapsuleModule()`
No example yet.

## `new PHYSICS.ConeModule()`
```javascript
const sphere = new WHS.Cylinder({
  geometry: {
    radiusTop: 0,
    radiusBottom: 3,
    height: 4
  },
  
  modules: [
    new PHYSICS.ConeModule({
      mass: 2
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

box.addTo(app);
```
## `new PHYSICS.ConvexModule()`
```javascript
const teapot = new WHS.Model({
  geometry: {
    path: 'path/to/teapot.json'
  },
  
  modules: [
    new PHYSICS.ConvexModule({
      mass: 2,
      path: 'path/to/simplified/teapot.json'
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

teapot.addTo(app);
```
## `new PHYSICS.CylinderModule()`
```javascript
const sphere = new WHS.Cylinder({
  geometry: {
    radiusTop: 3,
    radiusBottom: 3,
    height: 4
  },
  
  modules: [
    new PHYSICS.CylinderModule({
      mass: 2
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

box.addTo(app);
```

![](http://i.imgur.com/WohSp97.png)
## `new PHYSICS.HeightfieldModule()`
```javascript
const terrain = new WHS.Parametric({
  geometry: {
    func: myFunction
  },
  
  modules: [
    new PHYSICS.HeightfieldModule({
      mass: 5,
      size: new THREE.Vector2(100, 100),
      autoAlign: true // center physics object automatically.
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

terrain.addTo(app);
```

![](http://i.imgur.com/h6Z8IIq.png)

## `new PHYSICS.CompoundModule()`
This module should be used only if you want to create a copmound physics object without shape and then add needed objects. `CompoundModule` is selected by default if you add object to another object.

## `new PHYSICS.ConcaveModule()`
```javascript
const teapot = new WHS.Model({
  geometry: {
    path: 'path/to/teapot.json'
  },
  
  modules: [
    new PHYSICS.ConcaveModule({
      mass: 2,
      path: 'path/to/simplified/teapot.json'
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

teapot.addTo(app);
```

![](http://i.imgur.com/aoJ7fgv.jpg)
## `new PHYSICS.SoftbodyModule()`
```javascript
const sphere = new WHS.Icosahedron({
  geometry: {
    radius: 3,
    detial: 2
  },
  
  modules: [
    new PHYSICS.SoftbodyModule({
      mass: 5,
      pressure: 500
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

sphere.addTo(app);
```
## `new PHYSICS.ClothModule()`

> Used only with `WHS.Plane`

```javascript
const cloth = new WHS.Plane({
  geometry: {
    width: 100,
    height: 50
  },
  
  modules: [
    new PHYSICS.ClothModule({
      mass: 5
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

cloth.addTo(app);
```

## `new PHYSICS.RopeModule()`

```javascript
const rope = new WHS.Line({
  geometry: {
    curve: new THREE.LineCurve3(new THREE.Vector3(0, 10, 0), new THREE.Vector3(0, 20, 0))
  },
  
  modules: [
    new PHYSICS.RopeModule({
      mass: 5
    })
  ],
  
  material: new THREE.MeshBasicMaterial({color: 0xff0000})
});

rope.addTo(app);
```
