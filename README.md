# val3dity 

Validation of 3D primitives according to the international standard ISO19107.
Think of it as [PostGIS ST_IsValid](http://postgis.net/docs/ST_IsValid.html), but for 3D primitives (PostGIS is only for 2D ones).

It allows us to validate a 3D primitive, ie to verify whether it respects the definition as given in [ISO19107](http://www.iso.org/iso/catalogue_detail.htm?csnumber=26012) and GML/CityGML.
All the 3D primitives of GML are supported:

  - `<gml:MultiSurface>`
  - `<gml:CompositeSurface>` 
  - `<gml:Solid>`
  - `<gml:MultiSolid>`
  - `<gml:CompositeSolid>`

However, as is the case for CityGML, only planar and linear primitives are allowed: no curves or spheres or other parametrically-modelled primitives are supported (and there is no plan to do so!).

val3dity accepts as input:

  - [CityGML](https://www.citygml.org)) 
  - [CityJSON](http://www.cityjson.org))
  - any [GML files](https://en.wikipedia.org/wiki/Geography_Markup_Language) 
  - [OBJ](https://en.wikipedia.org/wiki/Wavefront_.obj_file), 
  - [OFF](https://en.wikipedia.org/wiki/OFF_(file_format))
  - [POLY](http://wias-berlin.de/software/tetgen/1.5/doc/manual/manual006.html#ff_poly).


## How do I compile and use val3dity?

It is a command-line program, which we provide as source code, with CMake.
It's trivial to compile under Mac and Linux.
[For Windows, we do offer an executable](https://github.com/tudelft3d/val3dity/releases).

To compile val3dity yourself, you first need to install the following free libraries:

  1. [CGAL](http://www.cgal.org)
  1. [GEOS](http://trac.osgeo.org/geos/) 
  1. [CMake](http://www.cmake.org)

Under Mac we suggest using [Homebrew](http://brew.sh/):

    $ brew install cmake 
    $ brew install cgal
    $ brew install geos

Afterwards run:

    $ mkdir build
    $ cd build
    $ cmake ..
    $ make
    $ ./val3dity ../data/cityjson/cube.json
    
## Documentation and help

The documentation is available at [http://val3dity.rtfd.io](http://val3dity.rtfd.io)