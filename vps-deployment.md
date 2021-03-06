# Process to run this BOT on VPS

- Clone this repo:
```
git clone https://github.com/gautamajay52/TorrentLeech-Gdrive torrentleech-gdrive
cd torrentleech-gdrive
```

- Install requirements
For Debian based distros
```
sudo snap install docker
```
Install Docker by following the [official docker docs](https://docs.docker.com/engine/install/debian/)

## Setting up config file
```
cp sample_config.env config.env
```
After this step you will see a new file named ```config.env``` in root directory.

Fill those compulsory variables.

If you need more explanation about any variable then read [app.jso](https://github.com/gautamajay52/TorrentLeech-Gdrive/blob/master/app.jso)

##### Set Rclone

1. Set Rclone locally by following the official repo : https://rclone.org/docs/
2. Get your `rclone.conf` file.
will look like this
```
[NAME]
type = 
scope =
token =
client_id = 
client_secret = 

```
2 Copy `rclone.conf` file in the root directory (Where `Dockerfile` exists).

3 Your config can contains multiple drive entries.(Default: First one and change using `/rclone` command)

## Deploying

- Start docker daemon (skip if already running):
```
sudo dockerd
```
- Build Docker image:
```
sudo docker build . -t torrentleech-gdrive
```
- Run the image:
```
sudo docker run torrentleech-gdrive
```
Follow this [Video Tutorial](https://youtu.be/J3tMbngA9DE)
### The Legacy Way
Simply clone the repository and run the main file:

```sh
git clone https://github.com/gautamajay52/TorrentLeech-Gdrive
cd TorrentLeech-Gdrive
python3 -m venv venv
. ./venv/bin/activate
pip install -r requirements.txt
# <Create config.py appropriately>
python3 -m tobrot
```
