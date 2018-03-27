# Spatiotemporal Navigation (client)

Originally developed for the "_Extended Video Streams for Spatiotemporal Navigation_" demo presented at The Graphical Web 2016 and extended for the "_Streaming And Presentation Architectures For Extended Video Streams_" [short paper](https://www.researchgate.net/publication/317593679_Streaming_and_Presentation_Architectures_for_Extended_Video_Streams), presented at ACM TVX '17.

This version of the client supports navigating through space and time in a selection of videos. The sister project of Spatiotemporal Navigation is [SWAPUGC](https://github.com/emmanouil/SWAPUGC), which permits watching an event via different UGC video streams (with spatiotemporal information). A demo of SWAPUGC is available [here](https://emmanouil.github.io/SWAPUGC/)

### Input:
A `playlist.txt` located in a top-level subfolder named `parsing` with names of files.

For each _NAMEOFFILE_ there should exist (in the same folder as `playlist.txt`) a:

1. `VID_NAMEOFFILE.mp4` video file
2. `OUT_NAMEOFFILE.txt` data file (output of the parser), that contains an array of JSON Object [like this](#location-and-sensor-pairs)

=====

### Data In Use
#### Global Pairs Holder
global variable name: ```globalSetIndex```
decription: an Array of recordings - the Location/Sensor Pair Objects of each recording are stored in the ```set``` field)
```JSON
    {
        id: "1234567_12345"
        index: 0
        set: Array[12]
        textFile: "OUT_1234567_12345.txt"
        textFileURL: "http://137.194.232.162:8080/parsing/OUT_1234567_12345.txt"
        videoFile: "OUT_1234567_12345.mp4"
    }
```


#### Location and Sensor Pairs
decription: An Object holding Orientation and Location information for a POI
```JSON
    {
        "id": 1,
        "Sensor": {
            "Y": -0.083974324,
            "LocalTimestamp": 1466187515309,
            "Type": "ORIENTATION",
            "X": 2.5136049,
            "Z": -1.4016464
        },
        "Location": {
            "Time": 1466187920000,
            "LocalNanostamp": 27814219216825,
            "Longitude": 2.3506619881858737,
            "Latitude": 48.83000039044928,
            "Altitude": 111.77508694140864,
            "Bearing": 213.30880737304688,
            "Provider": "gps",
            "Accuracy": 16,
            "LocalTimestamp": 1466187515321,
            "Velocity": 1.0693713426589966
        }
    }
```
