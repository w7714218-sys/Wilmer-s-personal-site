# Wilmer's Personal Site

This is my personal website where I showcase my recent projects and experiments.

## Personal Music Server

This project uses an old computer with **Linux** as a personal music server. It stores the music locally and lets me play it from different devices.

It uses **Docker** to run Jellyfin and **Tailscale** for remote access without opening Jellyfin directly to the Internet.

### Features

- Local music library.
- Jellyfin to organize and play music.
- Access from a phone, computer, and other devices.
- Remote access with Tailscale.
- Jellyfin running in Docker.
- Jellyfin automatically manages music information and covers.
- Port 8096 does not need to be open to the Internet.

### Technologies

- **Linux** as the operating system.
- **runit** for managing services.
- **Docker** to run Jellyfin.
- **Jellyfin** as the music server.
- **Tailscale** for remote access.

### Music Library

The music is stored in:

```bash
/home/ftpuser/ftp/cliente
```

Docker mounts this folder in Jellyfin as:

```bash
/media
```

Jellyfin uses **/media** as the music library folder.

### Jellyfin

Jellyfin runs in Docker and uses port:

```bash
8096
```

To check if it is running:

```bash
sudo docker ps
curl http://127.0.0.1:8096
```

### Remote Access

Tailscale lets me access the server from devices that are connected to my Tailscale network.

To see the server's Tailscale IP:

```bash
tailscale ip
```

To see the connected devices:

```bash
tailscale status
```

Jellyfin can be accessed from another device using:

```bash
http://TAILSCALE-IP:8096
```

### Security

Port **8096** is not exposed directly to the Internet.

Tailscale is used to connect the server and the authorized devices privately.

### Project Image

![Personal music server](images/myownmusicserver.png)

---

This project is part of my personal portfolio and reflects my interest in self-hosting, home infrastructure, and media systems.
