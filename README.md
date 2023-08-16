# paliatweaks
A repo containing usefull Unreal Engine tweaks to improve Palia


Editing **Engine.ini** in "C:\Users\%UserName%\AppData\Local\Palia\Saved\Config\WindowsClient" will increase overall performance across all kinds of systems. 
It could resolve unexpected and unexplainable stutters.

```
[SystemSettings]
r.bForceCPUAccessToGPUSkinVerts=True
r.GTSyncType=0
r.OneFrameThreadLag=0
r.FinishCurrentFrame=0
r.TextureStreaming=1
r.Streaming.PoolSize=3072
r.Streaming.LimitPoolSizeToVRAM=1

[ConsoleVariables]
AllowAsyncRenderThreadUpdates=1
AllowAsyncRenderThreadUpdatesDuringGamethreadUpdates=1
AllowAsyncRenderThreadUpdatesEditor=1
```

# Options explained


**r.GTSyncType=0**

This only helps if the user has vsync enabled, disabling Vsync removes the need for messing with LowLatency mode entirely so users without vsync should set this to "0"

In all my games I limit the fps in the engine hence disable vsync ingame! 
In Palia this can be done trough editing GameUserSettings.ini by adding this vallue (Example for a 120hz screen with freesync enabled)

```
FrameRateLimit=117.000000
```

**r.OneFrameThreadLag=0**

Players with minimum requirements or an old system can enable this setting. That’s because it offers additional FPS at the cost of some input lag, this is not a competive game by any means so enabling this on older systems might help you out.

**r.Streaming.PoolSize=**

For r.Streaming.PoolSize, set the value based on the (GPU) videomemory.

```<8GB: 2048
8GB: 3072
10GB: 4096
12GB: 5120
>12GB: 6144
