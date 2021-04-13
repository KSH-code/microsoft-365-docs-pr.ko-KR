---
title: Puppet을 통해 Linux용 Microsoft Defender ATP 배포
ms.reviewer: ''
description: Puppet을 사용하여 Linux용 Microsoft Defender ATP를 배포하는 방법에 대해 설명
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 562433ee52b2e39716e933c67c706f030195bd2f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688420"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a><span data-ttu-id="75907-104">Puppet을 통해 Linux에서 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="75907-104">Deploy Microsoft Defender for Endpoint on Linux with Puppet</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="75907-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="75907-105">**Applies to:**</span></span>
- <span data-ttu-id="75907-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="75907-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="75907-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75907-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="75907-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="75907-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="75907-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="75907-110">이 문서에서는 Puppet을 사용하여 Linux용 Endpoint용 Defender를 배포하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-110">This article describes how to deploy Defender for Endpoint for Linux using Puppet.</span></span> <span data-ttu-id="75907-111">배포를 성공적으로 수행하려면 다음 작업을 모두 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="75907-112">온보더링 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="75907-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="75907-113">Puppet 매니페스트 만들기</span><span class="sxs-lookup"><span data-stu-id="75907-113">Create Puppet manifest</span></span>](#create-a-puppet-manifest)
- [<span data-ttu-id="75907-114">배포</span><span class="sxs-lookup"><span data-stu-id="75907-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="75907-115">온보더링 상태 확인</span><span class="sxs-lookup"><span data-stu-id="75907-115">Check onboarding status</span></span>](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="75907-116">선행 조건 및 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="75907-116">Prerequisites and system requirements</span></span>

 <span data-ttu-id="75907-117">현재 소프트웨어 버전에 대한 선행 조건 및 시스템 요구 사항에 대한 설명은 [Linux용 끝점용 주 Defender 페이지를 참조하세요.](microsoft-defender-endpoint-linux.md)</span><span class="sxs-lookup"><span data-stu-id="75907-117">For a description of prerequisites and system requirements for the current software version, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md).</span></span>

<span data-ttu-id="75907-118">또한 Puppet 배포의 경우 Puppet 관리 작업에 익숙하고, Puppet을 구성하고, 패키지를 배포하는 방법을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-118">In addition, for Puppet deployment, you need to be familiar with Puppet administration tasks, have Puppet configured, and know how to deploy packages.</span></span> <span data-ttu-id="75907-119">Puppet에는 동일한 작업을 여러 가지 방법으로 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75907-119">Puppet has many ways to complete the same task.</span></span> <span data-ttu-id="75907-120">이러한 지침에서는 패키지 배포에 도움이 되는 *apt와* 같은 지원되는 Puppet 모듈의 가용성을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-120">These instructions assume availability of supported Puppet modules, such as *apt* to help deploy the package.</span></span> <span data-ttu-id="75907-121">조직에서 다른 워크플로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75907-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="75907-122">자세한 내용은 [Puppet 설명서를](https://puppet.com/docs) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="75907-122">Refer to the [Puppet documentation](https://puppet.com/docs) for details.</span></span>

## <a name="download-the-onboarding-package"></a><span data-ttu-id="75907-123">온보더링 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="75907-123">Download the onboarding package</span></span>

<span data-ttu-id="75907-124">Microsoft Defender 보안 센터에서 온보딩 패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-124">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="75907-125">Microsoft Defender 보안 센터에서 설정 > 장치 관리 > **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="75907-125">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="75907-126">첫 번째 드롭다운 메뉴에서 **운영 체제로 Linux Server를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-126">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="75907-127">두 번째 드롭다운 메뉴에서 배포 **방법으로** 기본 Linux 구성 관리 도구를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-127">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="75907-128">**온보더링 패키지 다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="75907-128">Select **Download onboarding package**.</span></span> <span data-ttu-id="75907-129">파일을 다른 파일로 WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="75907-129">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender 보안 센터 스크린샷](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="75907-131">명령 프롬프트에서 파일이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="75907-131">From a command prompt, verify that you have the file.</span></span> 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. <span data-ttu-id="75907-132">보관함의 내용을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-132">Extract the contents of the archive.</span></span>
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a><span data-ttu-id="75907-133">Puppet 매니페스트 만들기</span><span class="sxs-lookup"><span data-stu-id="75907-133">Create a Puppet manifest</span></span>

<span data-ttu-id="75907-134">Puppet 서버에서 관리하는 장치에 Linux용 Defender for Endpoint를 배포하기 위한 Puppet 매니페스트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-134">You need to create a Puppet manifest for deploying Defender for Endpoint for Linux to devices managed by a Puppet server.</span></span> <span data-ttu-id="75907-135">이 예제에서는 puppetlabs에서 사용할 수 있는 *apt* 및 *yumrepo* 모듈을 사용하며, 모듈이 Puppet 서버에 설치되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-135">This example makes use of the *apt* and *yumrepo* modules available from puppetlabs, and assumes that the modules have been installed on your Puppet server.</span></span>

<span data-ttu-id="75907-136">Puppet 설치의 *모듈 install_mdatp/파일* 및 install_mdatp/매니페스트에 대한 폴더를 만들 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="75907-136">Create the folders *install_mdatp/files* and *install_mdatp/manifests* under the modules folder of your Puppet installation.</span></span> <span data-ttu-id="75907-137">이 폴더는 일반적으로 Puppet 서버의 */etc/puppetlabs/code/environments/production/modules에* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75907-137">This folder is typically located in */etc/puppetlabs/code/environments/production/modules* on your Puppet server.</span></span> <span data-ttu-id="75907-138">위에서 mdatp_onboard.js파일 폴더에 install_mdatp *파일을 복사합니다.*</span><span class="sxs-lookup"><span data-stu-id="75907-138">Copy the mdatp_onboard.json file created above to the *install_mdatp/files* folder.</span></span> <span data-ttu-id="75907-139">*init.pp 만들기*</span><span class="sxs-lookup"><span data-stu-id="75907-139">Create an *init.pp*</span></span> <span data-ttu-id="75907-140">배포 지침이 포함된 파일:</span><span class="sxs-lookup"><span data-stu-id="75907-140">file that contains the deployment instructions:</span></span>

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a><span data-ttu-id="75907-141">의 내용 `install_mdatp/manifests/init.pp`</span><span class="sxs-lookup"><span data-stu-id="75907-141">Contents of `install_mdatp/manifests/init.pp`</span></span>

<span data-ttu-id="75907-142">Linux용 Endpoint용 Defender는 다음 채널(아래 *[채널]으로* 표시됨) 중 하나에서 배포할 수 있습니다. *insiders-fast,* *insiders-slow* 또는 *prod*. 이러한 각 채널은 Linux 소프트웨어 리포지토리에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-142">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

<span data-ttu-id="75907-143">채널 선택에 따라 장치에 제공되는 업데이트의 유형과 빈도가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="75907-143">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="75907-144">*insiders-fast의* 장치는 업데이트 및 새 기능을 수신하는 첫 번째  장치로, 그 다음에는 이후의 내부자 속도가 느려지며 마지막으로 *prod가 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="75907-144">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="75907-145">새 기능을 미리 보고 초기 피드백을 제공하도록 엔터프라이즈의 일부 장치는 *insiders-fast* 또는 *insiders-slow를* 사용하도록 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="75907-145">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="75907-146">초기 설치 후 채널을 전환하려면 제품을 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-146">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="75907-147">제품 채널을 전환하려면 기존 패키지를 제거하고 새 채널을 사용하도록 장치를 다시 구성하고 이 문서의 단계에 따라 새 위치에서 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-147">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

<span data-ttu-id="75907-148">배포 및 버전을 확인하고 에서 가장 가까운 항목을 `https://packages.microsoft.com/config/` 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-148">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

<span data-ttu-id="75907-149">아래 명령에서 *[distro]* 및 *[version]을* 식별한 정보로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-149">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

> [!NOTE]
> <span data-ttu-id="75907-150">RedHat, Oracle EL 및 CentOS 8의 경우 *[distro]를* 'rhel'으로 바꿈합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-150">In case of RedHat, Oracle EL, and CentOS 8, replace *[distro]* with 'rhel'.</span></span>

```puppet
# Puppet manifest to install Microsoft Defender ATP.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a><span data-ttu-id="75907-151">배포</span><span class="sxs-lookup"><span data-stu-id="75907-151">Deployment</span></span>

<span data-ttu-id="75907-152">site.pp에 위의 매니페스트 포함</span><span class="sxs-lookup"><span data-stu-id="75907-152">Include the above manifest in your site.pp</span></span> <span data-ttu-id="75907-153">파일:</span><span class="sxs-lookup"><span data-stu-id="75907-153">file:</span></span>

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

<span data-ttu-id="75907-154">등록된 에이전트 장치는 정기적으로 Puppet 서버를 폴링하고 새 구성 프로필 및 정책이 검색되는 즉시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-154">Enrolled agent devices periodically poll the Puppet Server and install new configuration profiles and policies as soon as they are detected.</span></span>

## <a name="monitor-puppet-deployment"></a><span data-ttu-id="75907-155">Puppet 배포 모니터링</span><span class="sxs-lookup"><span data-stu-id="75907-155">Monitor Puppet deployment</span></span>

<span data-ttu-id="75907-156">에이전트 장치에서 다음을 실행하여 온보더링 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75907-156">On the agent device, you can also check the onboarding status by running:</span></span>

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- <span data-ttu-id="75907-157">**licensed:** 이 경우 장치가 조직에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="75907-157">**licensed**: This confirms that the device is tied to your organization.</span></span>

- <span data-ttu-id="75907-158">**orgId**: 끝점 조직 식별자에 대한 Defender입니다.</span><span class="sxs-lookup"><span data-stu-id="75907-158">**orgId**: This is your Defender for Endpoint organization identifier.</span></span>

## <a name="check-onboarding-status"></a><span data-ttu-id="75907-159">온보더링 상태 확인</span><span class="sxs-lookup"><span data-stu-id="75907-159">Check onboarding status</span></span>

<span data-ttu-id="75907-160">스크립트를 만들어 장치가 올바르게 온보딩된지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75907-160">You can check that devices have been correctly onboarded by creating a script.</span></span> <span data-ttu-id="75907-161">예를 들어 다음 스크립트는 등록된 디바이스에서 등록 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-161">For example, the following script checks enrolled devices for onboarding status:</span></span>

```bash
mdatp health --field healthy
```

<span data-ttu-id="75907-162">위의 명령은 제품이 온보드되어 예상대로 작동하면 `1` 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-162">The above command prints `1` if the product is onboarded and functioning as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75907-163">제품이 처음 시작되면 최신 맬웨어 방지 정의를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-163">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="75907-164">인터넷 연결에 따라 이 시간이 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75907-164">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="75907-165">이 시간 동안 위의 명령은 의 값을 `0` 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-165">During this time the above command returns a value of `0`.</span></span>

<span data-ttu-id="75907-166">제품이 정상이 아닌 경우 종료 코드(를 통해 확인할 수 있습니다.)는 `echo $?` 문제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75907-166">If the product is not healthy, the exit code (which can be checked through `echo $?`) indicates the problem:</span></span>

- <span data-ttu-id="75907-167">1 장치가 아직 온보드되지 않은 경우 1입니다.</span><span class="sxs-lookup"><span data-stu-id="75907-167">1 if the device isn't onboarded yet.</span></span>
- <span data-ttu-id="75907-168">3 데몬에 대한 연결을 설정하지 못하면 3.</span><span class="sxs-lookup"><span data-stu-id="75907-168">3 if the connection to the daemon cannot be established.</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="75907-169">로그 설치 문제</span><span class="sxs-lookup"><span data-stu-id="75907-169">Log installation issues</span></span>

 <span data-ttu-id="75907-170">오류가 발생할 때 설치 관리자에서 자동으로 생성된 로그를 찾는 방법에 대한 자세한 내용은 로그 설치 [문제 를 참조하세요.](linux-resources.md#log-installation-issues)</span><span class="sxs-lookup"><span data-stu-id="75907-170">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Log installation issues](linux-resources.md#log-installation-issues).</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="75907-171">운영 체제 업그레이드</span><span class="sxs-lookup"><span data-stu-id="75907-171">Operating system upgrades</span></span>

<span data-ttu-id="75907-172">운영 체제를 새 주 버전으로 업그레이드할 때 먼저 Linux용 Endpoint용 Defender를 제거하고 업그레이드를 설치한 다음 마지막으로 디바이스에서 Linux용 Endpoint용 Defender를 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75907-172">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="75907-173">제거</span><span class="sxs-lookup"><span data-stu-id="75907-173">Uninstallation</span></span>

<span data-ttu-id="75907-174">*init.pp에서* *remove_mdatp*  있는 install_mdatp 모듈 만들기</span><span class="sxs-lookup"><span data-stu-id="75907-174">Create a module *remove_mdatp* similar to *install_mdatp* with the following contents in *init.pp*</span></span> <span data-ttu-id="75907-175">파일:</span><span class="sxs-lookup"><span data-stu-id="75907-175">file:</span></span>

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
