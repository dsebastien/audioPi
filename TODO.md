# Tests
* Configure another Linux host as RTP client & update MPD config to push audio towards it
* Remuco

# Base OS config
* test removing 'audio' group membership
* set static ip
* Microphone recording: https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture#No_Microphone_Input

# audioPi basic config
* MPD clients review/tests
* MPD client: remuco / bluetooth
* MPD restore_paused "yes"
* MPD scrobbling
* Bluetooth setup and config
* Bluetooth pairing tests
* Bluetooth A2DP config and tests
* PulseAudio RTP config and tests
* PulseAudio RTP: http://www.freedesktop.org/wiki/Software/PulseAudio/Documentation/User/Modules/#index7h2
* PulseAudio RTP: http://www.freedesktop.org/wiki/Software/PulseAudio/Documentation/User/Network/RTP/
* PulseAudio RTP: http://blog.seventhmoon.info/blog/2012/12/23/pulseaudio-over-network/
* PulseAudio_ctl: keyboard volume control
* AudioEngine (MPD client) development
* if USB plugged in, mount (+ symbolic link?) under /media/music so that MPD can pick it up

# Open questions (will generate additional todos :p)
* Bluetooth - PulseAudio relationship
* Bluetooth - AudioEngine relationship
* AudioEngine: python, feature set? Act as MDP server wrapper, make it so that existing MPD clients can connect to it
* MPD - Bluetooth link?
* MDP - A2DP link?
* Voice recognition config + integration with AudioEngine / MPD
* Installation/Distribution of the project? OpenEmbedded? Super script that does it all for you? :)

# Bonus audio config
* PulseAudio: comment out: load-module module-suspend-on-idle (causes crackling between songs)
* PulseAudio: change resample-method, set to 'src-sinc-fastest' (the default one, speex-float-3 does not work on the pi with the adaptive resampling required to compensate for the clock drift between rtp stream and alsa device
* PulseAudio: set default-fragments = 10 
* PulseAudio: set default-fragment-size-msec = 10
* NTP server (Chrony?)
* MPD: auto_update_depth
* MPD: symlinks behavior
* MPD: zeroconf / network publication
* MPD: check mpd.git (more recent :p)
* MPD: check audio_output - mixer_type      "software"
* MPD HTTPD output
* MPD shoutcast streaming (or from PulseAudio?): http://mpd.wikia.com/wiki/Configuration
* check out pulseaudio_ctl: https://aur.archlinux.org/packages/pulseaudio_ctl/
* check out paxmier: https://aur.archlinux.org/packages.php?ID=52369
* Icecast: https://wiki.archlinux.org/index.php/Streaming_With_Icecast
* AirPlay: http://www.freedesktop.org/wiki/Software/PulseAudio/Documentation/User/Modules/#index8h2
* HQ resampling - test performances: https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture#High_quality_resampling
* Upmixing/Downmixing - test: https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture#Upmixing.2FDownmixing
* Find how to make hot-plugging USB sound card work: https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture#Using_a_USB_Headset_and_External_USB_Sound_Cards
* Text to speech: eSpeak

# Ideas
* LCD display (e.g., song metadata, lyrics, ...)
* Infinite intelligent queue (party shuffle, DJ mpde)
* MusicBrainz integration (acoustic id)
* Control device: like/dislike -> adapt ratings
* DLNA integration: AudioPi as DLNA renderer (gmrender-resurrect and/or MPD-UPNP), control by phone via DLNA controller (bubbleUPNP), LDC rendering using UPNP-Display Rpi project: LCDDisplay

# Python clients to check out
* Pymps
* Music-PLayer (Github -> albertz/music-player
* PyMServ
* PyTone
* PythonInMusic
* Exaile

# Python libs
* python-mpd2
* PulseAudio/ALSA
* BlueZ
