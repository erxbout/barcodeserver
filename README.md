# BarCodeServer

Simple HTTP API around [https://github.com/boombuler/barcode](https://github.com/boombuler/barcode).

## Api Usage

Simply issue a get using the type of barcode desired as path and the content as queryString content and it will return a generated png.

    curl -v http://localhost:8080/datamatrix?content=Whatever%20data

Available types:

* codabar
* code128
* code39
* ean
* datamatrix
* qr
* 2of5

In case of error it will return Bad Request 400 and error in plain/text.

## Deploy

Using the binary, download from the release page and run the binary and it will bind to port 8080.

Using docker:

    docker run -p 8080:8080 erxbout/barcodeserver

Example docker-compose.yml with custom port 8000:

``` yaml
version: "3.4"

services:
  barcodeserver:
    image: erxbout/barcodeserver
    ports:
      - 8000:8000
    environment: 
      PORT: 8000

```

## License 

MIT, same as [https://github.com/boombuler/barcode](https://github.com/boombuler/barcode).
