# qrit
QR Information Transfer

A method for sending data one-way using QR codes; no wires, no addressing, just reading codes. To use, the receiving system turns on its camera to begin scanning for QR codes. Then, the sending device will load a file, hit "Send Data", and then let the system run on both sides. Transfer rates are pretty abysmal in this initial implementation at approximately 100 - 200Kb/m depending on the "chunk" size versus delay between QR codes.

The idea is basic in implementation so far; take a string or convert a file into a string. Cut that string into parts that make simple-enough QR codes to scan with minimal errors. Use the browser's animation timing to delay a cycle from one part of the string to the next. Cycle through these "chunks" until reaching the end of the file. File transfers are marked with a beginning "header" that includes transfer type and number of chunks to receive. Tail data includes the file name being transferred. The receiving end starts building an array of chunks when it sees the header, and it collapses the array back to a string when it sees all chunks as described by the header. Once reassembled, the file gets downloaded with an HTML element operation.

![alt text](https://github.com/jawcode/qrit/raw/main/qrTransfer.png?raw=true)

The HTML file is an all-in-one download that has embedded scripts to create and scan QR codes. Scripts are from the following repos:

QR Scanning: https://github.com/nimiq/qr-scanner
QR Creation: https://davidshimjs.github.io/qrcodejs/
