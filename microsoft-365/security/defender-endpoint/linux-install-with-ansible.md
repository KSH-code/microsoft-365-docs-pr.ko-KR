---
title: Ansible을 통해 Linux용 Microsoft Defender ATP 배포
ms.reviewer: ''
description: Ansible을 사용하여 Linux용 Microsoft Defender ATP를 배포하는 방법에 대해 설명
keywords: microsoft, defender, atp, linux, 설치, 배포, 제거, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 994adcd718f2318a0bd90e2d8604e6f19b2a42c5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072287"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-ansible"></a><span data-ttu-id="75cd0-104">Ansible을 통해 Linux용 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="75cd0-104">Deploy Microsoft Defender for Endpoint for Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="75cd0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="75cd0-105">**Applies to:**</span></span>
- [<span data-ttu-id="75cd0-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="75cd0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="75cd0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75cd0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="75cd0-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="75cd0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="75cd0-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="75cd0-110">이 문서에서는 Ansible을 사용하여 Linux용 Endpoint용 Defender를 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-110">This article describes how to deploy Defender for Endpoint for Linux using Ansible.</span></span> <span data-ttu-id="75cd0-111">배포를 성공적으로 수행하려면 다음 작업을 모두 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="75cd0-112">온보더링 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="75cd0-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="75cd0-113">Ansible YAML 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="75cd0-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="75cd0-114">배포</span><span class="sxs-lookup"><span data-stu-id="75cd0-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="75cd0-115">참조</span><span class="sxs-lookup"><span data-stu-id="75cd0-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="75cd0-116">선행 조건 및 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="75cd0-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="75cd0-117">시작하기 전에 Linux용 끝점용 주 [Defender](microsoft-defender-endpoint-linux.md) 페이지에서 현재 소프트웨어 버전에 대한 선행 조건 및 시스템 요구 사항에 대한 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75cd0-117">Before you get started, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="75cd0-118">또한 Ansible 배포의 경우 Ansible 관리 작업에 익숙하고, Ansible을 구성하고, 플레이북 및 작업을 배포하는 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="75cd0-119">Ansible에는 동일한 작업을 완료하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="75cd0-120">이러한 지침에서는 패키지 배포에 도움이 되는 *apt* 및 *unarchive와* 같은 지원되는 Ansible 모듈의 가용성을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="75cd0-121">조직에서 다른 워크플로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="75cd0-122">자세한 내용은 [Ansible 설명서를](https://docs.ansible.com/) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75cd0-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="75cd0-123">Ansible needs to be installed on least one computer (we will call it the primary computer).</span><span class="sxs-lookup"><span data-stu-id="75cd0-123">Ansible needs to be installed on at least one computer (we will call it the primary computer).</span></span>
- <span data-ttu-id="75cd0-124">기본 컴퓨터와 모든 클라이언트 간의 관리자 계정에 대해 SSH를 구성해야 합니다. 공개 키 인증을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-124">SSH must be configured for an administrator account between the primary computer and all clients, and it is recommended be configured with public key authentication.</span></span>
- <span data-ttu-id="75cd0-125">모든 클라이언트에 다음 소프트웨어를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-125">The following software must be installed on all clients:</span></span>
  - <span data-ttu-id="75cd0-126">curl</span><span class="sxs-lookup"><span data-stu-id="75cd0-126">curl</span></span>
  - <span data-ttu-id="75cd0-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="75cd0-127">python-apt</span></span>

- <span data-ttu-id="75cd0-128">모든 호스트는 또는 관련 파일에 다음 형식으로 `/etc/ansible/hosts` 나열되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-128">All hosts must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="75cd0-129">Ping 테스트:</span><span class="sxs-lookup"><span data-stu-id="75cd0-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="75cd0-130">온보더링 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="75cd0-130">Download the onboarding package</span></span>

<span data-ttu-id="75cd0-131">Microsoft Defender 보안 센터에서 온보딩 패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="75cd0-132">Microsoft Defender 보안 센터에서 설정 > 장치 관리 > **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="75cd0-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="75cd0-133">첫 번째 드롭다운 메뉴에서 **운영 체제로 Linux Server를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="75cd0-134">두 번째 드롭다운 메뉴에서 배포 **방법으로** 기본 Linux 구성 관리 도구를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="75cd0-135">**온보더링 패키지 다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="75cd0-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="75cd0-136">파일을 다른 파일로 WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="75cd0-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 보안 센터 스크린샷](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="75cd0-138">명령 프롬프트에서 파일이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="75cd0-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="75cd0-139">보관함의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-139">Extract the contents of the archive:</span></span>

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

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="75cd0-140">Ansible YAML 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="75cd0-140">Create Ansible YAML files</span></span>

<span data-ttu-id="75cd0-141">재생 문서 또는 작업에 기여하는 하위 작업 또는 역할 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-141">Create a subtask or role files that contribute to an playbook or task.</span></span>

- <span data-ttu-id="75cd0-142">온보더링 작업 만들기: `onboarding_setup.yml`</span><span class="sxs-lookup"><span data-stu-id="75cd0-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

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

- <span data-ttu-id="75cd0-143">Endpoint 리포지토리 및 키에 대한 Defender를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-143">Add the Defender for Endpoint repository and key.</span></span>

    <span data-ttu-id="75cd0-144">Linux용 Endpoint용 Defender는 다음 채널(아래 *[채널]으로* 표시됨) 중 하나에서 배포할 수 있습니다. *insiders-fast,* *insiders-slow* 또는 *prod*. 이러한 각 채널은 Linux 소프트웨어 리포지토리에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-144">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="75cd0-145">채널 선택에 따라 장치에 제공되는 업데이트의 유형과 빈도가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="75cd0-146">*insiders-fast의* 장치는 업데이트 및 새 기능을 수신하는 첫 번째  장치로, 그 다음에는 이후의 내부자 속도가 느려지며 마지막으로 *prod가 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="75cd0-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="75cd0-147">새 기능을 미리 보고 초기 피드백을 제공하도록 엔터프라이즈의 일부 장치는 *insiders-fast* 또는 *insiders-slow를* 사용하도록 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="75cd0-148">초기 설치 후 채널을 전환하려면 제품을 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="75cd0-149">제품 채널을 전환하려면 기존 패키지를 제거하고 새 채널을 사용하도록 장치를 다시 구성하고 이 문서의 단계에 따라 새 위치에서 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="75cd0-150">배포 및 버전을 확인하고 에서 가장 가까운 항목을 `https://packages.microsoft.com/config/` 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="75cd0-151">다음 명령에서 *[distro]* 및 *[version]을* 식별한 정보로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75cd0-152">Oracle Linux의 경우 *[distro]를* "rhel"으로 바하십시오.</span><span class="sxs-lookup"><span data-stu-id="75cd0-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

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

- <span data-ttu-id="75cd0-153">Ansible 설치를 만들고 YAML 파일을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="75cd0-154">apt 기반 배포의 경우 다음 YAML 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - apt:
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
            - apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="75cd0-155">yum 기반 배포의 경우 다음 YAML 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-155">For yum-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_yum.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - yum:
              name: mdatp
              state: latest
              enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_yum.yml
        ```
        ```Output
        - hosts: servers
        tasks:
            - yum:
               name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="75cd0-156">배포</span><span class="sxs-lookup"><span data-stu-id="75cd0-156">Deployment</span></span>

<span data-ttu-id="75cd0-157">이제 작업 파일을 또는 관련 `/etc/ansible/playbooks/` 디렉터리에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="75cd0-158">설치:</span><span class="sxs-lookup"><span data-stu-id="75cd0-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="75cd0-159">제품이 처음 시작되면 최신 맬웨어 방지 정의를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="75cd0-160">인터넷 연결에 따라 이 시간이 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="75cd0-161">유효성 검사/구성:</span><span class="sxs-lookup"><span data-stu-id="75cd0-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="75cd0-162">제거:</span><span class="sxs-lookup"><span data-stu-id="75cd0-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="75cd0-163">로그 설치 문제</span><span class="sxs-lookup"><span data-stu-id="75cd0-163">Log installation issues</span></span>

<span data-ttu-id="75cd0-164">오류가 [발생할 때](linux-resources.md#log-installation-issues) 설치 관리자에서 자동으로 생성된 로그를 찾는 방법에 대한 자세한 내용은 설치 문제 로그를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75cd0-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="75cd0-165">운영 체제 업그레이드</span><span class="sxs-lookup"><span data-stu-id="75cd0-165">Operating system upgrades</span></span>

<span data-ttu-id="75cd0-166">운영 체제를 새 주 버전으로 업그레이드할 때 먼저 Linux용 Endpoint용 Defender를 제거하고 업그레이드를 설치한 다음 마지막으로 디바이스에서 Linux용 Endpoint용 Defender를 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75cd0-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="75cd0-167">참조</span><span class="sxs-lookup"><span data-stu-id="75cd0-167">References</span></span>

- [<span data-ttu-id="75cd0-168">YUM 리포지토리 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="75cd0-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/2.3/yum_repository_module.html)

- [<span data-ttu-id="75cd0-169">yum 패키지 관리자를 사용하여 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="75cd0-169">Manage packages with the yum package manager</span></span>](https://docs.ansible.com/ansible/latest/modules/yum_module.html)

- [<span data-ttu-id="75cd0-170">APT 리포지토리 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="75cd0-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/modules/apt_repository_module.html)

- [<span data-ttu-id="75cd0-171">apt-packages 관리</span><span class="sxs-lookup"><span data-stu-id="75cd0-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/modules/apt_module.html)
