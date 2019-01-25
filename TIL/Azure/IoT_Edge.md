# Azure IoT Edge

Contents

- [Edge Deploy](#Edge_Deploy)
  - Ubuntu
  - Debian
- [Machine Learning Module Deploy](#Machine_Learning_Module_Deploy)



## Edge Deploy

MS Docs : [Linux](https://docs.microsoft.com/en-us/azure/iot-edge/how-to-install-iot-edge-linux), [Windows](https://docs.microsoft.com/en-us/azure/iot-edge/how-to-install-iot-edge-windows)

### Ubuntu

### Debian

- curl 등 Ubuntu에서 기본으로 지원하는 기능이 없어 설치해야 함

  ```sh
  sudo apt-get install \
      apt-transport-https \
      ca-certificates \
      curl \
      gnupg2 \
      software-properties-common
  ```

- Debian에 맞는 repository 및 GPG 키 설정

  ```sh
  # Install repository configuration
  curl https://packages.microsoft.com/config/debian/<version>/prod.list > ./microsoft-prod.list
  sudo cp ./microsoft-prod.list /etc/apt/sources.list.d/
  
  # Install Microsoft GPG public key
  curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
  sudo cp ./microsoft.gpg /etc/apt/trusted.gpg.d/
  
  # Perform apt upgrade
  sudo apt-get upgrade
  ```



## Machine Learning Module Deploy

