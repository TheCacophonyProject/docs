---
title: 'Thermal video processing'
taxonomy:
    category:
        - 'Developer'
---

## In the field

* A thermal camera in the fields spots something a moving warm 'animal'. 
* The thermal camera records the 'animal' until it 'stops seeing movement'.   The raw data from our lepton3 camera for this time is then saved into our custom *.CPTV format. 
* The date-stamped file is then uploaded through the internet or by using side kick to our API server. 

## On the API server

* Once a CPTV file makes it into our cloud one of our thermal video processors will pick up the file and process it.  (
* First the processor will extract the metadata from the CPTV.
* Then it will run the video through our machine learning model.   This works in three stages:
  1. Possible animals called tracks are extracted from the video
  2. The tracks are feed into our machine learning model
  3. A MP4 videos is produced so we humans can view it.
* The processor takes the results and decides what tags to identify the track/video with.
* The processor uploads the track definitions and MP4 to the api server. 

## Setting up a test server on your machine

To try this yourself you first need to download the four projects involved:

* [cacophony-api](https://github.com/TheCacophonyProject/cacophony-api)
* [cacophony-processing](TheCacophonyProject/cacophony-processing)
* [classifier-pipeline](https://github.com/TheCacophonyProject/classifier-pipeline)

Then:

1.  Run the cacophony-api using the ./run command
2.  Set up the paths to the classifier-pipeline and virtural env in your cacophony-processing yaml 
3.  Run cacophony-processing: `python thermal-processing.py`
4.  Upload a CPTV file to the api server.  (Any easy way to to this is to run `test\pytest test_thermal_device.py` in the cacophony-api project)
5.  Wait for the cacophony-processing process to poll for the file and process it.

