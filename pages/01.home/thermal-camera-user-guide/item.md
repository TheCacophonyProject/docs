---
title: 'Thermal Camera User Guide'
media_order: 'image1.png,image2.png,image3.png,image4.png,image5.png,image6.png,image7.png,image8.png,image9.png,image10.png'
published: false
---

# Confirming Camera Alignment

The "Cacophony Sidekick" app can be used on an Android phone or tablet to confirm the camera is functioning and correctly aligned. If you don't already have an Android device with Sidekick configured, please see [Appendix 1](#appendix) for installation instructions. To confirm camera alignment:

-   Ensure the hotspot is active on your Android device (see [Appendix 1](#appendix)).

-   Ensure the camera is powered on. If the camera is configured to only turn on at night it will turn itself off 20 minutes after being turned on during the day. If the camera might have turned itself off, disconnect and reconnect power to the camera,

-   Run the Cacophony Sidekick app.
-   Wait a few seconds for the camera's name to appear in Sidekick. Click the Refresh button if the camera has not been detected within a minute.
    > ![](image5.png?cropResize=400x400)
-   When the camera name appears, tap on the name.
-   The phone's web browser app will open and show the camera's management screen. Depending on the installed browser you may have to click an "Open Now" button in order to see the management screen.
-   Click on the menu button at the top right.
    > ![](image9.png?cropResize=400x400)
-   Click "Camera" on the menu that appears:
    > ![](image2.png?cropResize=400x400)
-   A live view from thermal camera should appear:
    > ![](image7.png?cropResize=400x400)
-   Adjust the camera's position as required using the live view as reference.
-   Use the Android back button (typically a left arrow icon at the bottom of the screen) to return to Sidekick.

# Collecting Recordings

Recordings created by Cacophony Project thermal cameras need to be uploaded to the Cacophony Project's API server for processing and storage. For cameras located in an area with mobile network coverage this will happen automatically. For devices that do not have mobile network coverage, the Sidekick app can be used to collect recordings from cameras in the field for later upload to the Cacophony Project's API server.

These instructions assume that Sidekick has already been installed and configured on an Android phone or tablet (see [Appendix 1](#appendix)).

## Collection

To collect recordings from one or more Cacophony Project thermal cameras:

-   Walk up to the camera.
-   Ensure the hotspot is active on your Android device (see [Appendix 1](#appendix).
-   If it's day time, it's likely that the camera will be asleep. Disconnect the power to the camera and reconnect it so that it wakes up - newer cameras will have a reset button which can be used instead. If you are also planning on changing battery packs, this is a good time to do so.
-   Run the Cacophony Sidekick app. It will start searching for nearby cameras.
-   The camera's name should appear within a minute (or less). The number of recordings available on the device will be indicated.
    > ![](image4.png?cropResize=400x400)
-   Tap the Download button to transfer recordings from the camera to the phone/tablet. As recordings are downloaded, the number of recordings on the device should count down. When the transfer is complete, "No recordings to download" will be indicated.
    > ![](image1.png?cropResize=400x400)
-   You may now leave the camera. If it is day time, and it has been configured to do so, the camera will turn itself off again.
-   If there are no more cameras to collect recordings from, exit the Sidekick app and turn off the Android device's WiFi hotspot.

## Uploading Recordings

Recordings collected by Sidekick can be uploaded to the API server once the phone or tablet has access to the internet. To do this:

-   Ensure the Android device's hotspot is **disabled**.
-   Ensure the Android device is connected to a WiFi network or has mobile network coverage.
-   Open the Sidekick app.
-   Click the Upload Recordings button.
-   The button will remain disabled ("greyed out") until uploads have completed.
-   Once uploads are done, exit the Sidekick app.

# Appendix 1: Sidekick App Installation <a id="appendix"></a>

Sidekick is an application which runs on an Android phone or tablet. It can connect to the Cacophony Project's thermal cameras in order to streamline installation, confirm correct operation and to collect recordings for otherwise offline devices.

## Installation & Setup

Sidekick is available on the Google Play Store. To install it open the Play Store app on the Android device and search for "sidekick cacophony". Sidekick should be the first listing. Alternatively, the app can be installed via [this link](https://play.google.com/store/apps/details?id=nz.org.cacophony.sidekick).

Once Sidekick is installed, start it up. The first it is run you will be asked to give Sidekick various permissions. Click "Allow" for each permission so that Sidekick can operate correctly.

![](image6.png?cropResize=400x400)
![](image3.png?cropResize=400x400)

A login screen will appear next. Enter your Cacophony Project username and password here, or if you don't have an account yet use the Register button to create yourself an account. If you're unsure what to do here, email [*support@cacophony.org.nz*](mailto:support@cacophony.org.nz).

![](image10.png?cropResize=400x400)

## Hotspot

Sidekick typically connects to Cacophony Project thermal cameras via a local WiFi connection. In order to set up your Android device for this, enter the Settings app and locate the Hotspot settings. Ensure the hotspot is configured with the following settings:

  | Hotspot Parameter | Value  |
  | --- | ---- |
  | Name | bushnet |
  | Security | WPA2 PSK |
  | Password | feathers |

**Important:** The hotspot needs to be activated whenever Sidekick needs to interact with Cacophony Project thermal cameras.
