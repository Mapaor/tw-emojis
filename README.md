### Assets TW Emojis
Twitter emojis from [https://github.com/jdecked/twemoji](https://github.com/jdecked/twemoji) as svgs, and pngs for using on custom websites, mail signatures, or whatever.
- [svgs](./tw-emojis-svgs)
- [pngs 128x128](./tw-emojis-pngs)
- [pngs 36x36](./tw-emojis-pngs-36x36)

### Tip to use them
To make it have the same size and alignment as text you can set a custom class like:

```
.emoji { 
	width: 24px; 
	height: 24px; 
	vertical-align: middle; 
	margin-left: 4px;
  margin-right: 4px;
} 
```

And then:
```
<p>This is a sample text <img src='1f004.png' class='emoji'> that includes an emoji.</p>
```

### Tools used
I used Inkscape CLI to render the pngs from the svgs. 
<details>
  
<summary>How to do it</summary>

Note: this is only displayed properly in the markdown file, not in the github pages version of the markdown file.

### Install Inkscape and add it to PATH

1. To install Inkscape, simply download the Inkscape app (GUI) from [https://inkscape.org/release/](https://inkscape.org/release/).
2. Inkscape CLI would be automatically installed but probably won't be added to PATH.
   1. Check if is added to PATH with:
      
      ```
      inkscape --version
      ```
      
      If it does not return a version number it means Inkscape is not added to PATH.
      
   3. To add it to PATH for Windows, first do Win+R and type `C:\Program Files\Inkscape\bin`. Check there is an executable `inkscape.exe`.
   4. If there is great, we'll add it by searching (in the windows search) 'system environment variables' > 'environment variables' > 'system variables' > 'Path' > 'Edit' > 'New' > 'C:\Program Files\Inkscape\bin' > 'Accept', 'Accept', 'Accept'.
   5. Close the terminal, open a new one and check again with `inkscape --version`. It should return something like `Inkscape 1.3.2 (091e20e, 2023-11-25, custom)`.


#### Use Inkscape CLI
For example to render an individual file we would do:

```
inkscape input.svg --export-filename=output.png --export-width=128 --export-height=128
```

And the powershell script used for this repo was:

<details>

<summary>Simpler version</summary>

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

```
$inputDir = "tw-emojis-svgs"
$outputDir = "tw-emojis-pngs"

New-Item -ItemType Directory -Force -Path $outputDir | Out-Null

$svgFiles = Get-ChildItem "$inputDir\*.svg"
$total = $svgFiles.Count
$counter = 0

foreach ($file in $svgFiles) {
    $counter++
    $filename = $file.BaseName

    inkscape "$($file.FullName)" `
        --export-filename="$outputDir\$filename.png" `
        --export-width=128 --export-height=128

    Write-Host "[$counter/$total] Converted: $filename.svg -> $filename.png"
}

Write-Host "`n✅ Done! Converted $counter SVG files to PNGs in '$outputDir'."
```

</details>

#### Optional
Use [jsDelivr](https://www.jsdelivr.com/) for faster delivering across the world. For example:
- Instead of [https://mapaor.github.io/tw-emojis/tw-emojis-svgs/1f004.svg](https://mapaor.github.io/tw-emojis/tw-emojis-svgs/1f004.svg) use [https://cdn.jsdelivr.net/gh/mapaor/tw-emojis/tw-emojis-svgs/1f004.svg](https://cdn.jsdelivr.net/gh/mapaor/tw-emojis/tw-emojis-svgs/1f004.svg).
- Instead of [https://mapaor.github.io/tw-emojis/tw-emojis-pngs/1f004.png](https://mapaor.github.io/tw-emojis/tw-emojis-pngs/1f004.png) use [https://cdn.jsdelivr.net/gh/mapaor/tw-emojis/tw-emojis-pngs/1f004.png](https://cdn.jsdelivr.net/gh/mapaor/tw-emojis/tw-emojis-pngs/1f004.png)

### Sample Videos
Maybe you're also interested in sample videos as URL mp4 files: [https://github.com/Mapaor/sample-videos](https://github.com/Mapaor/sample-videos)
