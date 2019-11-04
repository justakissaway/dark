[![](media/project_dark_home.png)](documentation.md)

# spatial security

This documentation concerns securing a room or tangible property.

# sentinel

This system is designed to run on Ubuntu and sends alerts via Matrix if motion is detected using its reliable motion detection algorithm.

- <https://github.com/wdbm/sentinel>

# Haven

- <https://www.youtube.com/watch?v=Fr0wEsISRUw>
- <https://www.theverge.com/2017/12/23/16812834/edward-snowden-haven-guardian-project-laptop-phone>

## setup

- [F-Droid](https://f-droid.org)
- [Google Play](https://play.google.com/store/apps/details?id=org.havenapp.main)
- [GitHub APK](https://github.com/guardianproject/haven/releases)

Haven walks users through configuring the sensors of the host device to best detect intrusions into their environment. The application's main view allows the user to select which sensors to use along with their corresponding levels of sensitivity. A security code must be provided, which is used to disable monitoring and a phone number can be set to which a message will be sent if any of the sensors are triggered.

Notifications can be sent through SMS or Signal (via the Signal API). Event logs and captured media can be accessed remotely through Tor. Haven must be configured as an Onion Service and requires the device to have Orbot set up.
