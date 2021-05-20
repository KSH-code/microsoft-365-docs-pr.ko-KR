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
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="b4a1e-104">Ansible와 리눅스에 엔드 포인트에 대 한 마이크로소프트 수비수 배포</span><span class="sxs-lookup"><span data-stu-id="b4a1e-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b4a1e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b4a1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4a1e-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b4a1e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b4a1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4a1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b4a1e-108">엔드포인트에 대한 수비수를 경험하고 싶으십니까?</span><span class="sxs-lookup"><span data-stu-id="b4a1e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b4a1e-109">무료 평가판에 가입하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b4a1e-110">이 문서에서는 Ansible을 사용하여 리눅스에 엔드포인트에 대한 수비수를 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="b4a1e-111">성공적인 배포를 위해서는 다음 모든 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="b4a1e-112">온보딩 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="b4a1e-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="b4a1e-113">Ansible YAML 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="b4a1e-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="b4a1e-114">배포</span><span class="sxs-lookup"><span data-stu-id="b4a1e-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="b4a1e-115">참조</span><span class="sxs-lookup"><span data-stu-id="b4a1e-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="b4a1e-116">전제 조건 및 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4a1e-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="b4a1e-117">시작하기 전에 현재 소프트웨어 버전에 대한 필수 구성 요소 및 시스템 요구 사항에 대한 설명은 [Linux의 끝점에 대한 기본 수비수 페이지를](microsoft-defender-endpoint-linux.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="b4a1e-118">또한 Ansible 배포의 경우 Ansible 관리 작업에 익숙하고 Ansible을 구성하고 플레이북 및 작업을 배포하는 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="b4a1e-119">Ansible은 동일한 작업을 완료하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="b4a1e-120">이러한 지침은 패키지를 배포하는 데 도움이 되는 *apt* 및 *아카이브 해제와* 같이 지원되는 Ansible 모듈의 가용성을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="b4a1e-121">조직에서 다른 워크플로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="b4a1e-122">자세한 내용은 [Ansible 문서를](https://docs.ansible.com/) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="b4a1e-123">Ansible은 하나 이상의 컴퓨터에 설치해야 합니다(Ansible은 이 것을 제어 노드라고 호출합니다).</span><span class="sxs-lookup"><span data-stu-id="b4a1e-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="b4a1e-124">SSH는 제어 노드와 관리되는 모든 노드(엔드포인트에 대한 Defender가 설치되는 장치) 사이의 관리자 계정에 대해 구성해야 하며 공개 키 인증으로 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="b4a1e-125">관리되는 모든 노드에 다음 소프트웨어를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="b4a1e-126">컬</span><span class="sxs-lookup"><span data-stu-id="b4a1e-126">curl</span></span>
  - <span data-ttu-id="b4a1e-127">파이썬 -apt</span><span class="sxs-lookup"><span data-stu-id="b4a1e-127">python-apt</span></span>

- <span data-ttu-id="b4a1e-128">관리되는 모든 노드는 다음 형식 또는 관련 파일에 나열되어야 `/etc/ansible/hosts` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="b4a1e-129">핑 테스트:</span><span class="sxs-lookup"><span data-stu-id="b4a1e-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="b4a1e-130">온보딩 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="b4a1e-130">Download the onboarding package</span></span>

