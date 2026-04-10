# Stego Challenges

Writeups for HTB Steganography challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Widescreen](widescreen/) | Very Easy | Image Dimensions | Modifying image height/width |
| [Lame Coder](lame-coder/) | Easy | Binary in Image | Hidden binary data in images |
| [Syringe](syringe/) | Easy | LSB Steganography | Least Significant Bit extraction |
| [Pusheen Loves Graphs](pusheen/) | Easy | PNG Chunks, IDAT | Hidden data in PNG chunks |
| [HiddenGem](hidden-gem/) | Easy | Audio Steganography | Spectrogram analysis |
| [SeeTheSharpFlag](see-the-sharp/) | Medium | .NET, Steghide | Multi-layer steganography |
| [Digital Cube](digital-cube/) | Medium | 3D Model, Hidden Data | Steganography in 3D objects |
| [Ghost](ghost/) | Medium | Whitespace, Invisible Ink | Zero-width character steganography |
| [Hackvent](hackvent/) | Hard | Multi-Layer Stego | Complex multi-step stego chain |

## Techniques & Tools

### Image Steganography
```bash
# Basic analysis
file image.png
exiftool image.png
binwalk image.png

# Strings in image
strings image.png

# Steghide (JPEG)
steghide extract -sf image.jpg
steghide extract -sf image.jpg -p "password"

# zsteg (PNG/BMP)
zsteg image.png
zsteg image.png -a  # All possible extractions

# LSB extraction
python3 -c "from PIL import Image; img=Image.open('image.png'); print(''.join(str(p&1) for p in img.getdata()))"

# stegsolve
java -jar stegsolve.jar

# PNG dimensions manipulation
python3 -c "
import struct
with open('image.png','rb') as f:
    data = f.read()
# Check IHDR chunk for height/width
"
```

### Audio Steganography
```bash
# Spectrogram analysis
# Open in Audacity -> Analyze -> Spectrogram

# Sonic Visualiser
# Load file, add spectrogram layer

# SSTV (Slow Scan Television)
# Use QSSTV or Robot36 app

# Morse code
# Audacity waveform analysis
```

### Text/Document Steganography
```bash
# Whitespace stego
stegsnow -C file.txt

# Zero-width characters
python3 -c "
with open('file.txt') as f:
    text = f.read()
hidden = ''.join('1' if ord(c) == 0x200b else '0' for c in text if ord(c) in [0x200b, 0x200c])
print(bytes(int(hidden[i:i+8],2) for i in range(0,len(hidden),8)))
"

# PDF
qpdf --qdf input.pdf output.pdf
strings output.pdf | grep -i flag
```

## Tools

| Tool | Purpose |
|------|---------|
| steghide | JPEG steganography |
| zsteg | PNG/BMP LSB analysis |
| stegsolve | Visual analysis GUI |
| Audacity | Audio analysis |
| Sonic Visualiser | Advanced audio spectrogram |
| exiftool | Metadata extraction |
| binwalk | Embedded file extraction |
| foremost | File carving |
| stegcracker | Steghide brute-force |
| openstego | Various stego techniques |
