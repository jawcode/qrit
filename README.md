# qrit
QR Information Transfer

A method for sending data one-way using QR codes; no wires, no addressing, just reading codes. To use, the receiving system turns on its camera to begin scanning for QR codes. Then, the sending device will load a file, hit "Send Data", and then let the system run on both sides. Transfer rates are pretty abysmal in this initial implementation at approximately 50 - 100Kb/s depending on the "chunk" size versus delay between QR codes.

![alt text](https://github.com/jawcode/qrit/raw/main/qrTransfer.png?raw=true)

The HTML file is an all-in-one donwload that has embedded scripts from the following repos:

QR Scanning: https://github.com/nimiq/qr-scanner
QR Creation: https://davidshimjs.github.io/qrcodejs/
