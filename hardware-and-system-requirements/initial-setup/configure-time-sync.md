# Configure time sync

#### Configure time sync

Here, you must make sure your server time matches the wall clock.

For Ubuntu 20.04

* Run the following command: `timedatectl`
* Check if NTP Service is active.
* Check if Local time, Time zone, and Universal time are all correct.
* If NTP Service is not active, run: `sudo timedatectl set-ntp on`
* If you see error message Failed to set ntp: NTP not supported, you may need to install chrony or ntp package.
* Note: by default, VMs may disable NTP so you may need to find a work-around for your environment.



{% hint style="info" %}
The RTC (Real-Time Clock) time may be set to your local timezone instead of UTC, especially in a VM which has its clock configured on Windows.
{% endhint %}
