# QRCoder

## Info 

This fork of QRCoder focuses on performance improvements to lessen generation time.

Current implementation is around 50 ~ 60x faster than original library in generation time and 2 ~ 10x faster in bitmap drawing.

### Differences
The differences between original QRCoder and this fork are listed as follow.

Since QRCodeGenerator has been changed to a static class, we don't have to instantiate it anymore.

For bitmap generation from QRCode class, the quiet zone has been paramatrized into the fourth GetGraphics method, overriding the original "drawQuietZone". Using value 4 for this parameter will produce exactly the same quiet zone length as the library before. You can increase or decrease to change the padding size of the quiet zone.
```csharp
QRCodeData qrCodeData = QRCodeGenerator.CreateQrCode("The text which should be encoded.", QRCodeGenerator.ECCLevel.Q);
QRCode qrCode = new QRCode(qrCodeData);
Bitmap qrCodeImage = qrCode.GetGraphic(20, Color.Black, Color.White, 4)
```

For other information, please visit the author's site.
