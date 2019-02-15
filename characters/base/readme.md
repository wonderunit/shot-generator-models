# Exporting

There is a bug in the GLTF exporter for blender. Therefore, to export the models, you first have to export the FBX, and then use another utility to convert the FBX file to GLTF.

## 1. Export to FBX

Export FBX..

Main > Apply Scale: "FBX ALL"
Armature > "DESELECT" Add Leaf Bones

## 2. Convert FBX to GLTF

https://github.com/facebookincubator/FBX2glTF/releases

```
./FBX2glTF-darwin-x64 -b --blend-shape-normals --blend-shape-tangents --pbr-metallic-roughness -i shot-generator-models/characters/base/male-adult/male-adult.fbx -o shot-generator-models/characters/base/male-adult/adult-male
./FBX2glTF-darwin-x64 -b --blend-shape-normals --blend-shape-tangents --pbr-metallic-roughness -i shot-generator-models/characters/base/male-youth/male-youth.fbx -o shot-generator-models/characters/base/male-youth/teen-male
./FBX2glTF-darwin-x64 -b --blend-shape-normals --blend-shape-tangents --pbr-metallic-roughness -i shot-generator-models/characters/base/female-adult/female-adult.fbx -o shot-generator-models/characters/base/female-adult/adult-female
./FBX2glTF-darwin-x64 -b --blend-shape-normals --blend-shape-tangents --pbr-metallic-roughness -i shot-generator-models/characters/base/female-youth/female-youth.fbx -o shot-generator-models/characters/base/female-youth/teen-female
```
