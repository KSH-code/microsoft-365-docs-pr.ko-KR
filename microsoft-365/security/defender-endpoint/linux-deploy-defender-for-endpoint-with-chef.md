---
title: Linux에서 Endpoint용 Defender를 배포하는 방법(원동기)
description: Linux에서 Endpoint용 Defender를 배포하는 방법에 대해 자세히 알아보기
keywords: microsoft, defender, atp, linux, 검사, 바이러스 백신, 끝점용 Microsoft Defender(linux)
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f8f71f4cafc7034a8d5cc5485989f0cab472a855
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188868"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Chef를 통해 Microsoft Defender for Endpoint(Linux용) 배포

시작하기 전에: 아직 설치되지 않은 경우 unzip을 설치합니다.

지우기 구성 요소가 이미 설치되어 있으며 지민 리포지토리가 존재하여 관리되는 Linux 서버의 Endpoint용 Defender에 배포하는 데 사용할 조리법을 저장합니다(리포지토리 \<reponame\> 생성).

저장소 리포지토리에 있는 준비 문서 폴더 내부에서 다음 명령을 실행하여 기존 리포지토리에 새 가이드를 만들 수 있습니다.

```bash
chef generate cookbook mdatp
```

이 명령은 mdatp라는 새 가이드에 대한 새 폴더 구조를 생성합니다. MDE 배포를 추가하는 데 사용할 기존 가이드가 이미 있는 경우 기존 가이드를 사용할 수도 있습니다.
바로 가기북을 만든 후 방금 만든 문서 폴더 안에 파일 폴더를 만들어야 합니다.

```bash
mkdir mdatp/files
```

이 새 파일 폴더로 Microsoft Defender 보안 센터 다운로드할 수 있는 Linux Server 온보더링 zip 파일을 전송합니다.

이동식 Workstation에서 mdatp/recipes 폴더로 이동합니다. 이 폴더는 작성된 문서가 생성될 때 만들어집니다. 기본 설정 텍스트 편집기(예: vi 또는 nano)를 사용하여 default.rb 파일의 끝에 다음 지침을 추가합니다.

- include_recipe '::onboard_mdatp'
- include_recipe '::install_mdatp'

그런 다음 default.rb 파일을 저장하고 닫습니다.

그런 다음 조리법 폴더에 install_mdatp.rb라는 새 조리법 파일을 만들고 이 텍스트를 파일에 추가합니다.

```powershell
#Add Microsoft Defender
Repo
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/config/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/config/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

배포할 버전 및 배포할 채널과 일치하도록 버전 번호, 배포 및 리포지타임 이름을 수정해야 합니다.
다음으로 mdatp/recipies 폴더에 onboard_mdatp.rb 파일을 만들어야 합니다. 해당 파일에 다음 텍스트를 추가합니다.

```powershell
#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

경로 이름을 온보더링 파일의 위치로 업데이트해야 합니다.
지우기 작업에서 배포를 테스트하기 위해 를 ``sudo chef-client -z -o mdatp`` 실행합니다.
배포 후 [Linux의 끝점용 Microsoft Defender에](/linux-preferences.md)대한 기본 설정 설정에 따라 구성 파일을 만들어 서버에 배포하는 것을 고려해야 합니다.
구성 파일을 만들어 테스트한 후 이 파일을 온보더링 패키지를 배치한 준비 문서/mdatp/files 폴더에 배치할 수 있습니다. 그런 다음 mdatp/recipies 폴더에 settings_mdatp.rb 파일을 만들고 다음 텍스트를 추가할 수 있습니다.

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

이 단계를 조리법의 일부로 포함하기 위해 조리법 폴더 내의 default.include_recipe settings_mdatp ':: settings_mdatp'를 추가합니다.
크로ntab를 사용하여 자동 업데이트를 예약할 수도 있습니다. [끝점용 Microsoft Defender 업데이트 예약(Linux)](linux-update-MDE-Linux.md).

MDATP 가이드 제거:

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```
