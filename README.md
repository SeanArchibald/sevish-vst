# sevish-vst

Microtonal VST intruments/effects built using Camomile and Pure Data.

## Getting Started

The contents of this repository contain only the source files for the plugins. In order to get the plugins working in your DAW or VST host, you need to [download the Camomile plugins](https://github.com/pierreguillot/Camomile/releases/latest) and [follow these intructions](https://github.com/pierreguillot/Camomile/wiki/How-to-generate-plugins).

## The Plugins

### Sampler

Stereo sampler with a traditional subtractive-synth topology. Probably only supports WAV, I haven't tried MP3s with it. 6-voice polyphony. This instrument uses up most of my CPU when running idle. Any ideas for optimisation would be appreciated.

### Sub

A monophonic additive synth, optimised for sub bass. Jolly good for adding weight to mixes, or doubling a bass part to add more weight to that part. Also you can use the pitch envelope to achieve a TR-808-like boom.

### MidiNoteScaler

MidiNoteScaler is a MIDI effect. You specify a source EDO and an output EDO, and it will change the MIDI note number of all incoming note messages.

Example use case: you have a MIDI sequence in 12-EDO, and your synth is tuned to 19-EDO. Put MidiNoteScaler in the chain before the synth. Set input to 12, output to 19. Now when you play the sequence, you will hear something very similar to the original 12-EDO music but each note is tuned to the nearest note from 19-EDO.

Beware of ~~rounding errors~~ stimulus for inspiration.

## Microtuning

In a perfect world, these instruments would support all the popular microtuning formats such as Scala scl/kbm or AnaMark TUN. Currently, Pd vanilla doesn't support any microtuning formats, so neither do these plugins. For now I'm happy to use a specific text format.

If you want to have an easy time, just use my [Scale Workshop](http://sevish.com/scaleworkshop) to import a .scl file and then export the Pure Data text format microtuning.

The properly formatted text file contains 128 lines. Each line contains a frequency (in Hz) followed by a semicolon. The first line corresponds with MIDI note 0, ascending through each MIDI note up to 127 on the last line. Example (12-edo A=440):

```
8.1757989;
8.6619572;
9.1770240;
9.7227182;
10.3008612;
10.9133822;
...
12543.8539514;
```

## Built With

* [Camomile](https://github.com/pierreguillot/Camomile/) - It turns Pure Data patches into VSTs
* [Pure Data](https://puredata.info/) - It turns lines and boxes into microtonal music (at least that was my experience)

## Contributing

Feel free.

## Authors

* [Sevish](http://sevish.com) - he started this project because he needed a microtonal polyphonic sampler with native Linux support.
