This repository merely exists to preserve it as an easily buildable copy, as the original source used a strange MonoGame layout.
I've provided a build artifact with the relevant `dotnet` version bundled, for easy usage of the project under `wine`, as that's how I would use it.

The following commands process can be used to build that on Linux, assuming .NET 6.0 with the right target available:

```bash
winetricks d3dcompiler_47 dotnet6
dotnet tool restore
MGFXC_WINE_PATH=$WINEPREFIX dotnet publish -c Release -r win-x64 /p:PublishReadyToRun=false /p:TieredCompilation=false --self-contained -o <outdir>
```

Certain files have been modified to use fonts that are available on my system (DejaVu Sans, Ubuntu Mono) over Microsoft fonts. You may have to adjust them if you get a build error.