<span data-ttu-id="b4a1e-131">Microsoft Defender 보안 센터 온보딩 패키지를 다운로드하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="b4a1e-132">Microsoft Defender 보안 센터 **온보딩**> 장치 관리 설정 >.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="b4a1e-133">첫 번째 드롭다운 메뉴에서 **Linux Server를** 운영 체제로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="b4a1e-134">두 번째 드롭다운 메뉴에서 선호하는 Linux 구성 관리 도구를 배포 방법으로 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b4a1e-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="b4a1e-135">**온보딩 패키지 다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b4a1e-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="b4a1e-136">파일을 WindowsDefenderATPOnboardingPackage.zip 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 보안 센터 스크린샷](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="b4a1e-138">명령 프롬프트에서 파일이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="b4a1e-139">아카이브의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-139">Extract the contents of the archive:</span></span>

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

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="b4a1e-140">Ansible YAML 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="b4a1e-140">Create Ansible YAML files</span></span>

<span data-ttu-id="b4a1e-141">플레이북이나 작업에 기여하는 하위 작업 또는 역할 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-141">Create a subtask or role files that contribute to a playbook or task.</span></span>

- <span data-ttu-id="b4a1e-142">온보딩 작업 `onboarding_setup.yml` 만들기:</span><span class="sxs-lookup"><span data-stu-id="b4a1e-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

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

- <span data-ttu-id="b4a1e-143">끝점 리포지토리 및 키에 대한 수비수 `add_apt_repo.yml` 추가:</span><span class="sxs-lookup"><span data-stu-id="b4a1e-143">Add the Defender for Endpoint repository and key, `add_apt_repo.yml`:</span></span>

    <span data-ttu-id="b4a1e-144">리눅스의 끝점에 대한 수비수는 다음 채널 중 하나에서 배포 할 수 있습니다 *([채널]로* 아래 표시 ): *내부자 빠른,* *내부자 느린,* 또는 *prod*. 이러한 각 채널은 Linux 소프트웨어 리포지토리에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="b4a1e-145">채널을 선택하면 장치에 제공되는 업데이트의 유형과 빈도가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="b4a1e-146">내부자 *빠른* 장치는 업데이트 및 새로운 기능을 수신하는 첫 번째 장치입니다, 내부자 *느린* 마지막으로 *prod에* 의해 다음.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="b4a1e-147">새로운 기능을 미리 보고 초기 피드백을 제공하기 위해 엔터프라이즈내 일부 장치를 구성하여 *내부자 속도* 또는 내부자 속도가 *느리도록* 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="b4a1e-148">초기 설치 후 채널을 전환하려면 제품을 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="b4a1e-149">제품 채널을 전환하려면 기존 패키지를 제거하고 장치를 다시 구성하여 새 채널을 사용하고 이 문서의 단계를 따라 새 위치에서 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="b4a1e-150">배포 및 버전을 기록하고 아래에서 가장 가까운 항목을 `https://packages.microsoft.com/config/` 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="b4a1e-151">다음 명령에서는 *[배포자]* 및 *[버전]을* 식별한 정보로 바꿉다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4a1e-152">오라클 리눅스의 경우 *[배포자]를* "용불구"로 바꿉다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

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

- <span data-ttu-id="b4a1e-153">Ansible 설치를 만들고 YAML 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="b4a1e-154">apt 기반 배포의 경우 다음 YAML 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-154">For apt-based distributions use the following YAML file:</span></span>

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

    - <span data-ttu-id="b4a1e-155">dnf 기반 배포의 경우 다음 YAML 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-155">For dnf-based distributions use the following YAML file:</span></span>

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

## <a name="deployment"></a><span data-ttu-id="b4a1e-156">배포</span><span class="sxs-lookup"><span data-stu-id="b4a1e-156">Deployment</span></span>

<span data-ttu-id="b4a1e-157">이제 작업 파일 또는 관련 디렉터리 에서 `/etc/ansible/playbooks/` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="b4a1e-158">설치:</span><span class="sxs-lookup"><span data-stu-id="b4a1e-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="b4a1e-159">제품이 처음 시작되면 최신 맬웨어 방지 정의를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="b4a1e-160">인터넷 연결에 따라 최대 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="b4a1e-161">유효성 검사/구성:</span><span class="sxs-lookup"><span data-stu-id="b4a1e-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="b4a1e-162">설치 취소:</span><span class="sxs-lookup"><span data-stu-id="b4a1e-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="b4a1e-163">로그 설치 문제</span><span class="sxs-lookup"><span data-stu-id="b4a1e-163">Log installation issues</span></span>

<span data-ttu-id="b4a1e-164">오류가 발생할 때 설치 관리자가 만든 자동으로 생성된 로그를 찾는 방법에 대한 자세한 내용은 [Log 설치 문제를](linux-resources.md#log-installation-issues) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="b4a1e-165">운영 체제 업그레이드</span><span class="sxs-lookup"><span data-stu-id="b4a1e-165">Operating system upgrades</span></span>

<span data-ttu-id="b4a1e-166">운영 체제를 새 주요 버전으로 업그레이드할 때 먼저 Linux의 끝점에 대한 Defender를 제거하고 업그레이드를 설치하고 마지막으로 장치에서 Linux의 끝점에 대한 수비수를 재구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4a1e-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="b4a1e-167">참조</span><span class="sxs-lookup"><span data-stu-id="b4a1e-167">References</span></span>

- [<span data-ttu-id="b4a1e-168">YUM 리포지토리 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="b4a1e-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="b4a1e-169">dnf 패키지 관리자로 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="b4a1e-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="b4a1e-170">APT 리포지토리 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="b4a1e-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="b4a1e-171">apt 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="b4a1e-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a><span data-ttu-id="b4a1e-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4a1e-172">See also</span></span>
- [<span data-ttu-id="b4a1e-173">에이전트 상태 문제 조사</span><span class="sxs-lookup"><span data-stu-id="b4a1e-173">Investigate agent health issues</span></span>](health-status.md)
