### Assets TW Emojis
Twitter emojis from [https://github.com/jdecked/twemoji](https://github.com/jdecked/twemoji) as svgs, and pngs for using on custom websites, mail signatures, or whatever.
- [svgs](./tw-emojis-svgs)
- [pngs](./tw-emojis-pngs)
### Tools used
I used Inkscape CLI to render the pngs from the svgs. 
<details>
  
<summary>How to do it</summary>

#### Install Inkscape and add it to PATH
1. To install Inkscape, simply download the Inkscape app (GUI) from [https://inkscape.org/release/](https://inkscape.org/release/).
2. Inkscape CLI would be automatically installed but probably won't be added to PATH.
   1. Check if is added to PATH with:
      
      ```
      inkscape --version
      ```
      
      If it does not return the version it is not added to PATH.
   3. To add it to PATH for Windows, first do Win+R and type `C:\Program Files\Inkscape\bin`. Check there is an executable `inkscape.exe`.
   4. If there is great, we'll add it by searching (in the windows search) 'system environment variables' > 'environment variables' > 'system variables' > 'Path' > 'Edit' > 'New' > 'C:\Program Files\Inkscape\bin' > 'Accept', 'Accept', 'Accept'.
      
#### Use Inkscape CLI
For example to render an individual file we would do:
```
inkscape input.svg --export-filename=output.png --export-width=128 --export-height=128
```
And the powershell script used for this repo was:
```
$inputDir = "tw-emojis-svgs"
$outputDir = "tw-emojis-pngs"

New-Item -ItemType Directory -Force -Path $outputDir

Get-ChildItem "$inputDir\*.svg" | ForEach-Object {
    $filename = $_.BaseName
    inkscape "$($_.FullName)" `
        --export-filename="$outputDir\$filename.png" `
        --export-width=128 --export-height=128
}
```
</details>

### Optional
Use [jsDelivr](https://www.jsdelivr.com/) for faster delivering across the world. For example:
- Instead of [https://mapaor.github.io/tw-emojis/tw-emojis-svgs/1f004.svg](https://mapaor.github.io/tw-emojis/tw-emojis-svgs/1f004.svg) use [https://cdn.jsdelivr.net/gh/mapaor/tw-emojis/tw-emojis-svgs/1f004.svg](https://cdn.jsdelivr.net/gh/mapaor/tw-emojis/tw-emojis-svgs/1f004.svg).
- Instead of [https://mapaor.github.io/tw-emojis/tw-emojis-pngs/1f004.png](https://mapaor.github.io/tw-emojis/tw-emojis-pngs/1f004.png) use [https://cdn.jsdelivr.net/gh/mapaor/tw-emojis/tw-emojis-pngs/1f004.png](https://cdn.jsdelivr.net/gh/mapaor/tw-emojis/tw-emojis-pngs/1f004.png)
### Sample Videos
Maybe you're also interested in sample videos as URL mp4 files: [https://github.com/Mapaor/sample-videos](https://github.com/Mapaor/sample-videos)
