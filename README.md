# useful_ubuntu
## Merge pdf files
Ghostscript is a package (available by default in Ubuntu) that enables you to view or print PostScript and PDF files to other formats, or to convert those files to other formats.
To use Ghostscript to combine PDF files, type something like the following:

```bash
gs -dBATCH -dNOPAUSE -q -sDEVICE=pdfwrite -dAutoRotatePages=/None -sOutputFile=output.pdf  input_file1.pdf input_file2.pdf
```

Some explanation
```
gs         starts the Ghostscript program.
-dBATCH    once Ghostscript processes the PDF files, it should exit.
           If you don't include this option, Ghostscript will just keep running.
-dNOPAUSE  forces Ghostscript to process each page without pausing for user interaction.
-q         stops Ghostscript from displaying messages while it works
-sDEVICE=pdfwrite 
           tells Ghostscript to use its built-in PDF writer to process the files.
-sOutputFile=finished.pdf
           tells Ghostscript to save the combined PDF file with the specified name.
-dAutoRotatePages=/None
           Acrobat Distiller parameter AutoRotatePages controls the automatic orientation selection algorithm: For instance: -dAutoRotatePages=/None or /All or /PageByPage.
```

ref: [https://askubuntu.com/a/257170/996807](https://askubuntu.com/a/257170/996807)

## Use python virtualenv with jupyter notebook
Create the python virtual environment, activate and install `ipykernal`
```bash
python3 -m venv ./venv_name
source ./venv_name/bin/activate
pip install ipykernal
python3 -m ipykernel install --user --name=venv_name
```

# Image and videos
## Convert images sequences to videos
```bash
ffmpeg -framerate 20 -i %06d.png -codec copy output.mp4
```
## Convert videos to images
```bash
# extract every 1 second
ffmpeg -i video.MP4 -vf fps=1 %6d.png
```

## Access ubuntu workstations in the local network
```bash
ssh <username>@<computer_name>.local
```
