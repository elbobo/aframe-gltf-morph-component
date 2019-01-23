# aframe-gltf-morph-component
An a-frame component that allows you to target and control a gltf model's morphTargets

![alt text](https://github.com/elbobo/aframe-gltf-morph-component/blob/master/puffer.gif?raw=true "Gltf-morph in action")

# Basic usage

```html
  <head>
    <script src="https://aframe.io/releases/0.8.2/aframe.min.js"></script>
    <script src="puturlhere.js"></script>
  </head>
  <body>
    <a-scene>
       <a-assets>
          <a-asset-item 
              id="puffer_model" 
              src="path/to/yourmodel.glb">
          </a-asset-item>
       </a-assets>
       <a-entity 
        gltf-model="#puffer_model"
        gltf-morph="morphtarget:Puffed up;value:1">
      </a-entity>
    </a-scene>
  </body>
```

