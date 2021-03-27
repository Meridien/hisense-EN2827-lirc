# hisense-EN2827-lirc
Configuration file for lircd

LIRC raw commands for Hisense EN2827 Television Remote

_Build Info_

| Parameter | Value |
| ------ | ------ |
| Date | 27 MAR 2021 |
| Hardware | Raspberry Pi 2B with Anavi IR Phat |
| Software | Raspbian GNU/Linux 9 (stretch) / Debian 9.13, LIRC, using mode2 command |



## Commands

```sh
power
ok
up
down
left
right
play
pause
mute
netflix
youtube
home
input
```

## Usage

Copy the file into the lirc configuration directory on your system. 

_E.g. for Debian:_

```sh
/etc/lirc/lircd.conf.d/
```

```sh
sudo cp hisense-EN2827-lircd.conf /etc/lirc/lircd.conf.d/hisense-EN2827-lircd.conf
```

Then restart lircd

```sh
sudo systemctl restart lircd
```

Then check lircd status - you should expect no errors

```sh
sudo systemctl status lircd
```

Then point the IR LEDs at the tv's receiver, and execute the commands like this:

```
irsend SEND_ONCE hisensetv power
irsend SEND_ONCE hisensetv netflix
irsend SEND_ONCE hisensetv ok
irsend SEND_ONCE hisensetv down
irsend SEND_ONCE hisensetv play
```


