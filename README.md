# AMP template for Moon Sweepers dedicated server

Contains the AMP template files, `Dockerfile.amp`, `container/`, `native/`, and a GitHub Actions workflow that builds and pushes the image to GHCR.

## Usage
1. Create a public GitHub repo (e.g. `BulletBound/moonsweeper`) and upload this folder's contents to `main`.
2. The workflow builds and pushes `ghcr.io/bulletbound/moon-sweepers-server:v1`.
3. After the first successful build: GitHub -> Packages -> `moon-sweepers-server` -> Package settings -> Change visibility -> **Public**.
4. In AMP: Configuration -> Instance Deployment -> Add Configuration Repository -> `BulletBound/moonsweeper:main`, then Fetch.
5. Create an instance from "MS Moon Sweepers Dedicated Server" and set a Server Password (8-128 printable ASCII) in the instance settings.
6. Start once: AMP creates `moonsweepers/5335510/import/game` automatically.
7. Upload the game ZIP into `moonsweepers/5335510/import/game` (File Manager) and extract it so `MoonSweepers.exe` is directly inside that folder.
8. Start the instance.

The container maps `/data` to `moonsweepers/5335510/`, so saves, logs, backups, Wine prefix and the imported game all live inside that instance subfolder.
