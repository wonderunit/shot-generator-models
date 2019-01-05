# Shot Generator Models

Shot Generator is a feature within Storyboarder to easily set up shots using 3D characters, objects, lights, and cameras.

Shot Generator uses 3D models as characters. This repository is the open source of those models as canonical Blender .blend files, and the exports used in shot generator: fbx, gltf, obj, etc.

## Characters

The objective of Shot Generator is to keep the setup of a shot extremely simple. Therefore, the characters are designed with the silhouette of the character in mind - a shape that upon quick glance, you can tell:
  * Gender
  * Age
  * Body type
  * Height
  * Pose

### The Models

Female and Male bone proportions and body shape are different so they needed to be their own models. Additionally, adult and youth bone proportions and body shape are different so they needed to be their own models. [ Male, Female ] x [ Adult, Youth] = 4 models.

We accomplished this by creating 4 main models: 
  * Female - Adult
  * Female - Youth
  * Male - Adult
  * Male - Youth

### Morph targets (Blend Shapes)

Body type is accomplished through morph targets. Morph targets or Blend Shapes are modifications to existing geometry. They have the same exact vertices, they are just in different locations. So you can easily mix/blend between 1 or more morph targets to get interesting model shapes. We decided on 4 prototypical body shapes: 
  * Mesomorph (Medium Build) [default]
  * Ectomorph (Skinny)
  * Muscular
  * Obese

By blending a combination, you can make many body shapes: 
  * Extremely skinny (Ectomorph: 1.0)
  * Skinny athletic person (Ectomorph: 0.7, Muscular: 0.4)
  * Stocky person (Obese: 0.5, Muscular: 0.5)

### Armature (Skeleton Structure)

The mesh of the model is rigged/skinned mostly by Mixamo's online tool. We use their standard 65 bone Standard Skeleton, which includes individual fingers. The bone names are named like: mixamorig:LeftUpLeg

<img src="https://user-images.githubusercontent.com/441117/50726908-49999a00-10e1-11e9-8bbc-71aefa5df0ac.png" width="300">

### Scale (Height)

1 3D Unit = 1 Meter = 3.28084 Feet = 1.09361 Yards (OMFG WTF IS A YARD AND WHY WE NEED IT WTFFFF)

Even though a 3D unit is arbitrary, the world has loosely agreed that this is the preferred conversion. 

Shot Generator automatically scales the models to normalize them. However the scales for the standard model heights are:
  * Male - Adult: 1.8 (5'11")
  * Female - Adult: 1.625 (5'4")
  * Female - Youth: 1.6 (5'3")
  * Male - Youth: 1.6 (5'3")

Height is controlled by scaling the armature/skeleton to the appropriate height. The only exception is that the head bone does not scale. As people are taller and shorter, their heads are roughly the same size. It is true that skulls vary in size. The scale of the head can be overridden. 

### Pose

Posing is done in the engine. This is by rotating bones, and saving a preset of all the bone rotations. There are no limitations on how you can rotate bones. Go crazy.

### UV / Texture

There is one material and one texture. It's adjacent to the model in the textures folder.

## Custom Character Models

The main reason why we are releasing these models open source is so people can make their own models or customize the existing models.

Making a new model should be fairly simple.

What you don't need: 
  * You don't even need a rigged skeleton. (It will work without - of course you can't pose it)
  * You don't need a standard skeleton. (You can pose any bones. So you could have a rigged dog.)
  * You don't need blend shapes / morph targets.
  * You can have any blend shapes you want (It will load them in dynamically)

What you need:
  * A model with a mesh
  * A single material with a single texture

So some custom examples:
  * A character downloaded off the internet with no rig and you don't need to pose it
  * A dog
  * A snake
  * A monster
  * A person with very specific morph targets
  * A very specific model with lots of detail
  * A model based on one of these models you slightly edited

----

## Thoughts on Format - Blender

Currently, most professional modelers tend to use Max or Maya. Max and Maya are expensive. Blender is free.

I've been following Blender for tens of years. Blender is 23 years old. I last checked in on Blender a few years ago. It sucked. Shit didn't even have undo. I wanted to use it. I wanted to like it. But it was always, you know, shitty.

Fast forward, Blender is excellent. It got better over time, and it's gotten so good, you can't ignore it. There's a new version 2.8, and honestly, it's awesome. It seems like they actually have a really great singular product visionary over there which is the problem with most open source software.

I learned Blender over a weekend of watching Youtube tutorials. 

It's easy to learn, capable (and in many cases better than paid software), and free. So we are standardizing the canonical models with it.

