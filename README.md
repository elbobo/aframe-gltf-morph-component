# aframe-gltf-morph-component
An a-frame component that allows you to target and control a gltf model's morphTargets created in Blender.

![alt text](https://github.com/elbobo/aframe-gltf-morph-component/blob/master/puffer.gif?raw=true "Gltf-morph in action")

# Basic usage

To simply target and effect a morph target, add the component as you would any other. Specific the name of the morph and the value that you want to set it to (0-1)

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
If there are multiple morphTargets in the model, they can be distinguished with double underscore (as with other components)

```html
   <a-entity 
    gltf-model="#puffer_model"
    gltf-morph__puff="morphtarget:Puffed up;value:1"
    gltf-morph__spike="morphtarget:Spikes out;value:1">
  </a-entity>
```
morphTargets can also be animated using the animation component (although in most cases it might make more sense to export the animations from Blender and trigger them using the animation-mixer component. (You need to add the morph target component you want to animate on to the entity before you can animate it).

```html
   <a-entity 
    gltf-model="#puffer_model"
    gltf-morph__puff="morphtarget:Puffed up;value:0"
    animation="property:gltf-morph__puff.value;from:0;to:0.75">
  </a-entity>
```
And of course you can target and/or set the `gltf-morph` with js as part of another component

```javascript
AFRAME.registerComponent('addamorph',{
  
  init: function(){
    
    this.el.setAttribute('gltf-morph', 'morphtarget:Puffed up;value:0.5')
    
  }
  
})
```

And using such an approach (or simply in HTML) you can see how you could for example, use the same model, but tweaking different morphTargets produce a variety of objects/characters. Example of a family of puffer fish generated from the same model below.




