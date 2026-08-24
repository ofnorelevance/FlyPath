# Ground Aware feature (alpha) notes:

### TODO / To think about

- Height changes are not following terrain, they are following the terrain at waypoints. This can be problematic if there are acute height changes between waypoint, like surveying a mountain but all the waypoint are at the edges, thus the low parts of the survey.
- Similarly a large depression with only turn waypoints selected will not follow the lower height required to maintain GSD.
- More importantly, if we have dense waypoints in a line that crosses a sharp drop or climb, there's a real chance if the drop starts early or the climb starts late the drone might crash into the terrain.
- I'm guessing none of this is important for enterprise level drones, as those I believe have the option to take the height from a waypoint mission as constant or AGL.
- The consumer class I believe always does a fixed height from the launch position, and as such we need a way to state where in the terrain we will be launching each mission, so the selected mission height can be calculated relative to that.

- dtm raster is assumed to have exactly one band with height values, needs to be documented or allowed to change.
- waypoints have gl now, next is export to kmz