# React-Ts-Base64-Image-Encoder

`react-ts-base64-image-encoder` is a simple utility package that converts uploaded files to Base64-encoded strings. It is available for use in TypeScript or JavaScript projects.

## Installation

To install `react-ts-base64-image-encoder`, run the following command:

```
npm install react-ts-base64-image-encoder
```

## Usage

```jsx
import FileBase64 from "react-ts-base64-image-encoder";
import {useState} from 'react';

function MyComponent() {
  interface Files {
    base64: any;
    // Add any other properties as needed
  }
  const [files, setFiles] = useState<Files>();
  const getFiles = (files: any) => {
    setFiles({ ...files });
  };

  return (
    <div>
      <FileBase64 multiple={false} onDone={(files) => getFiles(files)} />
    </div>
  );
}
```

The `onDone` prop is a callback function that will be called when the user selects a file. It will be passed an array of `FileInfo` objects if the `multiple` prop is set to `true`, or a single `FileInfo` object if `multiple` is `false`.

The `FileInfo` object has the following properties:

- `name` - the name of the file
- `type` - the MIME type of the file
- `size` - the size of the file in kilobytes
- `base64` - a Base64-encoded string of the file data
- `file` - the original `File` object

## Props

- `onDone` - (required) a callback function that will be called when the user selects a file
- `multiple` - (optional) a boolean value that determines whether the user can select multiple files (default `false`)
