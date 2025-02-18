- SciencePixelBinning 
  1. requires that science view geometry is defined in native pixel space
  2. hard coded to use linear radial spacing
  3. SLOW! and uses a ton of memory
  
- Solutions:
  1. this can be solved by deriving SPB inside ScienceGeom
  ``` python
  # current
  ScienceGeom(spacecraft, science_pixel_binning)
  # desired (inside sc2scivg())
  ScienceGeom((50, 100), sc.position_gse, fov=sc.sensor.spec.fov, rspacing='lin', rlim=(3, 25))
  ScienceGeom((50, 100), sc.position_gse, fov=sc.sensor.spec.fov, rspacing=[1.2, 3.5, ...])
  ```
  2. solved by SciencePixelBinning2
