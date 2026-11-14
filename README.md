# noseb13eds' brozzler and warcprox script

### 'nbaws' for short

bash script for archiving websites as .warc files using brozzler, warcprox, and yt-dlp.

## dependencies

[python](https://www.python.org/downloads/)

[rethinkdb](https://rethinkdb.com/docs/install/)

[chromium](https://www.chromium.org/getting-involved/download-chromium/)

## yt-dlp dependencies

`yt-dlp` has dependencies not included with the pip install found [here](https://github.com/yt-dlp/yt-dlp#dependencies) (mainly [ffmpeg/ffprobe](https://www.ffmpeg.org/download.html), [curl_cffi](https://www.ffmpeg.org/download.html), and [deno](https://deno.com/)).

## setup

install the above dependencies, and then run the following commands in the project directory:

```
python -m venv .venv
source .venv/bin/activate

# if installing curl_cffi for yt-dlp via pip:
pip install curl_cffi --upgrade

pip install warcprox brozzler[rethinkdb]
pip install -U --pre yt-dlp[default]

deactivate
```

## usage

```
source .venv/bin/activate
./nbaws jobs/example-job.yaml
```

jobs can be configured with a .yaml file.

an example job file is included in the `jobs` directory, and a guide for configuring job files can be found [here](https://github.com/internetarchive/brozzler/blob/master/job-conf.rst).
