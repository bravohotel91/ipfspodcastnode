# [bravohotel91/ipfspodcastnode](https://github.com/bravohotel91/ipfspodcastnode)

[IPFS Podcasting Node](https://ipfspodcasting.net) is a node providing Decentralized Podcast Distribution over IPFS - Crowd hosting podcast episodes with storage & bandwidth provided by volunteer nodes.

## Application Setup

Access the webui at `http://<your-ip>:8675`.

Go to IPFSPodcasting.net and create an account. 

Then enter your IPFSPodcasting.net account email in the top left hand corner and update the node to register your node to your account.

## Usage

To help you get started creating a container from this image you can either use docker-compose or the docker cli.

### docker-compose (recommended, [click here for more info](https://github.com/bravohotel91/ipfspodcastnode/blob/main/docker-compose.yml))

```yaml
---
services:
  web:
    image: ghcr.io/bravohotel91/ipfspodcastnode:latest
    init: true
    restart: on-failure
    stop_grace_period: 1m
    user: "1000:1000"
    ports:
      - 4001:4001  # IPFS
      - 8675:8675  # Web UI
    volumes:
      - ${APP_DATA_DIR}/ipfs:/ipfs-podcasting/ipfs
      - ${APP_DATA_DIR}/cfg:/ipfs-podcasting/cfg
```