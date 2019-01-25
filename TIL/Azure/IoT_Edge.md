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

### Portal에서 Module 배포

Portal에서 Container registry에 등록된 ML Module을 IoT Edge 장비에 배포합니다.

1. IoT Edge가 등록된 IoT Hub로 이동, 모듈을 탑재하고자 하는 Edge Device 선택

   ![](images/iot_edge_ml_module_01.png)

2. 상단 메뉴에서 `Set Modules` 선택하여 모듈 설정으로 이동

   ![](images/iot_edge_ml_module_02.png)

3. `Container Registry Settings`에 배포하고자 하는 모듈이 있는 ACR의 정보 입력

   ![](images/iot_edge_ml_module_03.png)

4. `Deployment Module`에서 `+`버튼을 누르고, `IoT Edge Module` 선택

   ![](images/iot_edge_ml_module_04.png)

5. 우측에 나타나는 창에 원하는 모듈의 이름과 이미지 경로를 입력하고 저장

   ![](images/iot_edge_ml_module_05.png)

6. 나머지 사항은 기본 옵션으로 진행하고 배포 수행

