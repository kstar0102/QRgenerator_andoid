# QRGenerator
QR Generator Library and Saves the QR Code as Image
### How to Import the Library:
<b>Gradle:</b>
```
compile 'androidmads.library.qrgenearator:QRGenearator:1.0.0'
	
repositories{
    maven{
        url 'https://dl.bintray.com/androidmads/maven'
    }
}
```

### Permission:
Add This Permission for saving your generated code
```
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```
### How to use this Library:
After importing this library, use the following lines to use this library.
The following lines are used to generated the QR Code
```
// Initializing the QR Encoder with your value to be encoded, type you required and Dimension
QRGEncoder qrgEncoder = new QRGEncoder(inputValue, null, QRGContents.Type.TEXT, smallerDimension);
try {
  // Getting QR-Code as Bitmap
  bitmap = qrgEncoder.encodeAsBitmap();
  // Setting Bitmap to ImageView
  qrImage.setImageBitmap(bitmap);
} catch (WriterException e) {
  Log.v(TAG, e.toString());
}
```

Save QR Code as Image 
```
// Save with location, value, bitmap returned and type of Image(JPG/PNG).
QRGSaver.save(savePath, edtValue.getText().toString().trim(), bitmap, QRGContents.ImageType.IMAGE_JPEG);
```

For more Details <a href="https://github.com/androidmads/QRGenerator/blob/master/app/src/main/java/androidmads/example/MainActivity.java">Visit Here</a>

# License:
```
The MIT License (MIT)

Copyright (c) 2016 AndroidMad / Mushtaq M A

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
