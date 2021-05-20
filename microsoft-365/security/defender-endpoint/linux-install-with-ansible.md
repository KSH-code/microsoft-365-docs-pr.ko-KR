---
title: Ansible와 리눅스에 엔드 포인트에 대 한 마이크로소프트 수비수 배포
ms.reviewer: ''
description: Ansible을 사용하여 리눅스에 엔드포인트에 대한 마이크로 소프트 디펜더를 배포하는 방법에 대해 설명합니다.
keywords: 마이크로 소프트, 수비수, 엔드 포인트에 대한 마이크로 소프트 수비수, 리눅스, 설치, 배포, 설치 취소, 인형, ansible, 리눅스, 레드 햇, 우분투, 데비안, 슬, suse, 센토스
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572732"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Ansible와 리눅스에 엔드 포인트에 대 한 마이크로소프트 수비수 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트에 대한 수비수를 경험하고 싶으십니까? [무료 평가판에 가입하십시오.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

이 문서에서는 Ansible을 사용하여 리눅스에 엔드포인트에 대한 수비수를 배포하는 방법에 대해 설명합니다. 성공적인 배포를 위해서는 다음 모든 작업을 완료해야 합니다.

- [온보딩 패키지 다운로드](#download-the-onboarding-package)
- [Ansible YAML 파일 만들기](#create-ansible-yaml-files)
- [배포](#deployment)
- [참조](#references)

## <a name="prerequisites-and-system-requirements"></a>전제 조건 및 시스템 요구 사항

시작하기 전에 현재 소프트웨어 버전에 대한 필수 구성 요소 및 시스템 요구 사항에 대한 설명은 [Linux의 끝점에 대한 기본 수비수 페이지를](microsoft-defender-endpoint-linux.md) 참조하세요.

또한 Ansible 배포의 경우 Ansible 관리 작업에 익숙하고 Ansible을 구성하고 플레이북 및 작업을 배포하는 방법을 알아야 합니다. Ansible은 동일한 작업을 완료하는 여러 가지 방법이 있습니다. 이러한 지침은 패키지를 배포하는 데 도움이 되는 *apt* 및 *아카이브 해제와* 같이 지원되는 Ansible 모듈의 가용성을 가정합니다. 조직에서 다른 워크플로를 사용할 수 있습니다. 자세한 내용은 [Ansible 문서를](https://docs.ansible.com/) 참조하십시오.

- Ansible은 하나 이상의 컴퓨터에 설치해야 합니다(Ansible은 이 것을 제어 노드라고 호출합니다).
- SSH는 제어 노드와 관리되는 모든 노드(엔드포인트에 대한 Defender가 설치되는 장치) 사이의 관리자 계정에 대해 구성해야 하며 공개 키 인증으로 구성하는 것이 좋습니다.
- 관리되는 모든 노드에 다음 소프트웨어를 설치해야 합니다.
  - 컬
  - 파이썬 -apt

- 관리되는 모든 노드는 다음 형식 또는 관련 파일에 나열되어야 `/etc/ansible/hosts` 합니다.

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- 핑 테스트:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>온보딩 패키지 다운로드

Microsoft Defender 보안 센터 온보딩 패키지를 다운로드하십시오.

1. Microsoft Defender 보안 센터 **온보딩**> 장치 관리 설정 >.
2. 첫 번째 드롭다운 메뉴에서 **Linux Server를** 운영 체제로 선택합니다. 두 번째 드롭다운 메뉴에서 선호하는 Linux 구성 관리 도구를 배포 방법으로 **선택합니다.**
3. **온보딩 패키지 다운로드를 선택합니다.** 파일을 WindowsDefenderATPOnboardingPackage.zip 저장합니다.

    ![Microsoft Defender 보안 센터 스크린샷](images/atp-portal-onboarding-linux-2.png)

4. 명령 프롬프트에서 파일이 있는지 확인합니다. 아카이브의 내용을 추출합니다.

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a>Ansible YAML 파일 만들기

플레이북이나 작업에 기여하는 하위 작업 또는 역할 파일을 만듭니다.

- 온보딩 작업 `onboarding_setup.yml` 만들기:

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- 끝점 리포지토리 및 키에 대한 수비수 `add_apt_repo.yml` 추가:

    리눅스의 끝점에 대한 수비수는 다음 채널 중 하나에서 배포 할 수 있습니다 *([채널]로* 아래 표시 ): *내부자 빠른,* *내부자 느린,* 또는 *prod*. 이러한 각 채널은 Linux 소프트웨어 리포지토리에 해당합니다.

    채널을 선택하면 장치에 제공되는 업데이트의 유형과 빈도가 결정됩니다. 내부자 *빠른* 장치는 업데이트 및 새로운 기능을 수신하는 첫 번째 장치입니다, 내부자 *느린* 마지막으로 *prod에* 의해 다음.

    새로운 기능을 미리 보고 초기 피드백을 제공하기 위해 엔터프라이즈내 일부 장치를 구성하여 *내부자 속도* 또는 내부자 속도가 *느리도록* 하는 것이 좋습니다.

    > [!WARNING]
    > 초기 설치 후 채널을 전환하려면 제품을 다시 설치해야 합니다. 제품 채널을 전환하려면 기존 패키지를 제거하고 장치를 다시 구성하여 새 채널을 사용하고 이 문서의 단계를 따라 새 위치에서 패키지를 설치합니다.

    배포 및 버전을 기록하고 아래에서 가장 가까운 항목을 `https://packages.microsoft.com/config/` 식별합니다.

    다음 명령에서는 *[배포자]* 및 *[버전]을* 식별한 정보로 바꿉다.

    > [!NOTE]
    > 오라클 리눅스의 경우 *[배포자]를* "용불구"로 바꿉다.

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Ansible 설치를 만들고 YAML 파일을 제거합니다.

    - apt 기반 배포의 경우 다음 YAML 파일을 사용합니다.

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - dnf 기반 배포의 경우 다음 YAML 파일을 사용합니다.

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a>배포

이제 작업 파일 또는 관련 디렉터리 에서 `/etc/ansible/playbooks/` 실행합니다.

- 설치:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> 제품이 처음 시작되면 최신 맬웨어 방지 정의를 다운로드합니다. 인터넷 연결에 따라 최대 몇 분 정도 걸릴 수 있습니다.

- 유효성 검사/구성:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- 설치 취소:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>로그 설치 문제

오류가 발생할 때 설치 관리자가 만든 자동으로 생성된 로그를 찾는 방법에 대한 자세한 내용은 [Log 설치 문제를](linux-resources.md#log-installation-issues) 참조하십시오.

## <a name="operating-system-upgrades"></a>운영 체제 업그레이드

운영 체제를 새 주요 버전으로 업그레이드할 때 먼저 Linux의 끝점에 대한 Defender를 제거하고 업그레이드를 설치하고 마지막으로 장치에서 Linux의 끝점에 대한 수비수를 재구성해야 합니다.

## <a name="references"></a>참조

- [YUM 리포지토리 추가 또는 제거](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [dnf 패키지 관리자로 패키지 관리](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [APT 리포지토리 추가 및 제거](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [apt 패키지 관리](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>참고 항목
- [에이전트 상태 문제 조사](health-status.md)
