# Simple Baby Monitor

This is a simple baby monitor, based on [this script](https://bitbucket.org/mjs0/peak-detect) and using the [Instapush](https://instapush.im/) API for notifications.

This script is designed to run on a Raspberry Pi with an attached USB microphone. When the audio level on the microphone reaches a certain peak, the script sends a notification via Instapush.

# Usage

1. Install Instapush pip package:
`pip install instapush`
2. Sign up for an account on Instapush.
3. Create an application within Instapush, and add the appid and secret to the script in the APPID and SECRET variables.
4. Find your PulseAudio sink name for your external microphone:
`pacmd list-sources | grep -e device.string -e 'name:'`
5. Add this value as the SINK_NAME variable
6. Change the THRESHOLD variable to account for background noise, etc. (optional)
7. Change the EVENT_NAME and TRACKERS variables to match the settings in your Instapush application.
8. Change the WAIT_TIME variable to set the minimum time between notifications, in seconds (optional)
9. Run the script:
`python baby-monitor.py`
