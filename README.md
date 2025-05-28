# Classes_Overview
 
para tansformar todos os arquivos .png em .avif usase o código

no powershell


``` bash
New-Item -ItemType Directory -Name "avif_output" -ErrorAction SilentlyContinue

Get-ChildItem -Path *.png | ForEach-Object {
  $filename = $_.BaseName
  ffmpeg -i $_.FullName -c:v libaom-av1 -still-picture 1 -crf 28 ".\avif_output\$filename.avif"
}
```