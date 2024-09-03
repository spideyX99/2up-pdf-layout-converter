# pdf2up

`pdf2up` is a Node.js library that transforms PDF documents into a 2-up layout, where two pages are combined side-by-side on a single sheet. This format is particularly useful for viewing or printing documents where you want to see two pages together.

## Installation

To install `pdf2up`, you need to use npm. Run the following command:

```bash
npm install pdf2up
```

## Usage

To use `pdf2up`, you need to convert a PDF file into the 2-up layout format. Here’s a basic example of how to do this:

```javascript
const { convertTo2up } = require('pdf2up');
const fs = require('fs');

async function processPdf(inputPath, outputPath) {
    // Read the PDF file
    const inputPdfBytes = fs.readFileSync(inputPath);

    // Convert to 2-up layout
    const newPdfBytes = await convertTo2up(inputPdfBytes);

    // Write the converted PDF to a new file
    fs.writeFileSync(outputPath, newPdfBytes);
}

// Example usage
processPdf('input.pdf', 'output-2up.pdf').then(() => {
    console.log('PDF converted to 2-up layout successfully!');
});
```

## API

### `convertTo2up(pdfBytes)`

- **Parameters:**
  - `pdfBytes` (Uint8Array or ArrayBuffer): The byte array of the original PDF document.
- **Returns:**
  - `Promise<Uint8Array>`: A promise that resolves with the byte array of the converted PDF in 2-up layout.

## Example

Here’s an example of how you might use `pdf2up` in a Node.js application:

```javascript
const { convertTo2up } = require('pdf2up');
const fs = require('fs');

// Load PDF file from disk
const inputPdfBytes = fs.readFileSync('input.pdf');

// Convert to 2-up layout
convertTo2up(inputPdfBytes).then(newPdfBytes => {
    // Save the new PDF file
    fs.writeFileSync('output-2up.pdf', newPdfBytes);
});
```

## Credits

This library is built on top of [pdf-lib](https://pdf-lib.js.org/), a powerful library for manipulating PDF documents in JavaScript. Special thanks to the authors of `pdf-lib` for their contributions to this excellent tool.

## License

This project is licensed under the MIT License. 
