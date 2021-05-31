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
