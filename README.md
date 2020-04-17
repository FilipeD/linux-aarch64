# linux-aarch64
Simple repo to share my recently built packages for either binaries or python wheels :)

A simple testdrive of a few linux distros on my 4GB Ram Android phone in order to test x forwarding without the hassle of installing virtualization lead to an interesting discovery: stability.

Having found it could be setup for usb-tethering by default, life became much more fun in a time when we all should #StayAtHome.
Soooo... What am I really going to do with a linux distro on a phone? My thoughts ran wild...

<h4> I - UserLAnd - Debian Buster</h4>

<h5>Will it code?</h5>
  - code-oss ./
Works!!! :D

<h5>Will it build?</h5>
  - Yes!!!! gcc 8.3.0 
  - Maybe clang-7/llvm-7: ran into some issues... :(
  - ispc - I built this one as well but can't really tell if it's working properly... Sorry...

<h5>Will it (machine-)learn?</h5>
Guess what? It might! I had to install something to figure out where some errors were coming from: the available boost_python1.67 was being pointed to by the linker, complaining about missing symbols. Needless to say, endless hours later, I found out (see [1] and [2] below) it isn't being linked with any particular python library, hence the issues.
In the meantime, I had tried to install dlib without even thinking if a wheel was available... It was not but, after an already long week trying to build something else I didn't really care...
It built dlib for python3.7!!! 8-D
And it went as far as it could with the tutorial at [2]. It wouldn't accept numpy's array though.
It did cross my mind to build opencv (and I might very well leave it building overnight ;-) )

So maybe it allows for some fun with the nearly 2GB ram (of 3.67 reported as available)...



<h4>II - Getting wilder - The 3D sort of wild ;-)</h4>

<h5>Will it "Blend"????!!!! XD XD XD</h5>
Now this came as of a surprise but, know what? Give up audio and Blender... Starts!
  - Wired mode viewports work
  - solid and textured, "don't" - gl issues but, come on... it needs OpenGL 2.x (this thing supports OpenGL-ES only...)  
  - Cycles (kind of) works! Yessss!!! Do you see where I'm going with this? Do you? :D

At this point, a full 13hrs of a steady putty based X forwarded session, I can say that I nearly
forgot I was working via ssh. Then it all vanished! X( - the phone simple rebooted. No noticeable
heat, the experience was "ok" (for a walk into uncharted territory, anyway), no stuttering... What
could possibly have happened? So far I haven't found.
By the way, the phone is stock, no root involved (hence the coice of UserLAnd).


Now, let's see: 4 x A73 + 4 x A53 = "eight core" coupled with 4GB Ram on a near 200€ smartphone... 
"That can't possibly work...". Can it? Let's find out, gotta #StayAtHome, right? :>


<h4>III - :D Let's shed some "lux" on this, shall we? <h4>
  
luxcorerender? Hmmm, sources downloaded... Did you know "sdcard" gets mounted to /host-rootfs/sdcard B-D ?

(Many, many, many, many, Many, many, many, many Many, many, many, many, Many, many, many, many hours later)

Well, it's 1h25am and I'll have to start working in 8hrs so, before I can write properly about it, I'll have
to bid you all good night for now. The good news and the reason I finally decided on making some good use
of github's space are:

- I managed to get luxcoreui to build and RUN!!! I can't get tired of watching it on a window of it's own
on my vcXsrv server. 
- I had to disable Intel's Open Image Denoiser (It almost made me give up) :( Do you still see the "many,
many, many(...)" line above? It's a veeeery loooong story.

See you all very soon. It's Friday!!! It's gonna be an interesting weekend! 

ps: I know, this md needs some love... It'll be dealt with in a near future, I promise... :)

<h4>Usefull links:</h4>
  1 https://stackoverflow.com/questions/46934760/importerror-libboost-python-so-1-65-1-cannot-open-shared-object-file-no-such
  2 https://bugzilla.redhat.com/show_bug.cgi?id=1302120
