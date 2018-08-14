# A Frame (Cheat-Sheet)

This is a helpful library of resources for Upperline students on their A-Frame adventures! This file is broken down into the following categories:

* Getting Started
* Documentation
* Common Objects/Tags
* Animations
* GBlocks
* Physics
* Helpful Hints/Common Problems

To reference any category, scroll or click the handle on the side of the header. For more info about A-Frame, see <https://aframe.io>.
For more about Upperline, see <https://upperlinecode.com>.

## Getting Started

A-Frame is a javascript Virtual Reality library built on top of [Three JS](https://threejs.org). It is very new, as the first official
release has not yet been completed (Most current version is 0.8.0). Before starting with A-Frame it is necessary to create a web scaffold
with the following layout (or equivalent):

```
MyWebsite
|
|--index.html
|--scripts
| |--AFrame.js
| |--script.js
|--images
  |--assets
```

Include the url to the A-Frame Library at the <b>Head</b> of your index.html file in the form of a script tag:

<tt><script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script></tt>

Include the A-Frame Extras Library underneath to add extensions:
<tt><script src="https://cdn.rawgit.com/donmccurdy/aframe-extras/v4.1.2/dist/aframe-extras.min.js"></script></tt>

Once the A-Frame Library is included, you may add more extensions <b>beneath it</b> still within the Head.

## Documentation

* General Documentation: <https://aframe.io/docs/0.8.0/introduction/>
* Animations: <https://aframe.io/docs/0.8.0/core/animations.html#sidebar>
* Adding event listeners: <https://aframe.io/docs/0.8.0/introduction/javascript-events-dom-apis.html#adding-an-event-listener-with-addeventlistener>
* Physics: <https://github.com/donmccurdy/aframe-physics-system>
* A-Frame Extras: <https://github.com/donmccurdy/aframe-extras>
* Frequently Asked Questions: <https://aframe.io/docs/0.7.0/introduction/faq.html>

## Templates

* General A-Frame Template: <https://github.com/upperlinecode/a-frame-primitives-template>
* Physics Template: <https://github.com/upperlinecode/a-frame-physics-template>
* Animations Template: <https://github.com/upperlinecode/aframe-animations-practice-template>

## Common Objects/Tags

* Most Common Primitives
	* `<a-box></a-box>`
	* `<a-sphere></a-sphere>`
	* `<a-sky></a-sky>`
	* `<a-plane></a-plane>`
	* `<a-cylinder></a-cylinder>`
	* `<a-torus></a-torus>`
* Entities
	* `<a-entity></a-entity>`
	* Essentially wrappers/divs for A-Frame components
	* Used to apply animations
	* Used for gblocks
* Attributes
	* position (provides position in x-y-z coordinates)
	* src (accesses source of custom skin)
	* color (changes color)
	* radius (changes size)
	* scale (scales size in x-y-z coordinates)
	* rotation (gives rotation specifics in x-y-z coordinates)
	* static-body (classifies entity as non-moving physics body)
	* dynamic-body (classifies entity as physics body subject to gravity and interactions with other physics bodies)
	* kinematic-body (classifies entity as moving physics body)
	
## Animations

* [Documentation](https://aframe.io/docs/0.8.0/core/animations.html#sidebar)
* include by inserting an `<a-animation></a-animation>` tag
* Attributes
	* attribute
		* rotation-rotates object (default)
		* position-moves object from one point to another
		* scale-makes objects bigger/smaller
	* from-starting value
	* to-ending value
	* easing-change in animation intensity

## Inserting gblocks

G-Blocks are pre-built, unique objects that you can insert into your A-Frame Scene! To access gblock libraries,
visit [Google Poly](https://poly.google.com) or [Clara.io](https://clara.io)

There are two ways to insert gblocks into your A-Frame scene:

1. ### Embedded URLs

  a. Visit Google Poly or Clara.io and find a gblock you enjoy
  b. Insert an entity with the following format: `<a-entity block="url"></a-entity>`, where the "url" is the
     url of the block in Google Poly/Clara.io

2. ### Downloading and Uploading
  
  a. Visit Google Poly or Clara.io and find a gblock you enjoy
  b. Download the gblock by clicking Download -> OBJ File
  c. Open the corresponding .zip folder and upload the .obj and .mtl files into your project directory
  d. Add two sets of `<a-asset-item>` tags with the following format: 
  
  ```
  <a-asset-item id="id" src="link_to_file.obj"></a-entity>
  <a-asset-item id="id" src="link_to_file.obj"></a-entity>
  ```
  
  e. Create an a-object-model with an 'src' and 'mtl' attributes that refer to the .obj and .mtl assets respectively

## DOM Manipulation

* All A-Frame entities are included in the DOM and can be accessed using <tt>document.querySelector()</tt>
* Event Handlers:
	* Collision-fires when two objects collide
	* Click-fires when an object is clicked (must include [cursor](https://aframe.io/docs/0.8.0/primitives/a-cursor.html#sidebar))
* Appending to the DOM-add elements to an empty a-entity using <tt>.innerHTML</tt>

## Helpful Hints

* <b>You may only append to empty entities in the DOM</b>
* Link all extensions and personal Javascript to the html underneath the A-Frame library
* Insert all attributes in the opening tag of any A-Frame Entity
* Access all DOM elements by using <tt>document.querySelector()</tt> before performing operations on them
* Access the A-Frame inspector by pressing cntrl + shift + alt + i (windows) or cmd + shift + i (mac)
* An entity must be classified as a physics body (ie. include the words static-body, dynamic-body, or kinematic-body in the
  opening tag) to use the 'collide' event handler
