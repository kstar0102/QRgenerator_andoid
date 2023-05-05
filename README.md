# QRGenerator
QR Generator Library and Saves the QR Code as Image

### Featured In:
[![](https://jitpack.io/v/androidmads/QRGenerator.svg)](https://jitpack.io/#androidmads/QRGenerator)

[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-QRGenerator-green.svg?style=true)](https://android-arsenal.com/details/1/3890)
### How to Import the Library:
Add it in your root build.gradle at the end of repositories:

``` groovy
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}
```
<b>Gradle:</b>
```groovy
dependencies {
  implementation 'com.github.androidmads:QRGenerator:1.0.1'
}
```

### Features:
1. QR code color can be changed dynamically
2. Android X support is included
3. Minimum support from version 14 is included
4. Margin of the QR code can be controlled

### Permission:
Add This Permission for saving your generated code
```xml
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```
### How to use this Library:
After importing this library, use the following lines to use this library.
The following lines are used to generated the QR Code
```java
// Initializing the QR Encoder with your value to be encoded, type you required and Dimension
QRGEncoder qrgEncoder = new QRGEncoder(inputValue, null, QRGContents.Type.TEXT, smallerDimension);
qrgEncoder.setColorBlack(Color.RED);
qrgEncoder.setColorWhite(Color.BLUE);
try {
  // Getting QR-Code as Bitmap
  bitmap = qrgEncoder.getBitmap();
  // Setting Bitmap to ImageView
  qrImage.setImageBitmap(bitmap);
} catch (WriterException e) {
  Log.v(TAG, e.toString());
}
```
The following lines are used to generated the QR Code without margin/default border
```java
// Initializing the QR Encoder with your value to be encoded, type you required and Dimension
QRGEncoder qrgEncoder = new QRGEncoder(inputValue, null, QRGContents.Type.TEXT, smallerDimension);
qrgEncoder.setColorBlack(Color.RED);
qrgEncoder.setColorWhite(Color.BLUE);
try {
  // Getting QR-Code as Bitmap
  bitmap = qrgEncoder.getBitmap(0);
  // Setting Bitmap to ImageView
  qrImage.setImageBitmap(bitmap);
} catch (WriterException e) {
  Log.v(TAG, e.toString());
}
```

Save QR Code as Image 
```java
// Save with location, value, bitmap returned and type of Image(JPG/PNG).
QRGSaver qrgSaver = new QRGSaver();
qrgSaver.save(savePath, edtValue.getText().toString().trim(), bitmap, QRGContents.ImageType.IMAGE_JPEG);
```

For more Details [Click Here](https://github.com/androidmads/QRGenerator/blob/master/app/src/main/java/androidmads/example/MainActivity.java)
