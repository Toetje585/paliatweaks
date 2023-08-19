# paliatweaks
A repo containing usefull Unreal Engine tweaks to improve Palia

- Reduce game stutters across all kinds of systems

Editing **Engine.ini**

```
[SystemSettings]
D3D12.PSO.DiskCache=1                   ; Peformance tweak Pipeline State Objects (PSOs), to change GPU states more quickly.
D3D12.PSO.DriverOptimizedDiskCache=1    ; Peformance tweak
r.TextureStreaming=1                    ; (1) Enable Texture Streaming / (0) Disable texture streaming.
r.Streaming.PoolSize=2048               ; 2048,4096,5120,6144
r.ShaderPipelineCache.Enabled=1         ; which allows the pipeline cache to load existing data from disk and precompile it.
r.ShaderPipelineCache.StartupMode=3     ; Compile collected shaders before game starts
```

# Options explained

The texture streaming system, or texture streamer, is the part of the engine responsible for increasing and decreasing the resolution of each texture. This enables you to have good visual quality while managing the available memory efficiently.
especially for low/mid range gpu's this is usefull. 

For r.Streaming.PoolSize, set the value based on the (GPU) videomemory.

```<8GB: 2048
8GB: 3072
10GB: 4096
12GB: 5120
>12GB: 6144 or set r.TextureStreaming=0 (Load all high ress textures into gpu memory and disable texture streaming)

**Load all textures in memory, only for gpu's that have more then 12GB of vram:**

r.TextureStreaming=0
r.Streaming.PoolSize=0

```

Editing **GameUserSettings.ini**

If you use gsync or freesync make sure to disable vsync and set the FrameRateLimit (3) frames below the monitors refreshrate eg for a 120hz display it would be 117.

```
FrameRateLimit=117.000000
```

