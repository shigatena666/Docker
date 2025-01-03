### Useful Links
- **[Servarr Wiki](https://wiki.servarr.com/)**: Comprehensive documentation for the *Arr* applications.
- **[Trash Guides](https://trash-guides.info/)**: User-friendly guides for Sonarr, Radarr, and related tools.
- **[Ascii ART](https://patorjk.com/software/taag/#p=display&f=ANSI%20Shadow)**: Create ASCII art for your projects.

### Installation Process
1. **Preparation**:
   - Ensure you are in the same directory as `docker-compose.yml` and `.env` files.

2. **Deployment Commands**:
   - To deploy the stack, run:
     ```bash
     sudo docker-compose up -d 
     ```
   - To stop and remove the stack, use:
     ```bash
     sudo docker-compose stop
     sudo docker-compose rm 
     ```

### Service Configuration

#### qBittorrent Configuration
1. **Find Container ID**:
   - Execute:
     ```bash
     sudo docker ps
     ```
2. **Check Logs**:
   - Use the container ID to view logs:
     ```bash
     sudo docker logs <qbittorrent-container-id>
     ```
   - Look for a line indicating the temporary password.

3. **Access WebUI**:
   - Go to [http://localhost:8080](http://localhost:8080) and log in with the provided credentials.
   - Navigate to Tools > Options > WebUI, change the username and password, and enable "bypass authentication for clients on localhost".

#### Prowlarr Configuration
- Access at [http://localhost:9696](http://localhost:9696).
- Go to Settings > Download Clients > `+` > Add qBittorrent.
- Match the port ID with qBittorrent's WebUI (default is 8080) and enter the credentials set earlier.
- Change Host from localhost to your host machine's IP address (use `ip address` command).

#### Sonarr Configuration
- Access at [http://localhost:8989](http://localhost:8989).
- Set up Root Folder under Settings > Media Management as `/data/tvshows`.
- Repeat the download client setup as done in Prowlarr.
- Copy API key from Settings > General and add it in Prowlarr under Settings > Apps.

#### Radarr Configuration
- Access at [http://localhost:7878](http://localhost:7878).
- Set Root Folder as `/data/movies`.
- Follow similar steps as Sonarr for download client setup and API key integration.

#### Lidarr Configuration
- Access at [http://localhost:8686](http://localhost:8686).
- Configure similarly to Radarr.

#### Readarr Configuration
- Access at [http://localhost:8787](http://localhost:8787).
- Follow Lidarr's configuration steps.

#### Homarr Configuration
- Access at [http://localhost:7575](http://localhost:7575).
- Configure as per previous applications.

### Final Steps
1. In Prowlarr, click on Indexers > Add Indexer, search for indexers like 'rarbg' or 'yts', test, and save.
2. Click on 'Sync App Indexers' icon to ensure synchronization.
3. Verify that green 'Full sync' appears next to each application under Settings > Apps.

### Plex Configuration
1. Access at [http://localhost:32400](http://localhost:32400/).
2. Add media libraries matching folders specified in `docker-compose.yml`, such as:
   - `/data/Movies`
   - `/data/TVShows`
   - `/data/Animes`

With these steps completed, your *Arr* stack is fully operational, enabling you to add movies in Radarr or series in Sonarr and trigger downloads effectively.

### Paperless-ngx
1. **Preparation**:
   - Ensure you are in the same directory as `docker-compose.yml` and `.env` files.

2. **Deployment Commands**:
   - To deploy the stack, run:
     ```bash
     sudo docker-compose up -d 
     ```
   - To stop and remove the stack, use:
     ```bash
     sudo docker-compose stop
     sudo docker-compose rm 
     ```
