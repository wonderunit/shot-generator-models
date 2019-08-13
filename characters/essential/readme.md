## 1. Create all of the LOD Models

1. Name main model something like `male-youth-LOD0`
2. Duplicate the main model `(Shift + D, Escape)`
3. Remove shape keys on the duplicate
4. Add a decimate modifier to the duplicate
  * with `symmetry`
5. Add shrinkwrap modifier
  * select the target of `LOD0`
6. Copy shrinkwrap 2 times
7. Rename each shrinkwap:
  * `Skinny`
  * `Muscular`
  * `Obese`
8. Duplicate 3 more times so you have 5 models and rename to:
  * `male-youth-LOD0`
  * `male-youth-LOD1`
  * `male-youth-LOD2`
  * `male-youth-LOD3`
  * `male-youth-LOD4`
9. Apply decimate modifier to each:
  * LOD0 - 13,000 polys (100%)
  * LOD1 - 6,000 polys (44%)
  * LOD2 - 2,000 polys 
  * LOD3 - 750 polys
  * LOD4 - 400 polys
10. And apply

## 2. Create the shape keys by shrink wrapping

1. Make sure LOD0 model has the shapekeys named:
  * Skinny
  * Muscular
  * Obese
2. LOOP: For each shape key (Skinny, Muscular, Obese):
  * Click LOD0: Shape keys
    * Turn all down to 0
    * Turn the correct shape key (Skinny, Muscular, Obese) up to 1.0
  * Click on LOD1-4: Modifiers
    * Apply correct Shrink Wrap modifier as Shape key
3. Repeat for each LOD1+ and Shape key

## OPTIONAL:
  
1. Correct UV map
