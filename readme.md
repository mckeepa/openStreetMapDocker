## Create Server
``` 
docker run -v C:\dev\github\openStreetMapDocker\map-data\australia-latest.osm.pbf:/data.osm.pbf -v openstreetmap-data:/var/lib/postgresql/12/main overv/openstreetmap-tile-server import
```

## Apply automtuc updates
```
docker run -e UPDATES=enabled -v C:\dev\github\openStreetMapDocker\map-data\australia-latest.osm.pbf:/data.osm.pbf -v C:\dev\github\openStreetMapDocker\map-data\australia.poly:/data.poly -v openstreetmap-data:/var/lib/postgresql/12/main overv/openstreetmap-tile-server import
```

## start 

```
docker run -p 8080:80 -v openstreetmap-data:/var/lib/postgresql/12/main -d overv/openstreetmap-tile-server run
```
# For GeoCoding

use - https://github.com/mediagis/nominatim-docker/tree/master/3.7


```
docker run -it --rm \
  -e PBF_URL=https://download.geofabrik.de/australia-oceania/australia-latest.osm.pbf \
  -e REPLICATION_URL=http://download.geofabrik.de/australia-oceania/australia-updates/ \
  -p 8080:8080 \
  --name nominatim \
  mediagis/nominatim:3.7

```
