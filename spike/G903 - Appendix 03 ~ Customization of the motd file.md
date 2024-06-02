# G903 - Appendix 03 ~ Customization of the motd file

Every time you open a new shell terminal, no matter if remotely or locally, you see a bunch of lines over the starting prompt. In Debian, those lines are stored in the `/etc/motd` file and can be modified or completely replaced by any other text.

Just make a backup of that file (as a `.original` version) before editing it, and then modify in any way you want.

~~~bash
$ cd /etc
$ sudo cp motd motd.original
$ sudo vim motd
~~~

> **BEWARE!**  
> In the `sshd` configuration there's a `PrintMotd` set to `no`. **Don't change it** to `yes` or you'll see the `motd` content printed **twice**.

## References

- [Debian wiki. `motd`](https://wiki.debian.org/motd).
- [Customize your MOTD login message in Debian and Ubuntu](https://ownyourbits.com/2017/04/05/customize-your-motd-login-message-in-debian-and-ubuntu/).
- [Debian Buster Dynamic MOTD](https://oitibs.com/debian-buster-dynamic-motd/).
- [Create a Custom MOTD or Login Banner in Linux](https://www.putorius.net/custom-motd-login-screen-linux.html).
- [ASCII generator](http://www.network-science.de/ascii/)

## Navigation

[<< Previous (**G902. Appendix 02**)](G902%20-%20Appendix%2002%20~%20Vim%20vimrc%20configuration.md) | [+Table Of Contents+](G000%20-%20Table%20Of%20Contents.md) | [Next (**G904. Appendix 04**) >>](G904%20-%20Appendix%2004%20~%20Object%20by%20object%20Kubernetes%20deployments.md)
