---
tags:
  - CS381
---
Waveform Audio File Format is an audio file format standard used for storing an audio bitstream on personal computers.

WAV is an application of the [[RIFF]] bitstream format method for storing data in chunks, and thus is similar to the 8SVX and the AIFF format used on Amiga and Macintosh computers, respectively. 

## WAV File Header
This is an example of a WAV file header (44 bytes). Data is stored in little-endian byte order.

```
[Master RIFF chunk]
   FileTypeBlocID  (4 bytes) : Identifier « RIFF »  (0x52, 0x49, 0x46, 0x46)
   FileSize        (4 bytes) : Overall file size minus 8 bytes
   FileFormatID    (4 bytes) : Format = « WAVE »  (0x57, 0x41, 0x56, 0x45)

[Chunk describing the data format]
   FormatBlocID    (4 bytes) : Identifier « fmt␣ »  (0x66, 0x6D, 0x74, 0x20)
   BlocSize        (4 bytes) : Chunk size minus 8 bytes, which is 16 bytes here  (0x10)
   AudioFormat     (2 bytes) : Audio format (1: PCM integer, 3: IEEE 754 float)
   NbrChannels     (2 bytes) : Number of channels
   Frequency       (4 bytes) : Sample rate (in hertz)
   BytePerSec      (4 bytes) : Number of bytes to read per second (Frequency * BytePerBloc).
   BytePerBloc     (2 bytes) : Number of bytes per block (NbrChannels * BitsPerSample / 8).
   BitsPerSample   (2 bytes) : Number of bits per sample

[Chunk containing the sampled data]
   DataBlocID      (4 bytes) : Identifier « data »  (0x64, 0x61, 0x74, 0x61)
   DataSize        (4 bytes) : SampledData size
   SampledData
```

## Metadata
As a derivative of RIFF, WAVE file can be tagged with metadata in the INFO chunk. In addition, WAV files can embedded any kind of metadata, including but not limited to XMP data or ID3 tags in extra chunks. The RIFF specification requires that applications ignore chunks they do not recognise and applications may not necessarily use this extra information.

