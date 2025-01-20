# MIDI Note Converter

A simple, lightweight tool for converting between musical notes and MIDI note numbers. This tool provides both a visual interface and a JavaScript API for note conversion.

Try it here: https://steveseguin.github.io/midinote/

## Features

- Convert musical notes (C-B with sharps) and octaves to MIDI note numbers (0-127)
- Reverse conversion from MIDI numbers to note/octave pairs
- Modern, responsive web interface
- Standalone JavaScript API for programmatic use
- No external dependencies

![image](https://github.com/user-attachments/assets/a1bd717d-0261-48e2-8722-3d1cea333d16)

## Quick Start

1. Clone or download the repository
2. Open `index.html` in a web browser
3. Use the dropdowns to select a note and octave
4. View the corresponding MIDI note number

## API Usage

### Converting Note to MIDI Number

```
// Example usage
const midiNumber = midiNoteConverter.toMIDI('C', 4);  // Returns 60
const midiNumber = midiNoteConverter.toMIDI('A', 4);  // Returns 69
```

### Converting MIDI Number to Note

```javascript
const noteInfo = midiNoteConverter.fromMIDI(60);  
// Returns { note: 'C', octave: 4 }
```

## Integration with WebMidi.js

This tool can be used alongside WebMidi.js v3 for more advanced MIDI functionality:

```javascript
// Example integration
WebMidi.enable().then(() => {
    const note = 'C';
    const octave = 4;
    const midiNumber = midiNoteConverter.toMIDI(note, octave);
    
    // Use the MIDI number with WebMidi.js
    const output = WebMidi.outputs[0];
    output.playNote(midiNumber);
});
```

## Customization

### Styling

The interface uses CSS variables for easy customization. The main styling is contained in the `<style>` section of `index.html`. Key style elements include:

- Gradient background
- Glassmorphism effect
- Responsive layout
- Interactive dropdowns

### Adding Features

To extend the functionality:

1. Modify the `midiNoteConverter` object for additional conversion features
2. Update the UI in the HTML section
3. Add event listeners for new interactive elements

## Technical Details

- Note range: C-B with sharps (C, C#, D, D#, etc.)
- Octave range: -1 to 9
- MIDI number range: 0-127
- Invalid combinations return `null`

## Browser Support

Works in all modern browsers that support:
- ES6 JavaScript
- CSS Grid and Flexbox
- Linear gradients
- Backdrop-filter (for glassmorphism effect)

## License

MIT License - Feel free to use in any project

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request
