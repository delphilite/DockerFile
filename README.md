# Delphi Docker Build Environment
![License](https://img.shields.io/github/license/delphilite/DockerFile)
![stars](https://img.shields.io/github/stars/delphilite/DockerFile.svg)

[English](./README.md) | [Chinese](./README.zh-CN.md)

This repository provides a collection of Dockerfiles to create Docker-based build environments for Delphi on Windows. It simplifies the process of building Delphi projects by ensuring a consistent, isolated environment.

## Features
* Dockerfiles for Delphi XE2+ version.
* Configured for Windows process isolation mode.

## Usage
You can use this image in two ways: as a base image in a Dockerfile or by running it directly.

### Option 1: Use as a Base Image
Use the provided images as a base to build your Delphi projects:

```dockerfile
FROM delphilite/delphilite:xe2-ltsc2022
SHELL ["powershell"]

COPY YourApp /build/app
WORKDIR /build/app
RUN msbuild /t:build YourApp.dproj;
```

### Option 2: Run Directly in Docker
Run the Docker container directly and mount your project directory:

```bash
docker run -v C:\host_dir:C:\build\app delphilite/delphilite:xe2-ltsc2022 msbuild /t:build C:\build\app\YourApp.dproj
```

### Supported Tags
Each image tag corresponds to a Delphi version and Windows base image combination. Example tags:
- `xe2-ltsc2022`: Delphi XE2 on Windows LTSC 2022.
- `xe2-win-ltsc2022`: Delphi XE2 (x86+x64 only) on Windows LTSC 2022.
- `xe2-win32-ltsc2022`: Delphi XE2 (x86 only) on Windows LTSC 2022.

Refer to the Docker Hub repository for a complete list of available tags.

## Getting Started
Follow these steps to build your own Docker image locally:

1. **Install Docker Desktop**
   Ensure Docker Desktop is installed and switched to Windows containers mode.

2. **Prepare Proxy and Web Services (Optional)**
   Set up file services like [3proxy](https://github.com/3proxy/3proxy) and [Caddy](https://github.com/caddyserver/caddy) if needed for your build process.

3. **Clone This Repository**
```bash
git clone https://github.com/delphilite/dockerfile.git
```

4. **Build the Docker Image**
   Replace <your3proxy> and <yourimagename> with your actual settings:
```bash
docker build --build-arg http_proxy=http://<your3proxy> -t <yourimagename>:xe2-ltsc2022 -f Dockerfile-Full .
```

## Documentation
For more detailed information, refer to [Docker's official website](https://www.docker.com/get-started).

## Contributing
Contributions are welcome! Please fork this repository and submit pull requests with your improvements.

## License
This project is licensed under the Mozilla Public License 2.0. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
Special thanks to the following projects:
- [3proxy](https://github.com/3proxy/3proxy): A free, open-source proxy server that supports numerous protocols and provides various network services.
- [Caddy](https://github.com/caddyserver/caddy): A powerful, extensible web server written in Go, known for its automatic HTTPS feature and easy configuration.

## Disclaimer
This code is predetermined for educational, personal, AND non-commercial use only. Please buy and use only original licensed software.

The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.
