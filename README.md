# a-mp3-player-based-on-mini2440
Smart speakers are mainly made by imitating Xiaomi's Xiaoai speakers. The project adopts C/S architecture and is divided into three
part, speaker part, background Aliyun server and APP.

The speaker part is based on the mini2440 development board, transplanted with the Linux operating system, including u-boot, internal
kernel and root filesystem. The application layer uses the open source library madplay as an audio codec tool, using parent,
Three processes of children and grandchildren are used to control the playback of music. Functions such as cutting songs, adjusting volume, and pausing can be realized by pressing the buttons.

The background Aliyun server is a public network server, using C++ language, which can realize APP data
Forward. Because the server has to handle multiple clients at the same time, I chose to use an open source high concurrency framework
libevent to achieve. The server also adds the function of linked list to record the binding relationship between APP and speakers.

The APP is implemented with Qt, and is mainly responsible for sending control commands to the server, including song switching, volume adjustment,
Playback modes, timer playback, voice control, and more.
