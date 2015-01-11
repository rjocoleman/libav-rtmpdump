# libav + rtmpdump for Heroku buildpacks

Created with https://github.com/hone/hammer

Specify libav version e.g ` hammer build --env VERSION:11.1`

Can be used with: https://github.com/peterkeen/heroku-buildpack-vendorbinaries

Provides `avconv` and `rtmpdump` binaries.


### Cedar-14

I need [Cedar 14](https://github.com/progrium/cedarish). Anvil currently is using Cedar. Can make a new Heroku app on cedar-14 and compile.

```
$ heroku run bash
~ $ git clone git://git.ffmpeg.org/rtmpdump
~ $ cd rtmpdump
~/rtmpdump $ output_dir=/tmp/rtmpdump
~/rtmpdump $ mkdir -p $output_dir
~/rtmpdump $ make SYS=posix prefix=$output_dir
~/rtmpdump $ cd $output_dir
/tmp/rtmpdump $ tar zcvf ./rtmpdump-bin.tgz .
/tmp/rtmpdump $ scp rtmpdump-bin.tgz user@some-scp-server:
/tmp/rtmpdump $ exit
```
