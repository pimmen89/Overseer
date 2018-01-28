# Overseer


[![Overseer](http://images.ctrustnetwork.com/static_pages/gaming/starcraft/unit_images_white/starcraft.2.overseer.png)](#features)

Header only library for analyzing Starcraft 2 maps by region decomposition. Based on the [Brood War Easy Map architecture](http://bwem.sourceforge.net/) created by Igor Dimitrijevic. It uses the MIT license.

## Getting started

Overseer is header only, you just need to include the folder anywhere in your source folder to use it.
Include the file `MapImpl.h` into your project to get started.

`#include "Overseer/MapImpl.h"`

You need to pass a pointer to your Agent to the map to have it fully configured. Then you need to call `Intialize()` to construct the map.
Now you're good to go! This is how it would look on Interloper LE

```c++
{
	Overseer::MapImpl map;

	map.setBot(&bot); //Pass a pointer to your sc2::Agent
	map.Initialize(); //Intialize the map

	std::cout << "Number of tiles on map: " << map.size() << std::endl;
	std::cout << "Number of regions: " << map.getRegions().size() << std::endl;
}
```

Example output:

```
Number of tiles on map: 26752
Number of regions: 18
```

If you want the number of `ChokePoint` you have to check for each region pair since a pair of regions could have multiple `ChokePoint`
## Project status

Overseer is currently under construction. Feel free to make a pull request!

## License

The license can be found [here.](https://github.com/pimmen89/Overseer/blob/master/LICENSE.md)
