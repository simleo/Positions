**example_4.hdf5**

contains 31 (2D phase contrast) trajectories of 30 frames duration, 

the hdf5 file is organized as follow: 

* Summary
    * frames
    * marks

* tracks
    * track0000
        * center
        * halo
        * soma
    * track0001
        * center
        * halo
        * soma
    * track0002
        * center
        * halo
        * soma
...

if No is the number of objets and Nf the number of frames

*frames* gives the validity window for each object Nox3 array : # of valid frames,first valid frame,last valid frame

*marks* gives the marker position for each tracked object Nox3 array : x,y,#frame (a marker can be put on any frame)

each track is described by 

*center* position of the object (Nfx2) float array : x,y

(cells are described using 8 triangles for the halo and 8 triangles for the soma)

*halo* shape of the halo the cell Nfx8x8 array 

- first dimension is the frame number,
 
- second dimension is the triangle id number (0-7),
 
- last dimension is the feature: 
    - xg,yg: triangle centroid
    - surf: triangle surface
    - surfalpha: triangle weighted surface
    - totalvalue: triangle total weight
    - vmax,vmin,vmean : min, max and mean gray value on the triangle

