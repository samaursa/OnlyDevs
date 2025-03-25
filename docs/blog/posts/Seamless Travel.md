- Enable the option on the GameMode
- Pre 5.1, seamless travel wasn’t supported in single process PIE (play-in-editor). Therefore, you had to either turn off Run Under One Process setting, or start a standalone (right click your .uproject and Launch game), or launch a packaged build. Since 5.1, seamless travel is supported in single process PIE, **but you need to enable CVar `net.AllowPIESeamlessTravel` from console command as it’s disabled by default**.

This can be set in the `DefaultEngine.ini` as follow:

[SystemSettings]  
net.AllowPIESeamlessTravel=1

Don't forget to setup a transition level