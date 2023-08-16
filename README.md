# paliatweaks
A repo containing usefull Unreal Engine tweaks to improve Palia


Editing Engine.ini in "C:\Users\%UserName%\AppData\Local\Palia\Saved\Config\WindowsClient" will increase overall performance across all kinds of systems. 
It could resolve unexpected and unexplainable stutters.

```
[SystemSettings]
r.bForceCPUAccessToGPUSkinVerts=True
r.GTSyncType=1
r.OneFrameThreadLag=1
r.FinishCurrentFrame=0
r.TextureStreaming=1
r.Streaming.PoolSize=3072
r.Streaming.LimitPoolSizeToVRAM=1

[ConsoleVariables]
AllowAsyncRenderThreadUpdates=1
AllowAsyncRenderThreadUpdatesDuringGamethreadUpdates=1
AllowAsyncRenderThreadUpdatesEditor=1
```


Options explained: Low-latency frame syncing https://docs.unrealengine.com/4.27/en-US/SharingAndReleasing/LowLatencyFrameSyncing/

For r.Streaming.PoolSize, set the value based on the (GPU) videomemory.

```<8GB: 2048
8GB: 3072
10GB: 4096
12GB: 5120
>12GB: 6144
