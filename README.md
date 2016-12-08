# Kraken CLI

> Optimize images with the Kraken.io API.


## Dependencies

- [jq](https://stedolan.github.io/jq) - Used to parse JSON responses.


## Install

```
$ curl https://raw.githubusercontent.com/kjbrum/kraken-cli/master/kraken > ~/bin/kraken
$ chmod +x ~/bin/kraken
```


## Usage

```
Kraken CLI

Optimize images with the Kraken.io API.

Usage:
    $ kraken <options>

Options:
    --callback=<url>            Callback URL for posting the response to
    --convert=<json>            Convert your image to a different format
                                    - https://kraken.io/docs/image-type-conversion
    --dev                       Enable developer mode (false)
    --file=<path/to/file>       Path to the file to upload and optimize
    --help                      Display the help text
    --lossy                     Enable lossy optimization (false)
    --meta=<array>              Preserve metadata of the image (profile|date|copyright|geotag|orientation)
    --orient                    Enable lossless rotation of the image (false)
    --quality=<integer>         Quality of the optimized image (1-100)
    --resize=<json>             Resize or generate multiple sizes of the given image
                                    - https://kraken.io/docs/image-resizing
                                    - https://kraken.io/docs/generating-image-sets
    --sampling=<subsampling>    Set a custom chroma subsampling for the optimization (4:2:0|4:2:2|4:4:4)
    --status                    Query your account status
    --url=<url>                 URL of the image you want to optimize
    --webp                      Enable returning WebP format (false)

Example:
    $ kraken --url=http://example.com/image.jpg --lossy --convert='{"format": "jpg", "background": "#ff0000"}'
    $ kraken --url=http://example.com/image.jpg --meta='["profile", "date"]'
    $ kraken --file=path/to/image.jpg --resize='{"size": 150, "strategy": "square"}'
    $ kraken --file=path/to/image.jpg --lossy --quality=50 --webp
```


## Config

[Find/create your API credentials here.](https://kraken.io/account/api-credentials)

##### KRAKEN_KEY

Your Kraken.io API key.

##### KRAKEN_SECRET

Your Kraken.io API secret.


## To-do

- Add external storage options
    - [] https://kraken.io/docs/storage-s3
    - [] https://kraken.io/docs/storage-cloudfiles
    - [] https://kraken.io/docs/storage-azure
    - [] https://kraken.io/docs/storage-softlayer


## License

Copyright © [Kyle Brumm](http://kylebrumm.com). Free to use on whatever and may be redistributed under the terms specified in the [license](LICENSE.md).
